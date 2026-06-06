---
type: start-here
audience: every new Channel Operator (Sam, John, Glitch, Jay, + future)
purpose: the one ordered on-ramp — read this first, follow it top to bottom
---

# START HERE — RT YouTube Operator On-Ramp

You're being initiated into the RT YouTube Growth Arm: a portfolio of faceless long-form channels aimed at a **$1M annualized run-rate by June 2027.** Your job is to run a lane, ship 2 videos/week, read the signal, and double down on winners. You own **~20% of your channels' upside.** This is the whole path, in order — no guessing.

## 0. One-time setup (Day 0) — ~20 min
Follow **`Onboarding-Runbook.md`** §Day-0. In short:
1. Clone the 3 repos: `rt-yt-knowledge` (corpus), `rt-yt-substrate` (skills), `youtube-growth-playbook` (method).
2. Install: `yt-dlp`, `ffmpeg`, `ollama` (+ `ollama pull qwen2.5:7b`), Python 3.
3. Drop **`CLAUDE-youtube-agenda.md`** into your working folder as `CLAUDE.md` so *your* Claude/Claude Code is primed on this agenda.
4. Verify the skills run: `python3 rt-yt-substrate/skills/python/teardown.py --channel @Fireship --lane ai-dev`

## 1. Learn your lane (Day 1, morning)
- Read **your quickstart card**: `quickstart-<yourname>.md` (Sam=history, John=ai-dev, Glitch=aviation, Jay=meditation/distribution).
- Read your lane's **`lanes/<lane>/script-bible.md`** (the winning-script doctrine) and skim the **`teardowns/`**.
- Read the **Operator Field Manual** + **`Operator-AI-Operating-Manual.md`** (how to drive your Claude through the work).

## 2. Pick a topic (Day 1, midday)
- Open **`lanes/<lane>/topic-queue.md`** (every lane has one). Or generate fresh: `python3 topic_loop.py --lane <lane> --n 12`.
- Pick your top candidate → **Google Trends verify** (US / past 12mo / YouTube Search). Rising/evergreen = keep. Declining = kill.
- Considering a whole new sub-niche? Run `python3 niche_validate.py --niche "<idea>" --lane <lane>` first.

## 3. Package FIRST (Day 1, afternoon)
Before any script: write 3 title candidates (use your bible's proven formulas) + spec the thumbnail (one idea, max contrast). If you can't make a clickable promise, the topic's wrong — find out now. Gate: would it make *you* stop scrolling? (target CTR ≥10%).

## 4. Script → produce → ship (Day 1–3)
Follow your **`operator-playbook.md`** + the AI Operating Manual prompt patterns. Hook in first 15s, stakes by 0:30, target APV ≥30%. Cheap-default production (archive.org real footage / Veo-Kling B-roll, ElevenLabs VO, Premiere+Claude). Ship.

## 5. Read + double down (ongoing)
48h + 7d: pull CTR/APV, find your quadrant (Field Manual diagnostic grid), execute the fix. **If a video over-indexes — especially on a new channel — drop everything and make 2–3 more in that cluster this week.** That's the chess. That's where the money is.

---
**The chain you now have:** quickstart → script-bible → playbook → topic-queue → ship → read → double down. Everything's in `rt-yt-knowledge`. Your Claude is primed. Go run your lane.
