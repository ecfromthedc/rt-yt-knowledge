---
type: bulletproofing-report
project: RT YouTube Growth Arm
phase: pre-initiation hardening
date: 2026-06-06
author: Claude (bulletproofing audit)
scope: rt-yt-skills (teardown.py, topic_loop.py) + rt-yt-knowledge-SEED corpus + operator end-to-end path
status: audit complete — TOP 5 must clear before team initiation
tags: [yt-growth, hardening, audit, operator-onboarding, factory]
---

# Bulletproofing Report — RT YouTube Growth Arm

**Verdict:** The machine works (both skills run clean against live tools; Ollama up, yt-dlp 2026.03.17, all four lane Script Bibles present). But it is **not yet operator-proof.** A non-technical operator (Glitch on aviation, Jay on distribution) will hit a wall in the first 30 minutes because of (a) doc/path drift between what the corpus README promises and what's on disk, (b) raw Python tracebacks on the most common failure (Ollama not running), and (c) a silent-success bug in `topic_loop.py` that emits a plausible-but-ungrounded queue on any lane typo. Fix the TOP 5 below and the system is initiation-ready.

This audit READ the live source of both skills, ran their error paths, and inventoried the SEED corpus against its own README.

---

## Environment baseline (verified live, 2026-06-06)

| Dependency | Status |
|---|---|
| `yt-dlp` | ✅ `/opt/homebrew/bin/yt-dlp` v2026.03.17 |
| `ollama` (API) | ✅ `localhost:11434` UP |
| Ollama models | ✅ `qwen2.5:7b` (default), `llama3.1:8b`, `gemma4`, `nomic-embed-text` — all present |
| `ffmpeg` / `whisper` | ✅ both present (whisper fallback path viable) |
| `gh` repos | ✅ `ecfromthedc/rt-yt-knowledge` (default `main`) + `rt-yt-substrate` both exist remotely |
| Script Bibles | ✅ all 4 lanes (history, ai-dev, aviation, meditation) |
| `timeout` binary | ⚠️ NOT installed on macOS (only matters for ops wrapping calls — note for Cron/loop wrappers; use `gtimeout` or none) |

**Tested error paths live:**
- `topic_loop.py --lane doesnotexist` → **silently SUCCEEDED**, wrote a stray `lanes/doesnotexist/topic-queue.md` from formulas only (0 competitor grounding). Bug. (Stray dir cleaned during audit.)
- Ollama unreachable (simulated wrong port) → operator sees raw `urlopen error [Errno 61] Connection refused` traceback, **zero guidance**.

---

## A. Failure-mode inventory (concrete)

### 1. Ollama down / unreachable — UNFRIENDLY (high frequency)
Both `teardown.py` (`ollama()`, line 82–87) and `topic_loop.py` (`ollama()`, line 29–34) call `urllib.request.urlopen` with no try/except. If Ollama isn't running (laptop just booted, `ollama serve` not started, model not pulled), the operator gets a raw `ConnectionRefusedError` / `URLError` traceback. This is the single most likely first-run failure and the current message is useless to a non-coder. **No preflight check that the API is up or the model is pulled.**

### 2. `topic_loop.py` accepts ANY lane and silently produces ungrounded output — SILENT-SUCCESS BUG (high impact)
`main()` (line 95–108) only `WARN`s on a missing Script Bible, then proceeds and **writes `lanes/<typo>/topic-queue.md` anyway**, creating a junk directory and a queue with no competitor grounding and no proven formulas. An operator who types `--lane avaition` gets a confident-looking queue that is actually garbage, plus pollutes the corpus tree. Should hard-fail on an unknown lane unless `--force` is passed.

### 3. Wrong/dead channel handle — partially handled, but weak
`teardown.py fetch_videos()` (line 33–51) returns `[]` on a bad handle and `main()` exits with `ERROR: no videos found (check handle).` (line 171–172) — acceptable. BUT: a **valid channel with all-zero `view_count`** (brand-new channel, or yt-dlp flat-playlist quirk) passes the `if not vids` guard, then `avg`/`top_avg` math runs on zeros. `write_doc()` guards divide-by-zero with `max(1, …)` so it won't crash, but it emits a teardown claiming "the power law is live" with fabricated 1.0x ratios. Misleading. No "views look suspicious / 0" warning.

### 4. Missing captions — handled, but the whole teardown can be hollow
`fetch_hook()` (line 53–80) returns `None` when no `.vtt` is produced, and `analyze_hooks()` (line 100–111) degrades gracefully to a "_No captions available_" note. Good. But if **all** top videos lack captions (common on music/meditation/aviation-cockpit-audio channels), §4 of the teardown is empty and the operator may not realize half the doc is missing. No summary line flagging "0/3 hooks captured — hook analysis skipped."

### 5. yt-dlp rate limiting / bot-check — UNHANDLED
No retry/backoff, no `--sleep-requests`, no cookies option. YouTube increasingly throws `Sign in to confirm you're not a bot` / HTTP 429 on `--dump-json` over a channel. `fetch_videos()` swallows per-line JSON errors but a top-level yt-dlp failure (429, bot wall) yields `[]` → the misleading "check handle" error, sending the operator chasing the wrong problem. No distinction between "bad handle" and "YouTube blocked us."

