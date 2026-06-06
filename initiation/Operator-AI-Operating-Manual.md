---
type: operating-manual
title: Operator AI Operating Manual
project: RT YouTube Growth Arm
phase: initiation
audience: Channel Operators (Sam · John Smathers · Glitch · Jay)
date: 2026-06-06
status: v1 — initiation-ready, copy-paste live
owner: Eric Cromartie / Rising Tides
related:
  - rt-yt-knowledge-SEED (the corpus / shared brain)
  - rt-yt-skills (teardown.py, topic_loop.py)
  - rt-yt-substrate (Postgres pipeline + state machine)
  - Operator Field Manual (CTR/APV/retention reading + Intrigue Doctrine)
tags: [youtube, operator, claude-code, factory, ai-operating-loop]
---

# Operator AI Operating Manual

**This is the centerpiece. It is how YOU — the Channel Operator — point your own Claude / Claude Code at this agenda and drive a lane from zero to a monetized, winning channel with zero guesswork.**

You are not a video editor with an AI plugin. You are the **pilot of a factory**. The factory (Production) is built to be cheap and frictionless. The chess (Growth) — reading the signal and deciding what to double down on — is the one place your human judgment is irreplaceable. This manual tells you exactly which buttons to press, which prompts to paste, and where to stop pressing buttons and start thinking.

Read it once end-to-end. Then keep it open in a tab and live in §4 (the daily loop) and §2 (the prompts).

---

## 0. The two engines (orient before you touch anything)

Everything you do lands in one of two engines. Knowing which one you're in tells you whether to trust the AI or override it.

| | **PRODUCTION (the factory)** | **GROWTH (the chess)** |
|---|---|---|
| Goal | Ship a competent video cheaply | Read the signal, bet on winners |
| Mode | Frictionless, automated, cheap-by-default | Slow, deliberate, human-judged |
| AI role | Does ~90% of the work | Advises; you decide |
| Cost | Minimal until a winner proves out | Reinvest ONLY behind proven over-indexers |
| Your job | Drive the skills, run the prompts | Read CTR/APV/retention, make the double-down call |

**The doctrine in one line:** *Launch many cheap shots → read the over-index signal → double/triple down on the few winners.* The AI fires the shots. You read the signal. (See §5 — that boundary is the whole game.)

**The methodology you are executing (Scott Smith 5-step):**
niche → **topic** (4-prompt Claude→Gemini chain + Google Trends verify) → **Script Bible** → **first views** (CTR ≥10%, APV ≥30%, hook <15s, stakes by 0:30) → **monetize at YPP** (1,000 subs + 4,000 watch hours).

---

## 1. Your toolkit — the exact skills & commands, and WHEN to fire each

Two local skills do the heavy, repetitive grinding so your Claude context stays free for judgment. Both offload bulk work to **local Ollama** (free, runs on your machine). You curate the output; the machine generates it.

### Setup (one time)
```bash
# Confirm the skills are present
ls ~/Projects/active/rt-yt-skills/        # teardown.py, topic_loop.py

# Confirm local Ollama is running and has the model
ollama list | grep qwen2.5        # the default extraction model
ollama serve >/dev/null 2>&1 &    # if not already running

# Confirm yt-dlp is installed (used by teardown for captions)
yt-dlp --version

# Your corpus (the shared brain) — READ from here, it's local + complete:
export SEED="$HOME/Documents/Obsidian Vault/Rising Tides OS/Session Logs/2026-06/session-2026-06-05/yt-1mil-plan/rt-yt-knowledge-SEED"
ls "$SEED/lanes/"     # aviation history ai-dev meditation
```

### `teardown.py` — reverse-engineer a competitor channel

**WHEN:** At the start of a lane, and any time a competitor video over-indexes (pops). This is how you steal proven title + hook patterns instead of guessing. **Fire it before you write anything.**

```bash
# Standard: tear down a channel into your lane's corpus
python3 ~/Projects/active/rt-yt-skills/teardown.py --channel @VoicesofthePast --lane history

# A bigger channel, sample the top 12 outliers, pull 5 hooks
python3 ~/Projects/active/rt-yt-skills/teardown.py --channel https://www.youtube.com/@Fireship --lane ai-dev --top 12 --hooks 5

# Aviation example
python3 ~/Projects/active/rt-yt-skills/teardown.py --channel @MentourPilot --lane aviation
```

