---
type: operator-playbook
lane: meditation
operator: TBD (Jay candidate)
date: 2026-06-06
rpm_band: "$1-3 + royalty upside"
status: ready-to-run
grounded_in:
  - rt-yt-knowledge-SEED/lanes/meditation/teardowns/greatmeditation.md
  - rt-yt-knowledge-SEED/lanes/meditation/teardowns/jasonstephensonmeditation.md
  - rt-yt-knowledge-SEED/lanes/meditation/script-bible.md
tags: [youtube, meditation, operator-playbook, faceless, yt-1mil]
---

# Meditation Lane — Operator Playbook

**This is the "how to run this lane" doc.** The script-bible tells you *what good looks like*; this tells you *what to do every week to ship it*. Everything below is grounded in two teardowns: `@GreatMeditation` (10-min Daily Practice, ~29K avg views) and `@jasonstephensonmeditation` (180-min Sleep/Hypnosis, ~161K avg views).

## 0. Read this first — the economic reality of this lane

Meditation pays the **lowest RPM of all four RT lanes ($1–3 vs. history $7–13, ai-dev $10–18).** You do not win this lane on ad RPM. You win on three other levers:

1. **Watch-time volume** — a 180-min sleep video farms enormous APV (all-night autoplay). One sleep session = the watch-time of dozens of short videos.
2. **Production that is genuinely cheap** — script + AI/stock voice + ambient music + a single still or slow-pan image. There is no filming, no B-roll hunting, no face. This is the cheapest lane to produce in the entire factory.
3. **Royalty/back-catalog upside** — meditation tracks are evergreen. A 10-min release video shipped today still earns in 18 months. Music/audio can be licensed and repurposed (Spotify, app catalogs) beyond YouTube.

**Operator mindset:** treat this like a back-catalog royalty machine, not a viral-hit machine. The strategy is *volume of evergreen assets in tight series*, riding autoplay. You are building a library, not chasing a spike.

**Start with the 10-minute Daily Practice video.** It's the cheapest unit to produce, fastest to test, and 9 of @GreatMeditation's top-10 are exactly 10 minutes. Prove the loop on Daily Practice, then graduate to Sleep long-form once a track is validated.

---

## 1. The weekly workflow (research → package → script → produce → ship → read → double-down)

Run this loop every week. Target cadence: **4–5 Daily Practice videos/week** at the start (cheap, fast), then layer in **1 Sleep long-form / week** once you have a validated track to expand.

### Monday — RESEARCH (30–45 min)
- Pull the top-10 of `@GreatMeditation` and `@jasonstephensonmeditation` for the week (and 2–3 adjacent channels: Great Meditation, Jason Stephenson, plus discover 1 new via "guided meditation 10 minute" search sort-by-this-month).
- Log every video doing **≥1.3x its channel average** into a running `winners.csv` (title, views, length, benefit promised, date).
- You're hunting for **named benefits that are spiking** (anxiety release, can't-sleep, overthinking, letting go). The *benefit* is the product; the format is fixed.

### Monday — PACKAGE (decide title + thumbnail BEFORE scripting)
- Package first, always. Pick a proven title formula from §2 and a single named benefit from the power-word bank.
- Lock the title and sketch the thumbnail concept (one mood, one image, ≤2 words) **before** a single line of script is written. If the package isn't clickable, the script doesn't matter.

### Tuesday–Wednesday — SCRIPT (1–2 hrs/video, batchable)
- Write to the descent-and-return arc (§4 of the bible): Arrival → progressive relaxation → core working (deliver the named benefit) → affirmation integration → gentle return.
- 10-min Daily = **~900–1,100 spoken words max.** Density kills the calm. Write pauses in as content: `[pause 8s]`.
- Batch this. Write 3–4 scripts in one sitting using the skeleton in §3 — the structure is identical video-to-video, only the named benefit changes.
- **Offload the grind:** draft scripts with a local LLM (Ollama llama3.1:8b) against the §3 skeleton, then human-edit for warmth and cadence. Claude/operator polishes; the model does the first-draft volume.

### Wednesday–Thursday — PRODUCE (see §4 for the cheap stack)
- TTS voice render → mix under ambient/binaural bed → marry to one looping still or slow-pan visual → export.
- Daily 10-min video should be a <90-min production task once the template is built.

### Thursday–Friday — SHIP
- Upload, fill the optimized title/description (CTA + playlist links live HERE, never in the audio), pin the next video, **add to the matching series playlist** (this is the growth engine).
- Schedule consistent posting times. Consistency feeds the autoplay/binge loop.

