---
type: operator-playbook
lane: aviation
operator: Glitch
date: 2026-06-06
status: active
rpm_band: "$7-13"
target_metrics: "CTR ≥10%, APV ≥30%, retention flat-to-rising through 0:30"
sources:
  - "$SEED/lanes/aviation/teardowns/mentourpilot.md (@MentourPilot — avg 997,964 views, top-10 avg 1,344,008, 1.7x outliers)"
  - "$SEED/lanes/aviation/teardowns/greendotaviation.md (@GreenDotAviation — avg 817,981 views, top-10 avg 1,234,291, 1.9x outliers)"
  - "$SEED/lanes/aviation/script-bible.md"
related:
  - "[[script-bible]]"
  - "[[Operator Field Manual]]"
tags: [youtube, aviation, operator-playbook, faceless-channels, rt-yt-1mil]
---

# Aviation Lane — Operator Playbook

**Operator:** Glitch · **Lane:** Aviation disaster / air-crash investigation · **RPM band:** $7–13

This is the practical "how to run this lane" doc. The genre is locked: **a known catastrophe re-told as an unfolding mystery, where the audience already knows the plane is in trouble but does NOT know why, who's at fault, or whether anyone survives.** Two proven channels — @MentourPilot and @GreenDotAviation — both run a million-view baseline with a live power law (outliers pull 1.7x–1.9x the channel average). We reverse-engineer them, beat them on packaging contrast + cadence, and stay cheap-by-default until a video proves itself a winner.

Do not invent a new format. Build to this single genre and nothing else.

---

## 1. The Weekly Workflow

One loop, run every week. Each step has a gate — don't advance until the gate is met. The whole point is to manufacture *swings at the power law*: most videos land near baseline, a few pull 1.7x+, and those few pay for everything. Your job is volume of well-packaged swings, then ruthless double-down on what hits.

### Research → Package → Script → Produce → Ship → Read → Double-Down

**1. RESEARCH (Mon)** — Pick the incident. Pull from the incident backlog (build a running list of 50+ documented crashes/emergencies). Select for: a documented investigation report (NTSB/AAIB/ICAO/final report exists), an unresolved-*feeling* "why," and a clear legacy/change (a regulation, procedure, or design fix came out of it). Avoid incidents with no public report — you can't ration a chain you can't source. **Gate:** you can name the chain of failures in 5–7 dominoes and state what changed afterward.

**2. PACKAGE (Mon)** — Title + thumbnail *before* you write a word of script. This is the most important step; a great video with a weak package dies. Write the title from Formulas A–E (§2). Draft 3 title variants and 2 thumbnail concepts. **Gate:** the *why* is withheld in the title, the flight identifier is present, and the thumbnail shows ONE literal visceral image. If you can't make the package intriguing, kill the idea here — cheapest place to fail.

**3. SCRIPT (Tue)** — Write to the script-bible arc: cold-open machine (0:00–0:30) → rewind to calm → lay dominoes one per beat with dramatic irony → point of no return → the event → investigation reveal (gap closes HERE, never earlier) → legacy beat. One new fact per beat; each beat opens a fresh micro-question. **Gate:** read the first 30 seconds aloud — if a viewer could click away satisfied after the cold open, rewrite it. The cold open answers nothing.

**4. PRODUCE (Wed–Thu)** — Cheap-default pipeline (§4). AI voiceover, stock aviation footage + map animations + report scans, simple motion. Do NOT over-invest until the video proves itself. **Gate:** audio is clean, pacing matches the script's micro-question rhythm, retention-critical first 30s is tight.

**5. SHIP (Fri)** — Upload, set thumbnail, write description with timestamps, end-card pointing to a *related* incident video. Publish in the slot your analytics show your audience is live (aviation skews evenings/weekends — confirm in your own data after 4–6 uploads). **Gate:** end-card is itself a curiosity gap into the next mystery.

**6. READ (Fri+72h, then 7d, then 28d)** — Read retention, not vanity views. The three numbers that matter: **CTR** (is the package working? ≥10% target), **APV / avg view duration** (is the chain holding? APV ≥30%), and the **first-30s retention curve** (is the cold open working? flat-to-rising). Diagnose with the Field Manual gates:
   - Low CTR → package problem. Title or thumbnail. Swap the thumbnail first (cheapest fix, A/B if available).
   - High CTR, low APV → the chain leaked. You resolved the mystery too early, or dumped the timeline instead of rationing it.
   - Retention cliff in first 30s → cold open failed. You introduced the channel/date first, or didn't drop into crisis mid-action.

