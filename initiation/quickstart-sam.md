---
operator: Sam
lane: history
rpm_band: $4–8 (history/documentary)
card: quickstart v1
---

# SAM — HISTORY LANE QUICKSTART

**Your lane:** Long-form history, told as a civilization obituary or eyewitness anthology. RPM band ~$4–8. You're stealing from three live winners: Fall of Civilizations (12.4M top-10 avg), Voices of the Past (2.4M), Kings & Generals (158K).
**Your corpus:** `…/rt-yt-knowledge-SEED/lanes/history/` — read `script-bible.md` (the doctrine), `teardowns/`, `topic-queue.md`. **RT default build:** Eyewitness-Anthology framing on Battle-Explainer economics (16–25 min). Don't start at 238-min Epic Obituary length — earn it.

## The load-bearing wall (memorize)
Every cold open does 4 moves in order: **broad setting → narrow to one human → plant the threat (stakes by 0:30) → slam shut on a question.** Never open on the channel ident. Re-anchor to a person/scene every 2–4 min or retention dies.

## Your top 3 title formulas (quoted from your bible)
1. **Total-Scope Promise** — `The Entire History of <Specific Civilization/Place>` (proof: *The Entire History of Ancient Japan*, 6.6M, 5.4x). Use the *specific* noun, never the vague one.
2. **Civilization + Evocative Death Phrase** — `<Civilization> - <Poetic Fall Phrase>` (proof: *The Sumerians - Fall of the First Cities*, 39M, 6.2x). One concrete metaphor image per title ("Empire of Iron").
3. **Eyewitness POV** — `Real <Occupation> Describes Real Life in <Period/Place>` (proof: *Mediocre Samurai Describes Real Life in Historical Japan*, 2.6M). The word **"Real"** is the whole moat; lead with a tonal adjective ("Confused," "Terrified").
> Power-word bank — bake ≥1 per title: **First / Fall / Last / Real / Entire / Empire / Strangest / Worst.** Avoid the decoy trap: no curiosity gap without a real, specific historical anchor.

## Your first 3 recommended videos (from topic-queue — Trends-verify first)
1. **The Forgotten Empire of Kush - Rise and Fall of Gold Mines** (Death-Phrase mold)
2. **Real Roman Legate Describes Life in the Early Empire** (Eyewitness POV — your bible's #1 mold)
3. **5 Terrifying Accounts of First Contact Between Cultures** (Numbered Anthology — the most repeatable factory mold)

## Your tools
Claude Max + Claude Code (scripts) · ElevenLabs (grave, measured, low-energy VO) · **archive.org for free real period footage** · Higgsfield (Veo 3.1 / Kling 3.0 fallback) for B-roll · Adobe Premiere + Claude · yt-dlp + local Ollama for teardowns.

## FIRST ACTION TODAY
Run a teardown on a 4th competitor to widen your pattern base, then regenerate your queue and Trends-verify your top pick:
```
cd ~/Projects/active/rt-yt-skills
python3 teardown.py --channel @FallofCivilizations --lane history   # confirm/extend patterns
python3 topic_loop.py --lane history --n 12                          # fresh candidates
```
Then take video #2 above, Trends-verify (US / 12mo / YouTube Search), and **package title + thumbnail FIRST** before writing a line of script. Gates to clear: CTR ≥10%, APV ≥30%, hook <15s, stakes by 0:30.