### Following Monday — READ THE RETENTION
- For each video 5–7 days old, pull: **CTR, APV (avg % viewed), 30-second retention, and the retention curve shape.**
- This lane's targets bend from the Field Manual defaults: CTR ≥6–8% is healthy for calm-signaling thumbnails (they don't curiosity-spike like history), but **APV is king here — push for ≥35–40%** because watch-time is the whole game. A clean, slow-decay retention curve (no early cliff) means the hook + voice are landing.
- Early cliff in first 30s = the cold open is failing (voice too cold, or you over-explained). Mid-video drop = the core working didn't deliver the title's promise.

### Ongoing — DOUBLE DOWN
- Any video that hits ≥1.3x your own channel average → **immediately clone its benefit into a series.** "10 Minute Anxiety Release" worked? Ship "10 Minute Stress Release," "10 Minute Fear Release," "10 Minute Anger Release" — same skeleton, swapped benefit. Then expand the winner into a 180-min Sleep version of the same theme.
- Kill benefits that underperform after 2 attempts. Don't sentimentalize. Volume + ruthless pruning.

---

## 2. Validated title formulas to clone (from the teardowns)

These are not guesses — every formula below is lifted from a video that beat its channel average. Bake **at least one power word** (§ power-word bank below) into every title.

### Daily Practice formulas (@GreatMeditation — clone these first)

