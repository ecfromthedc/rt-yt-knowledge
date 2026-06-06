---
type: operator-playbook
lane: ai-dev
operator: John Smathers
status: active build
date: 2026-06-06
rpm_band: $10-18
target: $1M annualized run-rate by June 2027 (RT YouTube Growth Arm)
sources:
  - lanes/ai-dev/teardowns/fireship.md (@Fireship, 25 vids, ch avg 928K, top-10 avg 1.37M, 3.5x outlier)
  - lanes/ai-dev/teardowns/twominutepapers.md (@TwoMinutePapers, 25 vids, ch avg 109K, top-10 avg 181K, 2.8x outlier)
  - lanes/ai-dev/script-bible.md
  - Operator Field Manual (CTR ≥10%, APV ≥30%, Intrigue Doctrine)
tags: [youtube, ai-dev, operator-playbook, faceless, rt-yt-arm]
---

# AI-Dev Lane — Operator Playbook

**This is the "how to run the lane" doc. John, this is your standing operating procedure.** The Script Bible tells you how to *write*; this tells you how to *run the machine* week over week. The strategy is non-negotiable: **reverse-engineer proven winners, ship cheap by default, and only spend real money on videos the data already validated.**

The lane has two validated archetypes (decide per video, never blend):
- **News-Reactor** (Fireship model) — 4-7 min, reacts to a news event, 3.5x power-law outliers. This is your **primary volume engine** — it's how you ship fast and hit YPP quickly.
- **Breakthrough-Narrator** (Two Minute Papers model) — 7-11 min, explains a new capability, 2.8x slower-burn outliers, more evergreen. This is your **compounding asset engine** — slower to make, longer to pull views.

RPM band is **$10-18** — the highest of all four RT lanes. That means each validated winner here is worth roughly 1.5-2.5x a history or aviation video at equal views. **The math rewards getting one News-Reactor outlier and then milking it.**

---

## 1. The weekly workflow (research → package → script → produce → ship → read → double-down)

Run this as a repeating loop. The faceless model means one operator can sustain **3-5 News-Reactor videos/week + 1 Breakthrough-Narrator/week** once the pipeline is warm. Front-load research, batch produce, ship daily on news.

### Monday — RESEARCH (90 min, batched)
- **Scan the news feed for live events.** Sources: Hacker News front page, r/LocalLLaMA, r/singularity, the @Fireship / @TwoMinutePapers / @AIExplained upload feeds (watch what THEY react to — they pre-validate the topic), X/Twitter AI accounts, and the official blogs (Anthropic, Google DeepMind, OpenAI, NVIDIA, Hugging Face trending).
- **The validation filter:** a topic is worth a video only if it (a) names a **recognizable proper noun** (Anthropic, Google, NVIDIA, DeepSeek, GitHub, Claude — never a no-name tool), and (b) has an **emotional verdict** available (a leak, an outage, a disruption, a "for free" upset, a cheat/contradiction). If you can't write a Fireship-style title in one line, kill the topic.
- **Maintain a rolling 10-topic backlog** in a simple `topic-queue.md`. Tag each `news-reactor` or `breakthrough-narrator`. News-Reactor topics expire fast (ship within 24-48h of the event); Breakthrough topics keep.

### Tuesday — PACKAGE (title + thumbnail FIRST, before any script)
- **Package before you produce. Always.** The packaging is the asset; the video services the packaging. This is the single biggest leverage point in the whole lane.
- Write **3-5 title candidates** per video using the validated formulas in §2. Every title: one recognizable entity, one emotional verdict, trailing `…` or post-dash twist, one idea.
- Spec **the thumbnail as one idea**: one recognizable logo/face + one emotional concept + ≤3 words of overlay. (Thumbnail recipes in §4.)
- **Gut-check against the Field Manual CTR bar (≥10%).** If the title/thumb pair wouldn't make YOU stop scrolling past Fireship, it's not done.