### 6. yt-dlp version drift — SINGLE POINT OF FAILURE
The entire research engine depends on yt-dlp parsing YouTube's HTML/API. YouTube breaks yt-dlp roughly monthly. There is no `yt-dlp -U` reminder, no version pin, and no "if extraction returns 0 across a known-good channel, update yt-dlp" runbook. When YouTube changes, **every operator's teardown breaks simultaneously** with the same misleading "check handle" message.

### 7. Hardcoded `/tmp` temp files — minor leak / collision risk
`fetch_hook()` writes to `/tmp/td-<id>` and scans `/tmp` for `.vtt` (line 55–63). Two operators (or two parallel runs) tearing down the same video ID race on the same path. Also `/tmp` isn't `$TMPDIR` (CLAUDE.md convention). Low severity, but the `/tmp` listdir scan is fragile if a stale `td-<id>.en.vtt` from a prior run lingers.

### 8. `--out` path is a 200-char absolute Session-Logs path baked into both scripts
`teardown.py` line 166–167 and `topic_loop.py` `SEED` line 19–20 hardcode the local `Session Logs/2026-06/session-2026-06-05/...` path. When this corpus is promoted to the `rt-yt-knowledge` repo (or any operator clones it to a different machine/path), the default write target is **wrong** and points into Eric's vault, not the operator's clone. Operators on their own machines will write into a path that doesn't exist or isn't theirs. Should resolve from an env var (`RT_YT_CORPUS`) with the Session-Logs path only as fallback.

---

## B. Corpus / doc-drift gaps (what trips a non-technical operator)

### 9. operator-playbooks are NOT where the system says they are — PATH DRIFT (initiation blocker)
The lane operator playbooks exist at `factory-build/playbooks/{history,ai-dev,aviation,meditation}-operator-playbook.md` — **not** inside the SEED lane folders. An operator handed "read `lanes/<your-lane>/` and your operator-playbook" (per task framing and corpus README spirit) will not find a playbook in their lane folder. The single most important onboarding doc is orphaned from the path an operator is pointed at.

### 10. Corpus README promises files that don't exist — TRUST/NAV GAP
`rt-yt-knowledge-SEED/README.md` (and each lane `README.md`) advertises `hook-patterns.md`, `thumbnail-patterns.md`, `rpm-notes.md` per lane, plus top-level `winner-log/` and `format-library/`. On disk: **none of the per-lane files exist**, and `winner-log/` + `format-library/` are **empty directories**. An operator opening their lane folder finds a README describing 5 files but sees only `script-bible.md` + `teardowns/`. This reads as "broken/incomplete," undermining confidence on day one. Either create stub files (with "fill after first 3 videos" TODO) or trim the README to match reality.