What it does: pulls the channel's recent uploads, finds the **outliers** (the videos pulling multiples of the channel average — that's where the money is), grabs captions for the top performers via the fast-path (no whisper, instant), and runs local Ollama to extract the **winning title patterns** and **hook patterns**. Writes a teardown doc into `$SEED/lanes/<lane>/teardowns/<channel>.md`.

**Your job after it runs:** open the file, sanity-check the extracted patterns (the AI is good but not infallible — see §5), and promote it. The teardown's §5 "steal list" is what feeds your Script Bible and your topic generation.

### `topic_loop.py` — generate a validated topic queue

**WHEN:** Once a Script Bible exists for your lane (it reads from it). Run it when your queue is running low — you always want 8–12 vetted candidates ahead of production so you never sit idle.

```bash
# Generate 12 fresh topics for your lane, built from its proven formulas
python3 ~/Projects/active/rt-yt-skills/topic_loop.py --lane history --n 12

# Aviation, 15 candidates
python3 ~/Projects/active/rt-yt-skills/topic_loop.py --lane aviation --n 15
```

What it does: reads your lane's `script-bible.md` + every teardown, pulls out the proven title formulas AND the competitor topics already used, then has local Ollama generate N **new** topics that fit the winning molds **without** copying competitors. Writes `$SEED/lanes/<lane>/topic-queue.md`.

**CRITICAL — these are CANDIDATES, not a green light.** The file says so in its own frontmatter: `status: candidates — operator must Trends-verify`. You verify each in Google Trends (US / past 12 months / **YouTube Search**) before producing. Kill declining, keep rising + evergreen. This Trends gate is a §5 human step — the AI does not see live search demand.

---

## 2. The prompt patterns — copy-paste-ready for every pipeline stage

These are the actual prompts you paste into **your own Claude** (the chat, not Claude Code) at each stage. They are written to be pasted verbatim — fill the `<BRACKETS>`. Each one is grounded in this lane's Script Bible and the Field Manual gates, so the AI stays on-doctrine instead of producing generic slop.

> **Setup move that 3x's every prompt below:** start each Claude session by giving it the corpus. Paste your lane's Script Bible and the relevant teardown into the chat first (or, in Claude Code, just point it at `$SEED/lanes/<lane>/`). Then run the prompt. The AI is only as good as the context you front-load.

---

### 2.1 — TOPIC RESEARCH (Scott Smith 4-prompt Claude→Gemini chain)

Use this to pressure-test and expand a candidate topic from the queue into a researched, defensible video idea. Run prompts in sequence in the same chat.

**Prompt 1 — Demand & angle:**
```
You are my YouTube topic strategist for a faceless long-form [LANE] channel.
Our proven title formulas and doctrine are in the Script Bible I pasted above.

Candidate topic: "[PASTE TOPIC FROM QUEUE]"

Do four things, tightly:
1. State the single curiosity gap this topic opens (the unanswered question that earns the click).
2. Identify the audience already searching for this and the adjacent searches they make.
3. Name 3 distinct ANGLES on this topic, ranked by curiosity-gap strength, each as a one-line title using one of our proven formulas.
4. Flag any reason this topic is a trap (too niche, decaying interest, no real specific anchor, oversaturated).
No preamble.
```

**Prompt 2 — Title candidates:**
```
Using angle #[N] above, write 8 title candidates.
Rules (from our Script Bible):
- Use a proven formula (Total-Scope Promise / Civilization+Death-Phrase / Eyewitness POV / Numbered Anthology / Surprising-Outcome).
- Each must carry at least one power word and name a SPECIFIC subject (never a vague noun).
- < 70 characters. One concrete image/metaphor per title.
Rank them by curiosity gap. Mark your single strongest pick and say why in one line.
```

**Prompt 3 — Source spine (this is what you hand to Gemini):**
```
For the winning title, give me the factual research spine I need before scripting:
- 5–8 key facts/events the video must cover, in narrative order (broad → specific human → escalation → turn → legacy).
- The named individuals or eyewitness sources I should anchor to (the lane lives on real, named humans).
- 3 surprising/counterintuitive details that would each make a strong mid-video retention beat.
- Anything commonly believed about this that's actually wrong (myth-busting = retention).
Output as a clean brief I can verify against primary sources.
```
> Then take that brief to **Gemini** (Deep Research) to fact-check and source it — Claude drafts the spine, Gemini grounds it. This is the Scott Smith hand-off. Never script from unverified facts.