### Wednesday — SCRIPT (use the Script Bible skeleton)
- Open `script-bible.md` §8 and fill the skeleton for the committed archetype.
- News-Reactor: shock sentence → context snap → open loop by 0:12 → 4-8 escalating beats → verdict + forward jab. ≤7 min, joke/30s, irony register.
- Breakthrough-Narrator: intriguing development → challenge question → establish the problem → rising staircase of demos → close on implication. 7-11 min, awe register.
- **Hook is law:** stakes live by 0:15, fully framed by 0:30 (Intrigue Doctrine). No intro, no "hey guys."
- Run the §9 Script Bible verification checklist before it goes to voice.

### Thursday — PRODUCE (cheap-default pipeline, §3)
- TTS voiceover → caption-paced B-roll/screen-recording/code-on-screen → cut to density. Batch 2-3 News-Reactors in one production session to amortize setup.

### Friday — SHIP + READ
- **Ship News-Reactors the day the news is hot — don't hold for Friday if Tuesday's event is live.** The calendar is a default, not a cage; recency is the RPM driver for this archetype.
- Upload with the validated package, end-screen looping to the next video, pinned comment posing the open-loop question.
- **READ the retention + CTR data on everything 48-72h old.** Pull from YT Studio: impressions CTR (target ≥10%), average percentage viewed / APV (target ≥30%), and the retention graph — find the drop-off cliffs and the swell-back moments.

### Weekend — DOUBLE-DOWN (the whole game)
- **The power law is live on this lane** (top videos pull 2.8-3.5x channel average). Your job is not to make every video good — it's to **find the outlier and feed it.**
- When a video clears ~1.5x your channel average: clone its title formula, its thumbnail composition, and its topic cluster into the next 2-3 videos. Make the sequel, the "part 2," the adjacent company's version of the same story.
- When a video underperforms: kill that title pattern, do NOT reshoot, move on. Cheap-by-default means a miss costs you a few hours, not a budget.
- **Only after a video is a proven winner** do you reinvest: a better thumbnail A/B, a custom-animated explainer segment, a higher-effort sequel. Production spend follows validation, never precedes it.

---

## 2. Validated title formulas to clone (with examples)

These are extracted verbatim from the teardowns — they are proven, not theoretical. Treat them as fill-in-the-blank templates. **Every title obeys the 5 title laws: (1) name a recognizable proper noun, (2) lead with an emotional verdict not the neutral fact, (3) end on `…` to open the loop, (4) put the twist after the ellipsis/dash, (5) one idea per title.**

### News-Reactor formulas (Fireship — the volume + recency engine)

| Formula | Validated example | Views / multiple |
|---|---|---|
| `<Emotional verdict>... <Company> <dramatic action>` | "Tragic mistake... Anthropic leaks Claude's source code" | 3.21M / **3.5x** (biggest outlier on channel) |
| `<Company> just casually <disrupted X>…` | "Google just casually disrupted the open-source AI narrative…" | 1.34M / 1.4x |
| `<Company> just changed the future of <domain>…` | "Google just changed the future of UI/UX design…" | 1.86M / 2.0x |
| `He just crawled through hell to <fix X>…` (personify a faceless eng story) | "He just crawled through hell to fix the browser…" | 1.26M / 1.4x |
| `<Subject> is too dangerous for <public/release>…` (forbidden-knowledge) | "Claude Mythos is too dangerous for public consumption…" | 1.08M / 1.2x |
| `<Company>'s AI endgame is here… everything you missed at <event>` (doom + FOMO recap) | "Google's AI endgame is here…" | 1.02M / 1.1x |
| `This new <thing> is breaking the law, by design…` | "This new Linux distro is breaking the law, by design…" | 914K / 1.0x |

**The single highest-leverage move:** lead with the *judgment* before the *fact*. The teardown's own A/B proof — "Tragic mistake..." (3.5x) crushed "GitHub is having some major issues" (1.1x). Same kind of event, the emotional verdict is what 3x'd the views.

### Breakthrough-Narrator formulas (Two Minute Papers — the compounding asset engine)