**7. DOUBLE-DOWN (ongoing)** — When a video pulls 1.5x+ baseline, mine it. Make a *sibling* video on a structurally similar incident (same failure type, same title formula, same thumbnail energy). The power law rewards clustering — GreenDotAviation and MentourPilot both run families of similar videos. *Now* you can invest more in production on the proven pattern. Cheap-by-default everywhere else.

**Cadence target:** 1 video/week minimum to start (this genre is script-heavy). Push to 2/week once the pipeline is greased and you've found a winning cluster. Consistency beats volume early — the algorithm needs a clean signal.

---

## 2. Validated Title Formulas (clone these)

Every title pairs an **emotional/curiosity trigger** with the **flight identifier** (airline + flight number, or named subject), split by a `|` or `..`. Always include the identifier — it's the credibility anchor that separates this from clickbait and signals "real, documented, investigable." Always scream ONE capitalized power word minimum. The *why* is never in the title.

### Formula A — The Question Hook (GreenDotAviation's signature)
`What HAPPENED [Flight]??` · open with What/Why/How, close on a **double `??`**. The `??` signals "even the experts are confused."
- Proven: *What HAPPENED Emirates 521??* (1.57M) · *Why did BOTH engines fail immediately after takeoff?? | SAS 751* (937K) · *What were they THINKING?? | Gulf Air Flight 072* (1.07M)

### Formula B — The Impossible / Contradiction Hook
State an outcome that violates how the viewer thinks flying works. The gap between "planes don't do that" and "this one did" is the click.
- Proven: *This Should NOT Have Been POSSIBLE! | LATAM 8073* (1.51M) · *Crashing after 22 seconds?? Delta 1141* (1.28M) · *The Plane that Couldn't Land | Avianca 052* (1.28M)

### Formula C — The Buried-Significance Hook (MentourPilot's signature)
Promise a *hidden* or *misunderstood* story — the viewer's ignorance is the hook. "You've Never Heard Of" / "What REALLY Happened" imply the official version is wrong or incomplete.
- Proven: *What REALLY Happened To Kobe Bryant's Helicopter?!* (1.70M — channel #1) · *The Most Important Crash You've Never Heard Of... | TWA Flight 514* (1.61M)

### Formula D — The Emotional-Stakes / Moral Hook
Front-load a value judgment (worst, lies, sacrifice, everything) that frames the story as morally charged, not just technical. This is what licenses 44–66 minute runtimes — the promise is emotional, not procedural.
- Proven: *The WORST Story I've Ever Told.. | Germanwings 9525* (1.67M) · *This Cost Them EVERYTHING | American Airlines 965* (1.14M) · *A Litany of LIES! | The Mount Erebus Disaster* (1.07M)

### Formula E — The Visceral Image Hook
Lead with a concrete, physical, slightly grotesque image the thumbnail can render literally.
- Proven: *Melting From The Inside Out! | Swiss Air 111* (1.31M) · *LOST at sea?? | The INSANE story of Flight 782* (1.56M) · *The Flight that went DARK | British Airways 870* (1.36M) · *Trapped! The harrowing story of Virgin Flight 024* (1.17M)

**Power-word bank (caps these):** HAPPENED · WORST · DARK · TRAPPED · LIES · EVERYTHING · POSSIBLE · REALLY · THINKING · LOST · MELTING · IGNORE · SACRIFICE · IMPOSSIBLE

**Non-negotiables:** (1) flight identifier always present; (2) ≥1 screamed power word; (3) curiosity gap unresolved — say *what* happened, withhold *why*; (4) close on `??` / `..` / `!` — these tics read as authentic enthusiast voice, not corporate.

---

## 3. Hook Doctrine for THIS Niche

The cold open is a machine. Build it in this exact order, every time. Both teardowns describe an identical opening structure — this is the highest-leverage 30 seconds you will write.

- **0:00–0:05 — Drop into the crisis, mid-action.** No channel intro, no host, no date. Open *inside* the tense moment — the aircraft is already in trouble. This is the <15s hook from the Field Manual. The #1 retention killer in this lane is starting with "Hey everyone, welcome back" — never do it.
- **0:05–0:20 — Open the loop / pose the unanswerable.** State the mystery as a question the viewer cannot answer yet: *Why was this possible? How did trained pilots miss this? What were they thinking?* Give just enough to make the question land — no more.
- **0:20–0:30 — Plant the stakes + the promise.** Signal why this matters beyond itself: "the most important crash," "this changed aviation forever," "this should never have happened." This is the stakes-by-0:30 rule.
- **End on a cliffhanger, then cut** to the rewind transition ("to understand how we got here, we need to go back to the beginning"). Resolve nothing.