**Prompt 4 — Trends gate (you, not the AI, run this):**
> Put the winning title's core noun into **Google Trends → United States → past 12 months → YouTube Search**. Rising or stable = produce. Declining = kill it and drop to the next queue candidate. The AI cannot see live demand — this gate is yours.

---

### 2.2 — PACKAGING: title + thumbnail (do this BEFORE scripting)

Packaging is researched and locked **first** — you script toward the promise, not the other way around. CTR ≥10% is a packaging metric; you can't fix bad packaging with a good script.

**Title (already chosen in 2.1). Thumbnail concept prompt:**
```
You are my thumbnail strategist for a faceless [LANE] channel. Thumbnail doctrine from our Script Bible §10:
one subject, one idea; specific iconography over generic; emotion-on-face for eyewitness titles;
cinematic low-key/mood lighting; minimal-to-no text; visually distinct from the incumbents in this cluster.

Title: "[FINAL TITLE]"

Give me:
1. The ONE idea the thumbnail must communicate (one sentence).
2. The single subject/image (specific, period-accurate — name it).
3. Lighting + mood + palette that matches our grave/documentary register.
4. The packaging-contrast move: what the top 3 competitors' thumbnails for this topic look like, and how ours is deliberately different.
5. A ready-to-use generation prompt for [Higgsfield / Veo 3.1 / Kling] to produce the image.
```

**The packaging A/B gut-check (paste your title + thumbnail concept):**
```
Here is my packaging — Title: "[TITLE]" + Thumbnail: "[1-line description]".
Score it brutally as a cold viewer scrolling the feed:
- Does the title open a gap I CAN'T answer but WANT to? (1–10)
- Does the thumbnail's one idea match the title's one promise? (1–10)
- Where do title and thumbnail say the SAME thing redundantly (waste) vs. each adding a NEW layer (good)?
- One sharper alternative title and one sharper thumbnail idea.
Be a critic, not a cheerleader.
```

---

### 2.3 — SCRIPTING (against the Script Bible, hitting the gates)

```
You are my long-form [LANE] scriptwriter. Obey our Script Bible (pasted above) exactly.

Title (the promise): "[FINAL TITLE]"
Research spine (verified): [PASTE THE GEMINI-VERIFIED BRIEF]
Target runtime: [16–22 min Battle Explainer / 25–32 min Eyewitness Anthology]

Write the script. NON-NEGOTIABLES:
- COLD OPEN (0:00–0:45) follows the four-move spine: vivid present-tense scene → narrow to ONE named human → plant the threat (stakes locked by 0:30) → slam shut on an unresolved question. Hook lands in <15s. Do NOT open on the channel ident.
- BODY: broad context → named human story → escalating conflict → turn/collapse → legacy. Re-anchor to a NEW named human or scene every 2–4 minutes. Never let abstraction run >90s without re-anchoring.
- Each chapter ends on a mini open-loop; next chapter opens the resolution + a new scene.
- TONE: grave, literary, documentary. Authority from real/named sources, intimacy from individuals. No carnival-barker clickbait register.
- CTA: no early CTA (never break the cold open). Soft mid-roll CTA after the first emotional payoff. End on a next-video tease, not a generic ask.

Output the full script with [VISUAL:] cues and [TIMESTAMP] markers per chapter.
```

**Cold-open hardening pass (run on just the open):**
```
Here is my cold open: [PASTE 0:00–0:45].
Stress-test it against our doctrine:
- Does a real hook land in the first <15 seconds, or is there throat-clearing to cut?
- Is there a SPECIFIC named human by ~0:15?
- Are the stakes unmistakable by 0:30?
- Does it END on an unresolved question (open loop), not an answer?
Rewrite it tighter, keeping the strongest single line. Then give me the one line a viewer would rewind for.
```

---

### 2.4 — RETENTION ANALYSIS (after the video has data)

This is where Production hands off to Growth. Pull your CTR / APV / the retention (audience-retention) graph from YouTube Studio, then:

```
You are my retention analyst (read the Operator Field Manual rules). Here is the data for "[TITLE]":
- CTR: [X]%   (gate: ≥10%)
- APV (avg % viewed): [X]%   (gate: ≥30%)
- Avg view duration: [M:SS] of [total runtime]
- Retention graph notable points: [describe dips/spikes by timestamp, e.g. "sharp drop at 0:35", "spike at 4:10", "cliff at 9:00"]

Diagnose:
1. Is the problem PACKAGING (low CTR) or CONTENT (low APV)? Name which engine to fix.
2. For each retention DIP, the likely cause (slow open, abstraction ran too long, weak transition, broken promise) and the specific fix from our Script Bible.
3. For each retention SPIKE, what worked — so I can do MORE of it. (Spikes are gold; they tell me what to double down on.)
4. The single highest-leverage change for the next video in this cluster.
Concrete, timestamp-specific, no hand-waving.
```

> **Read the Field Manual gates literally:** CTR <10% = packaging problem (fix title/thumbnail, the script is downstream). APV <30% = retention problem (fix the open and the pacing). A 0:35 cliff almost always means the cold-open open-loop didn't hold — that's a §3 Script Bible failure.

---

### 2.5 — THE DOUBLE-DOWN DECISION (Growth chess — AI advises, YOU decide)

When a video over-indexes (clears both gates, ideally pulls multiples of your channel average), the AI helps you map the bet — but the call is yours (§5).

```
This video over-indexed: "[TITLE]" — CTR [X]%, APV [X]%, [N]x my channel average.
You are my Growth strategist. Help me map the double-down (I make the final call):
1. Decompose WHY it won: which formula, which thumbnail move, which topic vein, which audience.
2. Give me 5 adjacent topics that share the winning DNA but aren't repeats — the "more of this" vein to mine.
3. Should I go DEEPER (longer runtime / series on this exact topic) or WIDER (more topics in this vein)? Argue both, then recommend.
4. What to STOP doing — which of my recent non-performers should I kill to reallocate effort here?
5. Draft the winner-log entry so the whole portfolio learns from this.
```

Then file the winner-log entry to the corpus so every other operator's Claude inherits the lesson:
```bash
# Winner-log template lives in the corpus
cp "$SEED/_templates/winner-log-entry.md" "$SEED/winner-log/$(date +%Y-%m-%d)-<lane>-<slug>.md"
# fill it in, commit/PR to ecfromthedc/rt-yt-knowledge
```

---

## 3. Driving the local skills + reading the corpus through Claude Code

Claude Code is your hands on the factory floor — it runs the skills, reads the corpus, and edits files. Use the chat (§2) for thinking; use Claude Code for doing.

**Point Claude Code at the corpus and skills (paste at session start):**
```
Read these so you have full context on my lane:
- $SEED/lanes/[LANE]/script-bible.md  (my winning template)
- $SEED/lanes/[LANE]/teardowns/*.md   (competitor patterns I'm stealing)
- $SEED/lanes/[LANE]/topic-queue.md   (my current candidate queue)
- $SEED/education/                     (Factory Operating Guide, Reverse-Engineering Workshop)
Then summarize my lane's top 3 title formulas and the cold-open spine back to me so I know you've got it.
```
(`$SEED` = `~/Documents/Obsidian Vault/Rising Tides OS/Session Logs/2026-06/session-2026-06-05/yt-1mil-plan/rt-yt-knowledge-SEED`)

**Have Claude Code run the skills for you (natural language → command):**
```
Run a teardown on @GreenDotAviation into the aviation lane, top 12, then read me the
title patterns and the steal list from the file it produces.
```
```
My topic queue is thin. Regenerate 15 history topics, then for each one give me the exact
Google Trends URL (US, 12mo, YouTube Search) so I can verify them fast.
```

**Query the corpus instead of guessing:**
```
Across ALL lanes in $SEED, which title formula shows up in the most over-indexing teardown
videos? I want to know what's working portfolio-wide, not just my lane.
```
```
Compare my last 3 shipped scripts against the script-bible cold-open spine. Where did I
drift off-doctrine? Quote the exact lines that broke a rule.
```

**Keep the corpus fed (this is how compounding happens):**
After every teardown and every winner, Claude Code commits it back. One operator's teardown becomes every operator's edge — the corpus is the shared brain. Don't hoard learnings in your head; push them to `ecfromthedc/rt-yt-knowledge`.

---

## 4. The operating loop — daily + weekly