| Formula | Validated example | Views / multiple |
|---|---|---|
| `<Company>'s New AI Is A Game Changer` | "DeepSeek's New AI Is A Game Changer" | 310K / **2.8x** |
| `<Company>'s New AI Just Changed <X> Forever` | "DeepMind's New AI Just Changed Science Forever" | 244K / 2.2x |
| `<Underdog> Beats <Expensive incumbent>…For Free` (the **…For Free** tag is the named edge) | "DeepSeek V4 AI Beats Billion Dollar Systems…For Free" | 189K / 1.7x |
| `<Company>'s New AI Just Broke My Brain` (first-person astonishment) | "Google's New AI Just Broke My Brain" | 168K / 1.5x |
| `<Company>'s New AI Solves Problems…By Cheating` (twist-after-ellipsis) | "Anthropic's New AI Solves Problems…By Cheating" | 165K / 1.5x |
| `<Company>'s New AI: A Gift To Humanity` (grandiose stakes) | "DeepMind's New AI: A Gift To Humanity" | 144K / 1.3x |

**Near-mandatory pattern:** the possessive + "New AI" construction (`DeepSeek's New AI…`). It's in nearly every winner. The twist after the ellipsis (`…For Free`, `…By Cheating`) is the curiosity engine — the setup is mundane, the tag reverses expectation.

**Power-word bank (use verbatim or as a thesaurus):** tragic mistake · just changed · just disrupted · casually disrupted · crawled through hell · too dangerous · endgame · major issues · breaking the law · game changer · changed [X] forever · beats billion dollar systems · broke my brain · by cheating · a gift to humanity · for free.

---

## 3. Hook doctrine for THIS niche

The Field Manual mandates stakes by 0:30 and hook < 15s. In ai-dev, the winners land it inside the **first 1-2 sentences.** Pick the cold-open by archetype.

### News-Reactor cold-open (3-beat)
1. **0:00–0:05 — Shock sentence.** Open mid-explosion on the surprising event, flat and declarative. "Anthropic just leaked its own source code." No setup, no greeting.
2. **0:05–0:12 — Context snap.** Two compressed sentences: who did it, why it matters. Just enough to make the shock legible.
3. **0:12–0:15 — Open loop.** "…but here's where it gets worse / stupid / dangerous." Tease the consequence you'll pay off.

Open-loop levers (from the teardown): highlight the **irony/contradiction** ("the richest company on earth just did the dumbest thing"), pose a **question about the implications**, or **emphasize impact on a specific group/industry** (devs, indie hackers, the open-source community).

### Breakthrough-Narrator cold-open (3-beat)
1. **0:00–0:05 — Intriguing development.** Introduce the new capability in sentence one. "An AI just wrote — and passed peer review on — its own research paper."
2. **0:05–0:15 — Challenge question.** Pose a question that challenges what the viewer assumes is possible — the teardown's literal examples: *"How can an AI write research papers?" / "What makes DeepSeek 4 unique?"*
3. **0:15+ — Rhythm lock.** Lock a fast, escalating cadence so the question's pull doesn't sag before the first demo.

### Hook anti-patterns (never, in either archetype)
Channel intro · self-introduction · "before we start, smash like" · slow throat-clearing · defining the topic academically. Stakes must be live by 0:15. The lane's audience has Fireship-grade impatience — a 10-second ramp loses them.

---

## 4. Cheap-default production approach + tools

**Doctrine: faceless, fast, cheap. The production exists to service the package. Spend hours on the title/thumbnail, minutes per minute of finished video. Reinvest only into proven winners.**

### The default stack (cheap by design)
- **Script:** Claude / local LLM drafts against the Script Bible skeleton; operator edits for voice, density, and the §9 checklist. (Per RT doctrine, offload bulk drafting/variation to local Ollama — `llama3.1:8b` — and reserve Claude for the hook and the package.)
- **Voiceover (faceless):** TTS — ElevenLabs (best quality, pay-per-char) for the published default, or a local/cheaper TTS for drafts and B-roll timing. One consistent voice = channel identity. (RT already runs ElevenLabs in the Remotion pipeline.)
- **Visuals:**
  - *News-Reactor:* screen-recordings of the actual news (the leaked repo, the blog post, the X thread, the GitHub issue), logos, code-on-screen, fast B-roll churn — a **visual change on nearly every sentence**. Hyper-cut. This is Fireship's whole look and it's cheap: it's mostly screenshots and screen-recordings, not animation.
  - *Breakthrough-Narrator:* the model's own demo footage / paper figures / result GIFs (the "just look at this" frames), shown as a rising staircase. The footage IS the product — let the impressive result carry it.
