---
operator: John Smathers
lane: ai-dev
rpm_band: $10–18 (tech/AI — highest RPM band in the factory)
card: quickstart v1
---

# JOHN SMATHERS — AI-DEV LANE QUICKSTART

**Your lane:** AI/dev news + breakthroughs. **RPM $10–18 — the richest band we run**, so a moderate-view AI channel out-earns a big history channel. Stealing from Fireship (1.37M top-10 avg) and Two Minute Papers (181K).
**Your corpus:** `…/rt-yt-knowledge-SEED/lanes/ai-dev/` — read `script-bible.md`, `teardowns/fireship.md`, `teardowns/twominutepapers.md`, `topic-queue.md`.

## Decide the archetype FIRST (never blend)
- **News-Reactor (Fireship):** 4–7 min, fast/sardonic/ironic. Trigger = *something that just happened* (leak, launch, outage). Ship the day the news breaks.
- **Breakthrough-Narrator (2MP):** 7–11 min, awe-driven. Trigger = *a capability that now exists.* Rising staircase of "wait, it gets better."
> Rule: just happened → News-Reactor. Now exists → Breakthrough-Narrator.

## Your top 3 title formulas (quoted from your bible)
1. **The "Tragic mistake" frame** — `<Emotional verdict>... <Company> <dramatic action>` (proof: *"Tragic mistake... Anthropic leaks Claude's source code"*, 3.21M, 3.5x — the channel's #1). Lead with the judgment, not the fact.
2. **The "casually disrupted" frame** — `<Company> just casually <disrupted X>…` (proof: *"Google just casually disrupted the open-source AI narrative…"*). The word **casually** does the work.
3. **The "…For Free" / "Game Changer" frame** — `<Underdog> Beats <Expensive incumbent>…For Free` / `<Company>'s New AI Is A Game Changer` (proof: *"DeepSeek's New AI Is A Game Changer"*, 2.8x). The `…For Free` tag is what top titles do that lower ones don't.
> Title laws: **name a recognizable proper noun** (no generic "this AI tool"), lead with an emotional verdict, end on a trailing `…` to open the loop, put the twist after the ellipsis ("…by cheating"). Stakes live by 0:15.

## Your first 3 recommended videos (from topic-queue — Trends-verify first)
1. **Google's New AI Just Broke My Brain** (Breakthrough-Narrator — awe staircase)
2. **DeepSeek V5 AI Just Broke Through Limitations... For Free** (the "…For Free" mold — your strongest)
3. **Claude Just Launched A New Feature That Will Change Everything** (News-Reactor — ship the day it breaks)

## Your tools
Claude Max + Claude Code (this is your home turf — script + ship fast) · ElevenLabs VO (deadpan for News-Reactor, earnest-wonder for Breakthrough) · Higgsfield / Veo 3.1 / Kling 3.0 for demo B-roll · Adobe Premiere + Claude for hyper-cut density · yt-dlp + local Ollama for teardowns.

## FIRST ACTION TODAY
Refresh your edge on the highest-RPM lane — re-teardown your two anchors, regenerate the queue, then ship a News-Reactor on whatever AI news broke today (recency is your moat):
```
cd ~/Projects/active/rt-yt-skills
python3 teardown.py --channel @Fireship --lane ai-dev
python3 topic_loop.py --lane ai-dev --n 12
```
Pick the freshest real news event, Trends-verify (US / 12mo / YouTube Search), **package title (verdict + `…`) + thumbnail (one logo + one idea) FIRST.** Gates: CTR ≥10%, APV ≥30%, stakes by 0:15, one archetype top-to-bottom.