**Formula A — the workhorse (highest ROI):**
> `<X> Minute <Named Benefit> (Guided Meditation)`
- "10 Minute Negative Emotion Release (Guided Meditation)" — **54,682 views (1.9x, channel #1)**
- "10 Minute Mindful Morning (Guided Meditation)" — 51,628 (1.8x)
- "20 Minute Chakra Healing & Balancing (Guided Meditation)" — 40,868 (1.4x)

**Formula B — the gerund/release frame:**
> `Releasing <X> (10 Minute Guided Meditation)`
- "Releasing Expectations (10 minute guided meditation)" — 37,624 (1.3x)
- Clone: `Releasing [Fear / Control / Worry] (10 Minute Guided Meditation)`

**Formula C — the transformation/identity frame (uses the `~` em-style):**
> `Become the <Role> and Find <State> ~ A 10 Minute Guided Meditation`
- "Become the Observer and Find Inner Peace ~ A 10 Minute Guided Meditation" — 37,300 (1.3x)
- "Just Breathe ~ A 10 Minute Guided Meditation" — 32,964 (1.1x)

**Three non-negotiables in every Daily title:** (1) explicit duration (10 or 20 min), (2) a specific named benefit, (3) the `(Guided Meditation)` tag. The curiosity-gap = name the **outcome, not the method**. "Negative Emotion Release" promises a result without revealing how — that's the click.

### Sleep / Hypnosis formulas (@jasonstephensonmeditation — graduate to these)

These are **comma-stacked, multi-promise** titles. The two strongest hooks are **reassurance** and **instant-relief**.

**Formula D — reassurance affirmation (the single biggest winner):**
> `You Are <Safe, Supported and Cared For>, Affirmations for a Calm Mind`
- "You Are Safe, Supported and Cared For, Affirmations for a Calm Mind" — **403,633 views (2.5x, channel #1)**

**Formula E — instant-relief urgency (caps intentional):**
> `Fall Asleep in MINUTES! Guided Meditation for <Instant Sleep / Deep Rest>`
- "Fall Asleep in MINUTES! Guided Meditation for Instant Sleep" — 362,482 (2.2x)

**Formula F — Sleep Hypnosis to <problem solved>:**
> `Sleep Hypnosis to <Stop Thinking / Quiet Your Mind / Let Go>`
- "Sleep Hypnosis to Stop Thinking and Start Being" — 237,321 (1.5x)

**Formula G — element + benefit stack:**
> `<Rainfall> Sleep Hypnosis, Wash Away Your <Worries>, Fall Asleep Quickly`
- "Rainfall Sleep Hypnosis, Wash Away Your Worries, Fall Asleep Quickly" — 218,003 (1.4x)

**Formula H — surrender/let-go frame:**
> `<Surrender> Meditation, Stop Trying to Control Life, Learn to Let Go`
- "Surrender Meditation, Stop Trying to Control Life, Learn to Let Go" — 200,409 (1.2x)

### Power-word bank (bake one into every title, seed several into the script)
- **Daily Practice:** Release, Healing, Balancing, Cleansing, Peace, Observer, Breathe, Mindful, Sacred, Supported.
- **Sleep / Hypnosis:** Safe, Supported, Cared For, Instant Sleep, Stop Thinking, Let Go, Wash Away Your Worries, Manifest, Joy, Happiness, Surrender, Quiet Your Mind, Talk Down.
- **The two strongest cross-lane themes** (proven #1s on both channels): **(1) Reassurance/safety** ("You Are Safe, Supported and Cared For") and **(2) Release/letting go** ("Negative Emotion Release," "Surrender," "Wash Away Your Worries"). When in doubt, build around one of these two.

---

## 3. Hook doctrine for THIS niche

**Critical — meditation hooks are the inverse of history/aviation hooks.** There is NO "stakes by 0:30" cliffhanger, NO suspense, NO open-loop tension. The retention contract is **relaxation delivered fast** — the listener must feel *safe and already practicing* within the first 15 seconds. A curiosity-spike hook would break the product.

The hook's job: **land them, make them feel safe, start the breath — immediately.** No throat-clearing, no "in today's video," no channel intro.

### Daily Practice cold open (copy-paste skeleton)
> "Welcome. Find a comfortable position, and gently allow your eyes to close. For the next ten minutes, there is nothing you need to do and nowhere you need to be. Let's begin by taking one slow breath in… and a long breath out. Together, over these next few minutes, we're going to **[PROMISED BENEFIT — e.g. release the tension you've been carrying]**."

Structure: (1) immediate do-it-now instruction (close eyes, settle), (2) present-moment anchor ("nowhere else to be"), (3) build safety then tease the transformation as a soft open loop ("we're going to release what no longer serves you"). The *transformation is the payoff being teased* — that's this lane's only "open loop."

### Sleep / Hypnosis cold open (copy-paste skeleton)
> "Hello, and welcome. It's such a pleasure to have you here tonight. You've arrived at a place where nothing is expected of you and nothing is required. There is nothing to fix, nothing to solve — only rest. So let your body sink down, and let's take this first slow breath in… together."

Structure: (1) warm personal welcome (the host persona IS part of the product in sleep), (2) the signature **permission-to-do-nothing** line — "a place where nothing is expected and nothing is required" — this maps directly to the 403K reassurance winner, (3) begin the breath, (4) fold them into the practice ("let's take this breath together").

**Hook rules:**
- First instruction inside 15 seconds. No preamble.
- Second person, present tense, soft imperative: "Allow yourself to…", "Notice the…".
- **No hype, no caps, no exclamation inside the audio** — even though "MINUTES!" wins in the *title*, the script delivers the opposite energy. Title sells urgency; audio delivers calm.
- The voice/persona matters more in sleep than in Daily Practice — invest warmth there.

---

## 4. Cheap-default production approach + tools

This lane must stay genuinely cheap (RPM is $1–3). Build a reusable template once, then it's near-zero marginal cost per video.

### The stack (build the template, then assembly-line it)

**Voice (the one place to test before committing cheap):**
- Default cheap path: **AI TTS — ElevenLabs** (has a meditation-suited soft voice) or **OpenAI TTS**. Pick ONE warm, slow voice and standardize it as the channel's "host." Consistency builds the brand.
- Test: render a 60s sample, listen for warmth + natural pauses. If AI voice tanks retention in the 30s read, a cheap human VO (Fiverr meditation narrator, ~$30–80/track) becomes the upgrade — but only after a benefit is validated. Cheap-by-default; invest only in proven winners.

**Audio bed:**
- Ambient/binaural/rain loops from **royalty-free libraries** (YouTube Audio Library, Pixabay Music, Epidemic Sound if already subscribed). Layer voice on top at low music volume.
- Reusable: build 3–4 standard beds (rain, deep-space ambient, soft piano, binaural) and rotate.

**Visual (faceless — one still or slow pan):**
- A single serene image: AI-generated (Midjourney/SDXL) silhouette-in-lotus, sunrise, moon/stars for sleep, or a soft gradient.
- Apply a slow **Ken Burns / parallax pan** so it's not a dead frame. Tools: **Remotion** (RT already has the skill — programmatic, repeatable, on-brand), or a simple ffmpeg zoompan for the cheapest path.
- For 180-min sleep: a single looping ambient visual is standard and accepted — viewers' eyes are closed.

**Assembly / render:**
- **Remotion** (preferred — RT in-house skill, templated, scales) for the visual + caption layer, or ffmpeg for raw audio-over-image muxing. Build the template ONCE; swap audio + benefit text per video.
- **Script first-draft offloaded to local Ollama** (llama3.1:8b) against the §3 skeleton — operator/Claude only polishes for warmth and cadence. Don't burn premium tokens on volume scripting.

### Thumbnail (cheap, templated)
- One mood, one focal image, ≤2 words of text (duration "10 MIN" or one power word "RELEASE"/"SLEEP").
- Daily Practice: serene single subject, palette matched to benefit (warm for "Mindful Morning," violet/cool for "Chakra Healing").
- Sleep: night palette — deep blues/purples, moon, stars, peaceful sleeping figure.
- Build a Canva or Remotion thumbnail template per series so the channel reads as one trustworthy, bingeable brand. **Series consistency reinforces the autoplay engine.**

### CTA discipline (this is the anti-CTA lane)
- **No mid-roll CTA. Ever.** It destroys the product, especially in sleep.
- Optional soft front-load (≤8s, inside the calm register): "If this brings you peace, you're always welcome back."
- All conversion work — subscribe, playlist links, next video — lives in the **end card + pinned description**, never the spoken audio.
- **Playlisting IS the CTA.** Build every video into a tight series so one view autoplays into the next.

---

## 5. YPP-fast strategy (get monetized quickly)

YPP threshold: **1,000 subscribers + 4,000 public watch hours in 12 months** (or 10M Shorts views in 90 days). This lane is *built* to clear watch hours fast — lean into that.

1. **Watch hours come free here — exploit it.** A single 180-min sleep video watched start-to-finish = ~3 watch hours from one viewer, and sleep viewers leave it on all night. **Ship 2–3 Sleep long-form videos early specifically to farm watch hours.** Five all-night plays of one 3-hour video ≈ 15 watch hours. This is the fastest path to 4,000 hours of any RT lane — meditation's structural advantage.
2. **Daily Practice clears the subscriber count.** The 10-min videos are more discoverable (search "10 minute guided meditation"), get more sessions, and drive subs. Run Daily for subs + discovery, Sleep for raw watch-hours.
3. **Front-load a tight series in the first 30 days.** Pick ONE validated benefit theme (start with "Release" or "Sleep — Safe & Supported," the two proven #1s) and ship 8–10 videos in that series fast. A coherent series = autoplay chaining = compounding watch hours + a reason to subscribe.
4. **Optimize the package relentlessly early** — at low channel volume, CTR on search/suggested is what gets the first sessions. Clone proven titles verbatim-in-structure (don't get creative).
5. **Avoid the watch-hour traps:** keep all videos **public** (private/unlisted don't count), avoid Shorts-only early (Shorts views don't count toward the 4,000-hour path), and don't run music you don't have rights to (claims/blocks zero out watch hours).

**Expected fast path:** 3 sleep long-form + a 10-video Daily series in month one realistically puts a focused operator on track to clear 4,000 watch hours and 1,000 subs faster than any other RT lane.

---

## 6. Five concrete first-video ideas (using the winning patterns)

Each clones a proven formula and a proven benefit. Ship these as the channel's opening series.

**Video 1 — "10 Minute Negative Emotion Release (Guided Meditation)"**
- Formula A, the literal #1 on @GreatMeditation (54,682 views, 1.9x). Start by cloning the proven winner directly. Benefit: release. Thumbnail: silhouette in lotus, warm gradient, "RELEASE." Cold open = Daily skeleton, promised benefit "release the heaviness you've been carrying."

**Video 2 — "10 Minute Mindful Morning (Guided Meditation)"**
- Formula A, proven #2 (51,628, 1.8x). Different daypart, different intent (energize/center vs. release) — gives the series two distinct entry points. Thumbnail: sunrise, warm palette, "MORNING." Anchors the "start your day" search demand.

**Video 3 — "Releasing Anxiety (10 Minute Guided Meditation)"**
- Formula B, modeled on "Releasing Expectations" (37,624, 1.3x), swapped to **anxiety** — the highest-demand named benefit in the niche. Core working = guide the actual anxiety release. Thumbnail: soft cool gradient, single calm subject, "RELEASING ANXIETY."

**Video 4 — "20 Minute Chakra Healing & Balancing (Guided Meditation)"**
- Formula A in the 20-min slot, cloning the proven 20-min outlier (40,868, 1.4x). Reserve the longer runtime for the "bigger" spiritual promise. Move through the chakras in the core working. Thumbnail: violet/rainbow energy motif, single glowing figure, "CHAKRA."

**Video 5 — "You Are Safe, Supported and Cared For — Sleep Affirmations for a Calm Mind" (180 min)**
- Formula D, modeling the single biggest winner across both channels (403,633 views, 2.5x). The reassurance theme is the strongest concept in the entire lane. This is the **watch-hour farm** for YPP. Build a 20–30 min affirmation talk-down, then loop with lengthening pauses to fill 3 hours. Cold open = Sleep skeleton (permission-to-do-nothing). Thumbnail: night palette, moon/stars, peaceful sleeping figure, "SAFE."

**Series logic:** Videos 1–4 are a cohesive "Daily Reset" 10-min collection (drives subs + discovery + playlist autoplay); Video 5 is the sleep flagship (farms watch hours for YPP). Together they cover the two proven #1 themes — **Release** and **Reassurance/Safety** — and exercise every Daily formula plus the top Sleep formula. After read-the-retention, double down on whichever benefit over-indexes by cloning it across the rest of the power-word bank.