### Daily (Production cadence — keep the factory humming)
1. **Pull the queue.** Open `$SEED/lanes/<lane>/topic-queue.md`. If <6 vetted topics remain, run `topic_loop.py` (§1) and Trends-verify the new batch (§2.1 Prompt 4).
2. **Lock packaging FIRST.** Take the next verified topic. Run §2.1 (title) → §2.2 (thumbnail) → the A/B gut-check. Do not write a word of script until title + thumbnail are locked.
3. **Script it.** Run §2.3 against the Script Bible. Run the cold-open hardening pass. Verify facts came through Gemini, not Claude's memory.
4. **Produce cheap-by-default.** VO via ElevenLabs; footage from archive.org (free, real) first, AI (Higgsfield/Veo/Kling) only where archive can't cover it; assemble in Premiere (+ Claude integration). **Do NOT over-invest** — this is an unproven shot. Cheap until it proves.
5. **Ship.** Upload with the locked packaging. Log it in the substrate pipeline (stage 09-Publish → it advances through the stored state machine).
6. **Read yesterday's shippers.** Pull CTR/APV/retention on anything with ≥48h of data. Run §2.4. File the diagnosis.

> The loop is: **research → package → script → produce → ship → read → (double-down).** Production runs this every day. Growth only fires on the "read" step when a signal appears.

### Weekly (Growth cadence — play the chess)
1. **Portfolio read.** Across all your channels/videos, rank by CTR×APV and by multiple-of-average. The over-indexers reveal themselves.
2. **The double-down call.** For each over-indexer, run §2.5. Decide deeper vs. wider. **This is the only place real money gets spent** — reinvest production budget (better footage, longer runtime, a series) ONLY behind a proven winner.
3. **Kill the losers.** Anything that's failed the gates across multiple shots in a vein → stop mining that vein. Reallocate to the winning one.
4. **Feed the corpus.** File winner-log entries (§2.5). Run a fresh teardown (§1) on any competitor who popped this week. Push to `rt-yt-knowledge`.
5. **Re-tune the Script Bible.** After your first 3 shipped videos in any cluster, replace the Bible's *prescriptions* with your *measured* CTR/APV reality (the Bible §11 says to do exactly this). The corpus gets smarter every week.

---

## 5. Where human judgment MUST override the AI (the chess)

The AI runs the factory. **You** run the chess. These five calls are yours — the AI advises, you decide. Getting this boundary right is the difference between a content farm that drowns in mediocre uploads and a portfolio that compounds into $1M.

1. **The signal read.** The AI can describe a retention graph; it cannot *feel* why a specific spike happened or sense that a "failing" video is actually one tweak from breaking out. Reading the over-index signal — separating noise from a real vein — is taste. The numbers inform you; they don't decide for you.

2. **The double-down call.** Deeper vs. wider, invest vs. kill, which winner gets the series treatment — this is capital allocation under uncertainty. The AI will give you a confident-sounding recommendation for *both* sides. The judgment of which bet to actually fund is the single highest-leverage decision you make, and it's 100% human.

3. **Taste on packaging.** The AI generates 8 titles and a thumbnail concept. Whether a title actually makes a real human *need* to click — that "this is irresistible" gut-feel — is yours. The Intrigue Doctrine in the Field Manual is a sensibility, not a formula. When the AI's "best" title leaves you cold, trust yourself and override.

4. **The Trends / live-demand gate.** The AI cannot see Google Trends or live YouTube search demand. A topic that fits every formula perfectly but is *decaying in interest* is a trap the AI will happily walk you into. You run the Trends check, every time, before producing. No exceptions.

5. **Fact integrity & brand register.** The AI will confidently state history that's subtly wrong (it's why the Gemini fact-check step exists) and will occasionally drift toward clickbait register the lane's decoy channel proved is fatal. You are the editor of record: verify the facts came through Gemini, and protect the grave/documentary tone. A factual error or a tonal misfire on a winning video is a self-inflicted wound.

**The rule of thumb:** if a decision spends money, sets the brand, or bets the lane's direction — that's the chess, and you move the piece. If it's generating, drafting, extracting, or grinding — that's the factory, and the AI plays it. When in doubt about which engine you're in, you're probably in the chess. Slow down and think.

---

> **You now have everything.** The skills fire the shots (§1). The prompts run the pipeline (§2). Claude Code drives the floor and the corpus (§3). The loop keeps it all moving (§4). And §5 is where you earn your revenue share — the judgment no model can replace. Open the queue and ship your first three.