- **Editing/render:** CapCut or DaVinci Resolve (free) for cutting; or **Remotion** (RT already has the `remotion-ads` skill + ElevenLabs word-level captions pipeline) for templated, code-driven segments and captions — this is the cheapest path to consistent, batchable output once a template exists.
- **Captions:** burned-in, word-by-word, opus-style — non-negotiable for retention. RT's existing caption pipeline covers this.
- **Thumbnails:** Canva (RT has the Canva MCP) or Figma. One recognizable logo/face + one emotional idea + ≤3 words. Build a reusable template per archetype so each thumb is 10 minutes, not an hour.

### Thumbnail recipes (one idea per thumb)
- **News-Reactor:** high-contrast, slightly chaotic. One recognizable logo + a 1-3 word screaming overlay or an emoji/expression telegraphing the irony (a leak = exposed code / red alert; an outage = a broken/error frame).
- **Breakthrough-Narrator:** the single most impressive result frame (the "just look at this" moment) + an awed expression. Show the payoff, not the process.
- **The named edge (both teardown steal-lists):** copy competitors' title formulas but **beat them on packaging contrast + upload cadence.** Your thumbnail must out-contrast theirs in the feed — bolder color, clearer single idea, bigger recognizable entity.

### Batching for sustainable volume
Produce 2-3 News-Reactors in one session (shared voice setup, shared template, shared render queue). A News-Reactor at ≤7 min with screenshot-driven visuals is a **half-day of work**; that's what makes 3-5/week feasible solo.

---

## 5. YPP-fast strategy (hit monetization, then hit the RPM)

YPP requires **1,000 subscribers + 4,000 watch-hours** (or 10M Shorts views) in 12 months. In this lane, News-Reactor is the YPP accelerator and Breakthrough-Narrator is the watch-hours bank.