**The one rule:** the cold open sharpens the question; it answers nothing. If a viewer could click away satisfied at 0:60, the cold open failed — rewrite it.

**Verbal tics to deploy** (steal verbatim): *"What the crew didn't know was…"* · *"At this point, everything still looked normal."* · *"But there was a problem no one had noticed."* · *"From this moment, there was no going back."* These set up the dramatic irony that IS the retention engine — the viewer sees each domino before the crew does and shouts at the screen.

**Tone:** authoritative but accessible (use correct terminology, then translate it), sober and respectful (real people died — drama comes from the chain of decisions, never gore), empathetic to the crew ("here's why a competent, trained pilot made this fatal choice," never "the pilots were idiots"). The empathy is what makes the irony land as tragedy, not mockery — and tragedy holds retention far longer than mockery.

---

## 4. Cheap-Default Production Approach + Tools

This lane is faceless and script-driven, which is a gift: no on-camera talent, no set, no shoot. The video is voiceover + visuals + motion. Keep it cheap until a video earns investment.

**The stack (cheap default):**
- **Script:** Claude/LLM-assisted draft → operator edit to the script-bible arc. The script is 80% of the value; spend time here, not on polish.
- **Voiceover:** AI TTS — ElevenLabs (best naturalness for long-form narration) or a cheaper tier (PlayHT, OpenAI TTS) while testing a cluster. A calm, authoritative, slightly grave voice fits the genre. Lock ONE voice as the channel's identity.
- **Visuals (the cheap-default kit):**
  - Stock aviation footage (Pexels, Pixabay, Storyblocks/Artgrid if you upgrade) — generic aircraft, cockpits, weather, airports. You rarely need the *specific* tail number.
  - **Map + flight-path animations** — the single most valuable visual in this lane. Animate the route, the deviation, the point of no return over a map. Cheap to make (After Effects, or even Keynote/Canva motion), and it carries the chronological chain visually.
  - **Investigation report scans / document overlays** — screenshot the actual NTSB/AAIB report pages (public domain) for the reveal beat. Free, and they sell credibility.
  - **Simple text/timestamp overlays** — "14 minutes before impact," "T-minus 22 seconds." Countdown framing accelerates the back half (cf. *Crashing after 22 seconds?? Delta 1141*).
  - Generic cockpit instrument B-roll + subtle Ken Burns motion on stills to avoid dead frames.
- **Editing:** DaVinci Resolve (free) or CapCut/Premiere. Burn captions for accessibility + retention.
- **Thumbnail:** ONE literal image of the title's visceral noun (Photoshop/Canva/Affinity). Aircraft in jeopardy mid-event — banking, smoke, night, weather — never a clean parked plane. Short text overlay echoing the power word, not the full title. Title carries the question, thumbnail carries the image — they contrast, never duplicate.

**Investment rule:** everything above is the cheap default for *unproven* videos. When a video pulls 1.5x+ baseline, the *sibling* videos in that cluster earn upgrades — premium footage license, custom map animations, a sound designer. Never invest ahead of proof. Production is cheap-by-default; you buy quality only for patterns the audience has already validated.

**Legal/sourcing note:** government accident reports (NTSB, AAIB, TSB, BEA, ICAO) are public domain — your factual spine. Use licensed/royalty-free footage and your own animations. Never lift another channel's footage or script.

---

## 5. YPP-Fast Strategy (get monetized quickly)

Goal: hit the YouTube Partner Program threshold (1,000 subs + 4,000 public watch hours in 12 months, or the Shorts path) as fast as possible, then unlock the $7–13 RPM. This lane is *built* for fast watch-hour accumulation because the videos are long (24–66 min) and retention-engineered.

- **Lead with watch hours, not subs.** A single 35-minute video that holds APV ≥30% banks ~10.5 minutes of watch time *per view*. At a few hundred thousand views per winner, you clear 4,000 hours off one or two outliers. Long-form + high retention is the fastest watch-hour engine on the platform — lean into the full runtime, don't cut it short.
- **Front-load your best 4–6 incidents.** Don't sandbag your strongest stories. Open the channel with your most intriguing, most-documented incidents using the proven title formulas — you want early swings at the power law to seed the channel and the algorithm.
- **Cluster from day one.** Pick a failure-type or era cluster (e.g., "engine failures," "pilot-error cover-ups," "weather disasters") so each video's end-card points to a sibling, compounding session time and binge behavior. Bingeable clusters accelerate both watch hours and the algorithm's understanding of your channel.
- **Optimize the cold open above all else.** Watch hours die in the first 30 seconds. The retention-flat-to-rising-through-0:30 gate is your YPP accelerator — every percentage point you save in the cold open multiplies across the full runtime.
- **Consistency for the signal.** 1/week, same slot, clean genre signal. The algorithm rewards a legible channel faster than a sporadic one. Don't dilute with off-genre experiments before YPP.
- **End-card chaining = watch-hour multiplier.** "If you found this disturbing, the story of [Flight X] is even worse." This turns one view into a session, and sessions are watch hours.

