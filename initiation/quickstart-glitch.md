---
operator: Glitch
lane: aviation
rpm_band: $7–13 (aviation/documentary)
card: quickstart v1
---

# GLITCH — AVIATION LANE QUICKSTART

**Your lane:** Air-crash investigation, told as a mystery. RPM ~$7–13. Single genre, nothing else. Stealing from MentourPilot (1.34M top-10 avg, outliers 1.7x) and GreenDotAviation (1.23M, outliers 1.9x).
**Your corpus:** `…/rt-yt-knowledge-SEED/lanes/aviation/` — read `script-bible.md`, `teardowns/mentourpilot.md`, `teardowns/greendotaviation.md`. (No topic-queue yet — generate one as your first action.)

## The core genre thesis
**A known catastrophe re-told as an unfolding mystery.** The viewer knows the plane crashed (it's in the title) but NOT why, who's at fault, or who survived. Your whole job: ration out the chain of failures so the curiosity gap stays open until the final third. This is why 24–66 min runtimes still hold APV.

## Your top 3 title formulas (quoted from your bible)
1. **The Question Hook (GreenDot signature)** — `What HAPPENED [Airline/Flight]??` (proof: *What HAPPENED Emirates 521??*, 1.57M). End on a double `??` — it signals even experts are confused.
2. **The Buried-Significance Hook (Mentour signature)** — `The Most Important Crash You've Never Heard Of... | [Flight]` / `What REALLY Happened To [Subject]?!` (proof: *What REALLY Happened To Kobe Bryant's Helicopter?!*, 1.70M — the #1).
3. **The Emotional-Stakes Hook** — `The WORST Story I've Ever Told.. | [Flight]` / `A Litany of LIES! | [Event]` (proof: *The WORST Story I've Ever Told.. | Germanwings 9525*, 1.67M). The moral framing is what licenses 44–66 min runtimes.
> Title laws: **ALWAYS include the flight identifier** (airline + number) — it's the credibility anchor. ≥1 screamed power word (HAPPENED, WORST, DARK, LIES). Withhold the *why*. Close on `??` / `..` / `!`.

## Your first 3 recommended videos (derived from your formulas — Trends-verify first)
1. **What HAPPENED to Flight 990?? | EgyptAir** (Question Hook — pilot-action mystery)
2. **The Most Important Crash You've Never Heard Of... | United 173** (Buried-Significance — fuel-starvation, huge legacy beat)
3. **A Litany of LIES! | The Tenerife Disaster** (Emotional-Stakes — the moral, runtime-justifying frame)

## Your tools
Claude Max + Claude Code (scripts) · ElevenLabs (authoritative-but-accessible, sober, empathetic VO) · **archive.org for free real aircraft/era footage** · Higgsfield / Veo 3.1 / Kling 3.0 for the jeopardy-state B-roll (banking hard, smoke, night) · Adobe Premiere + Claude · yt-dlp + local Ollama for teardowns.

## FIRST ACTION TODAY
You have no queue yet — generate it, then teardown a third competitor to widen patterns:
```
cd ~/Projects/active/rt-yt-skills
python3 topic_loop.py --lane aviation --n 12          # build your first queue
python3 teardown.py --channel @MentourPilot --lane aviation
```
Pick video #1 above, Trends-verify (US / 12mo / YouTube Search), **package title (withhold the why) + one literal thumbnail of the visceral noun FIRST.** Build the cold-open machine: crisis mid-action (0:05) → unanswerable question (0:20) → stakes/promise (0:30) → cliffhanger cut, resolve nothing. Gates: CTR ≥10%, APV ≥30%, retention flat-to-rising through 0:30.