1. **Lead with News-Reactor volume for subscribers.** The 4-7 min recency-driven format is what spikes impressions and CTR. Ship 3-5/week. Each outlier (and the power law guarantees you'll hit one) brings a sub surge. Volume + recency = fastest path to 1,000 subs.
2. **Use Breakthrough-Narrator to bank watch-hours.** A 7-11 min video at 30%+ APV banks far more watch-time per view than a 4-min reaction. Run ~1/week as the watch-hour engine while News-Reactors drive subs. The math: ten 9-min videos at 30% APV ≈ 27 view-minutes each — these are your watch-hour workhorses.
3. **Chase pre-validated topics only.** Watch what Fireship/2MP/AI Explained react to and ship YOUR angle within 24-48h. Riding a topic the giants already validated means you inherit search/suggest traffic — the cheapest watch-hours on the platform. (Steal the topic and the formula; beat them on packaging contrast + cadence, per the steal-list.)
4. **Loop the audience to compound watch-time.** End-screens point to the next video; pinned comment poses the open-loop question; series/playlists ("everything Anthropic shipped this week") keep sessions long — YouTube rewards session watch-time, which compounds toward both YPP thresholds.
5. **Don't spend until YPP clears.** Pure cheap-default until monetized. After YPP, the $10-18 RPM kicks in — *then* reinvest into the proven winners (better thumbs, sequels, custom segments). Money follows validation.
6. **Protect the CTR/APV bars the whole way.** YPP-fast still means Field-Manual-clean: CTR ≥10%, APV ≥30%. A fast-but-weak video that tanks CTR poisons your impressions for the next upload. Speed never overrides the package.

---

## 6. Five concrete first-video ideas (winning patterns applied)

Each uses a validated formula, a committed archetype, and a hook. Swap the proper noun for whatever's live the week you ship — the *structure* is the asset, the topic is interchangeable.

### Idea 1 — News-Reactor
- **Title:** "Tragic mistake… OpenAI just leaked its own system prompt"
- **Formula:** `<Emotional verdict>... <Company> <dramatic action>` (the 3.5x outlier formula — lead with the verdict)
- **Hook:** *"OpenAI just published its own secret system prompt — by accident. And what's inside is worse than you think."* → context snap → "…but here's where it gets stupid."
- **Why it wins:** recognizable entity + leak (the single biggest proven driver), exact clone of the channel's top-performing title structure.

### Idea 2 — Breakthrough-Narrator
- **Title:** "DeepSeek's New AI Beats Billion Dollar Systems…For Free"
- **Formula:** `<Underdog> Beats <Expensive incumbent>…For Free` (the teardown-flagged "…For Free" edge, 1.7x validated)
- **Hook:** *"A free, open-weight model just beat systems that cost a billion dollars to train. How is that even possible?"* (challenge question) → establish the problem → rising staircase of benchmark demos → "A Gift To Humanity" close.
- **Why it wins:** underdog-beats-giant + the proven "For Free" curiosity tag; evergreen watch-hour banker.

### Idea 3 — News-Reactor
- **Title:** "Google just casually disrupted the entire AI coding industry…"
- **Formula:** `<Company> just casually <disrupted X>…` ("casually" does the work — giant did something world-changing as an afterthought)
- **Hook:** *"Google dropped a free coding model on a random Tuesday and quietly torched three startups. Nobody's talking about it. Yet."* → "…and it gets worse for the paid tools."
- **Why it wins:** the "casually" disruptor frame (1.4x proven) + irony register punching up at a giant; topic stays fresh on any major model drop.

### Idea 4 — Breakthrough-Narrator
- **Title:** "Anthropic's New AI Solves Problems…By Cheating"
- **Formula:** `<Company>'s New AI Solves Problems…By Cheating` (twist-after-ellipsis contradiction engine, 1.5x validated)
- **Hook:** *"Anthropic's newest model just solved a benchmark nobody could crack. Then researchers looked closer — and realized it cheated. How?"* (challenge question) → walk the reward-hacking story as an escalating staircase → implication close on AI alignment.
- **Why it wins:** the contradiction/twist is the curiosity engine; alignment/safety angle is evergreen and high-RPM (advertiser-friendly AI-research audience).

### Idea 5 — News-Reactor
- **Title:** "He just crawled through hell to fix the AI nobody could fix…"
- **Formula:** `He just crawled through hell to <fix X>…` (personifies a faceless eng story into a human ordeal, 1.4x validated)
- **Hook:** *"One developer spent 72 hours and 4,000 lines of code untangling the bug that broke half the internet's AI apps. This is what he found."* → "…and the cause was insane."
- **Why it wins:** the human-ordeal frame turns a dry postmortem into a story; maps to any major outage/postmortem week (great for riding a live incident).

---

## 7. Pre-ship checklist (run on every video)

- [ ] **Topic validated:** recognizable proper noun + available emotional verdict. Not a generic "this AI tool."
- [ ] **Archetype committed** top-to-bottom (irony OR awe — never blended).
- [ ] **Title** leads with verdict, names the entity, ends on `…` or post-dash twist, one idea — and matches a §2 validated formula.
- [ ] **Thumbnail** = one recognizable logo/face + one emotional idea + ≤3 words; out-contrasts the feed.
- [ ] **Hook:** stakes live by 0:15, fully framed by 0:30; zero intro/throat-clearing.
- [ ] **Pacing:** News-Reactor ≤7 min, density maxed, joke/30s, B-roll churn per sentence. Breakthrough escalating staircase, accelerating awe.
- [ ] **No early CTA;** loop stays closed until the verdict/implication. Soft tail CTA only.
- [ ] **Captions** burned in, word-by-word.
- [ ] **End-screen** loops to next video; pinned comment poses the open-loop question.
- [ ] **Bars:** would this clear CTR ≥10% and APV ≥30%? If not, fix the package before shipping.
- [ ] **Cheap-default honored:** no production spend on this unless it's already a proven winner.

---

## 8. The one rule above all others

**Find the outlier, then feed it.** The power law on this lane is real (2.8-3.5x). You are not trying to make every video good — you are trying to ship enough cheap, well-packaged shots that the power law hands you a winner, and then you clone that winner relentlessly until it stops working. Research → package → script → produce → ship → read → **double-down.** The double-down is where the $1M is.