**Realistic path:** with 1 video/week at this length and retention, 1–2 outliers in the first 8–12 uploads typically clears the 4,000-hour bar; subs follow watch time in this genre. Then the RPM band kicks in and the power law does the rest.

---

## 6. Five Concrete First-Video Ideas

Each uses a proven title formula, a withheld *why*, a documented report, a clear legacy beat, and a literal thumbnail. These are the channel-seeding swings.

**1. United 232 — Sioux City (Formula B, Impossible/Contradiction)**
- Title: *They Flew a Plane With NO Controls | United 232*
- Why it works: total hydraulic failure should have been unsurvivable — the contradiction is the click. Withheld *why*: how did they steer with engines alone?
- Chain: fan-disk failure → all three hydraulic systems severed → differential-thrust improvised control → partial-survival crash landing. Legacy: DC-10 hydraulic redesign + CRM training canon.
- Thumbnail: DC-10 cartwheeling/breaking up on the runway, smoke. Overlay: "NO CONTROLS."

**2. Helios 522 — The Ghost Flight (Formula A, Question Hook)**
- Title: *Why Did This Plane Fly On With EVERYONE Asleep?? | Helios 522*
- Why it works: the eerie "ghost flight" image + the unanswerable *why* the crew was unconscious. Withheld *why*: a single switch position.
- Chain: pressurization switch left in MANUAL → hypoxia → incapacitated crew → autopilot flies to fuel exhaustion. Legacy: pressurization warning/checklist changes.
- Thumbnail: silent dark cabin, oxygen masks dangling. Overlay: "EVERYONE ASLEEP."

**3. Air France 447 (Formula C, Buried-Significance)**
- Title: *The Crash That Was Lost For 2 Years | What REALLY Happened to AF447*
- Why it works: "lost for 2 years" (black boxes deep in the Atlantic) + "what REALLY happened" implies the obvious story is wrong. Withheld *why*: trained pilots stalled a working plane.
- Chain: iced pitot tubes → unreliable airspeed → autopilot disconnect → sustained pilot-induced stall → ocean. Legacy: pitot-tube AD, stall-recovery retraining, manual-flying emphasis.
- Thumbnail: A330 over black open ocean at night. Overlay: "LOST FOR 2 YEARS."

**4. British Airways 9 — The Jakarta Incident (Formula E, Visceral Image)**
- Title: *All Four Engines Just Went DARK | British Airways 9*
- Why it works: "went DARK" is literal and visceral (St. Elmo's fire, dead engines over the ocean at night). Withheld *why*: there was no warning of the cause.
- Chain: flew into invisible volcanic ash cloud → all four engines flamed out → 16-minute glide → restart in cleaner air. Legacy: volcanic-ash advisory centers worldwide.
- Thumbnail: 747 at night, engines glowing/St. Elmo's fire on the windscreen. Overlay: "WENT DARK."

**5. Tenerife 1977 — The Runway Disaster (Formula D, Emotional/Moral Stakes)**
- Title: *The Deadliest Mistake in Aviation History | Tenerife*
- Why it works: deadliest-ever framing + a moral chain (one assumption, one radio clip, hundreds dead). Withheld *why*: how two working 747s collided on the ground.
- Chain: bomb threat diversion → fog → radio step-on/ambiguous clearance → captain's takeoff without clearance → collision. Legacy: standardized phraseology + CRM — the disaster that rewrote cockpit communication.
- Thumbnail: two 747s in fog on a runway, fireball. Overlay: "DEADLIEST MISTAKE."

> **Cluster logic:** #2 and #3 both fit a "human-factors / the crew couldn't save it" cluster; #1 and #4 fit a "catastrophic systems failure they survived anyway" cluster; #5 anchors a "communication breakdown" cluster. Ship across two clusters first, read the data, then double-down on whichever cluster pulls 1.5x+ and chain siblings off the winner.