### 11. Two lanes have no topic-queue — UNEVEN STARTING LINE
`history` and `ai-dev` have `topic-queue.md`; `aviation` (Glitch) and `meditation` (Jay's option) do **not**. Glitch boots up with no candidate topics while Sam and John have 12 each. Both lanes HAVE Script Bibles, so this is a one-command fix per lane (`topic_loop.py --lane aviation --n 12`), but it must be done before initiation so every operator starts equal.

### 12. winner-log + format-library are empty with no seed/example — COLD START
The "every over-indexer gets a winner-log entry" rule (README) has no example entry to copy. `_templates/winner-log-entry.md` exists, but the live `winner-log/` dir is empty. First operator to land a winner has no worked example in-place. Drop one filled sample entry so the pattern is obvious.

### 13. Lane↔operator mapping inconsistency — meditation vs distribution
Corpus README maps lanes to history(Sam)/ai-dev(John)/aviation(Glitch)/meditation(unassigned). Task framing lists Jay as "distribution + meditation option." There is **no `distribution` lane**, and `meditation` is labeled "unassigned" in the README. Jay's onboarding doc (`meditation-operator-playbook.md`) exists but the corpus says "unassigned." Reconcile the mapping so Jay knows meditation is his and distribution is a cross-lane function, not a missing lane.

### 14. No single "START HERE" entrypoint for an operator
There are excellent docs (`Factory-Operating-Guide.md`, `Reverse-Engineering-Workshop.md` in `factory-build/education/`, the operator playbooks in `factory-build/playbooks/`, the Operator Field Manual, the Script Bibles), but they live in **three different directories** and nothing says "Operator: open THIS file first, then run THESE two commands." A non-technical operator needs one linear runbook. This is the connective tissue gap.

---

## C. Prioritized hardening checklist

**P0 — initiation blockers (do before any operator touches this):**
- [ ] **Fix `topic_loop.py` unknown-lane silent success** — hard-fail unless lane dir exists OR `--force` passed; never write a stray `lanes/<typo>/`. (file: `topic_loop.py`, `main()` after `gather`)
- [ ] **Add Ollama preflight + friendly error** to BOTH scripts — before any `ollama()` call, GET `http://localhost:11434/api/tags`; on failure print: `Ollama not running. Start it with: ollama serve  (then: ollama pull qwen2.5:7b)` and exit 2. Wrap the `urlopen` in try/except for the same message. (files: `teardown.py` + `topic_loop.py`, new `ollama_preflight()`)
- [ ] **Generate the two missing topic-queues** — `topic_loop.py --lane aviation --n 12` and `--lane meditation --n 12`. (no code change)
- [ ] **Resolve the operator-playbook path drift** — either copy each `factory-build/playbooks/<lane>-operator-playbook.md` into `SEED/lanes/<lane>/operator-playbook.md`, or add a one-line pointer in each lane README. Every operator must find their playbook from their lane folder.
- [ ] **Write the "START HERE" operator runbook** — one file in `initiation/` (or each lane folder) that says, in order: read your operator-playbook → read your Script Bible → run `teardown.py` on 1 new competitor → run `topic_loop.py` → pick 1 topic → Trends-verify → produce. The single linear on-ramp.

**P1 — hardening (do this week, before scaling past lane #4):**
- [ ] **Distinguish yt-dlp "bad handle" vs "blocked/429"** in `teardown.py` — inspect yt-dlp stderr; if it contains `Sign in`/`429`/`bot`, print a rate-limit-specific message + "run `yt-dlp -U`". (file: `teardown.py`, `fetch_videos()`)
- [ ] **Add `--sleep-requests 1` + one retry** to the `yt-dlp --dump-json` call to soften rate limiting. (file: `teardown.py`, `fetch_videos()`)
- [ ] **Warn on all-zero / suspicious view counts** before writing the teardown ("views all 0 — yt-dlp may be flat-listing; re-run or update yt-dlp"). (file: `teardown.py`, after `fetch_videos`)
- [ ] **Flag empty hook capture** — if 0/N hooks captured, print a visible warning and stamp the doc "§4 skipped: no captions." (file: `teardown.py`, after the hook loop)
- [ ] **Env-driven corpus path** — read `RT_YT_CORPUS` env var, fall back to the Session-Logs path. (files: both scripts, `--out` default + `SEED`)
- [ ] **Reconcile README ↔ disk** — create stub `hook-patterns.md` / `thumbnail-patterns.md` / `rpm-notes.md` per lane (or trim the READMEs); drop one example `winner-log/` entry; clarify meditation=Jay in the corpus README.

**P2 — robustness / hygiene (do before cron/swarm automation):**
- [ ] Switch `/tmp` → `$TMPDIR` and make temp filenames run-unique (PID/uuid) in `fetch_hook()`. (file: `teardown.py`)
- [ ] Add a `yt-dlp -U` reminder + "if a known-good channel returns 0 videos, update yt-dlp first" line to the operator runbook (yt-dlp drift is the portfolio-wide SPOF).
- [ ] Pin/record working `yt-dlp` version in the repo (`requirements`/runbook) so a green baseline exists.
- [ ] Add a tiny `doctor` command/script (`rt-yt doctor`) that checks yt-dlp present+recent, Ollama up, model pulled, corpus path resolvable — one command an operator runs before starting.

---

## D. TOP 5 — fix BEFORE initiating the team

1. **`topic_loop.py` silent-success on unknown lane** — *file: `topic_loop.py`, `main()`.* It currently writes a junk, ungrounded `lanes/<typo>/topic-queue.md` and exits 0. Hard-fail when the lane folder/Script Bible is absent (require `--force` to override). A typo today = a confident garbage queue an operator might actually produce against.

2. **Ollama-down gives a raw traceback in BOTH scripts** — *files: `teardown.py` & `topic_loop.py`, the `ollama()` functions.* Add a preflight ping to `localhost:11434/api/tags` and wrap `urlopen` in try/except, printing `Ollama not running — run: ollama serve (then ollama pull qwen2.5:7b)`. This is the #1 first-run failure for a non-technical operator and right now it's a wall of Python.

3. **operator-playbooks are orphaned from the lane folders** — *path drift.* They live in `factory-build/playbooks/`, but operators are pointed at `lanes/<lane>/`. Copy each playbook into its lane folder (or add an explicit pointer in the lane README) so every operator finds their #1 onboarding doc where they're told to look.

4. **aviation + meditation have no topic-queue** — *Glitch and Jay start cold while Sam and John have 12 candidates each.* Both lanes already have Script Bibles, so run `topic_loop.py --lane aviation --n 12` and `--lane meditation --n 12`. One command per lane; everyone starts on the same line.

5. **No single linear "START HERE" runbook** — *connective-tissue gap.* The docs are excellent but scattered across `education/`, `playbooks/`, and the lane folders. Write one ordered on-ramp (read playbook → read Script Bible → teardown 1 competitor → topic_loop → pick → Trends-verify → produce) so an operator with their own Claude Code can self-serve with zero guesswork. Pair it with the README↔disk reconciliation (item B-10) so the corpus doesn't read as "half-built" on day one.
