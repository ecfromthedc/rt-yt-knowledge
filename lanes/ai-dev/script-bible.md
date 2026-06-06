---
type: script-bible
lane: ai-dev
date: 2026-06-06
sources:
  - teardowns/fireship.md (@Fireship, 25 videos, ch avg 928K, top-10 avg 1.37M)
  - teardowns/twominutepapers.md (@TwoMinutePapers, 25 videos, ch avg 109K, top-10 avg 181K)
rpm_band: $10-18
---

# Script Bible — AI-Dev Lane

The reusable blueprint for writing a winning ai-dev script. Every rule below is reverse-engineered from the two teardowns in `lanes/ai-dev/teardowns/`. The lane splits into two proven archetypes that map to two channels: **News-Reactor** (Fireship — 4-7 min, power-law outliers at 3.5x) and **Breakthrough-Narrator** (Two Minute Papers — 7-21 min, slower-burn 2.8x outliers). Pick the archetype per video; do not blend them.

---

## 0. The two archetypes (decide first)

| | News-Reactor (Fireship model) | Breakthrough-Narrator (2MP model) |
|---|---|---|
| Length | 4-7 min. Top outlier ("Anthropic leaks Claude's source code") = 7m, most winners 4-5m | 7-21 min. Winners cluster at 7-11m; one 21m interview ("Demis Hassabis On What AI Will Do Next") still cleared 1.2x |
| Trigger | A *news event* (a leak, a launch, an outage, a disruption) | A *research result / model release* and what it means |
| Energy | Fast, sardonic, hyper-cut, dense | Awe-driven, accelerating, "hold onto your papers" wonder |
| RPM driver | Volume + recency. Ship the day the news breaks | Depth + evergreen-ish breakthroughs that keep pulling |
| Outlier title | "Tragic mistake... Anthropic leaks Claude's source code" (3.21M, 3.5x) | "DeepSeek's New AI Is A Game Changer" (310K, 2.8x) |

**Operator rule:** if the topic is *something that just happened*, write News-Reactor. If the topic is *a capability that now exists*, write Breakthrough-Narrator.

---

## 1. Title formulas (the reusable money)

These are the literal extracted structures. Treat them as fill-in-the-blank templates.

### News-Reactor formulas (Fireship)
- **`<Event/Action> that <Company/Subject>`** — the core extracted structure.
- **The "Tragic mistake" frame:** `<Emotional verdict>... <Company> <dramatic action>` → *"Tragic mistake... Anthropic leaks Claude's source code"* (the single biggest outlier on the channel, 3.5x). Lead with the *judgment* before the *fact*.
- **The "just casually" disruptor:** `<Company> just casually <disrupted X>` → *"Google just casually disrupted the open-source AI narrative…"* The word **casually** does the work — it implies the giant did something world-changing as an afterthought.
- **The "just changed the future" frame:** `<Company> just changed the future of <domain>...` → *"Google just changed the future of UI/UX design..."*
- **The "crawled through hell" suffering frame:** `He just <crawled through hell> to <fix X>…` → *"He just crawled through hell to fix the browser…"* Personifies a faceless engineering story into a human ordeal.
- **The "too dangerous" forbidden-knowledge frame:** `<Subject> is too dangerous for <public/release>...` → *"Claude Mythos is too dangerous for public consumption..."*
- **The "endgame" frame:** `<Company>'s AI endgame is here… everything you missed at <event>` → *"Google's AI endgame is here…"* Pairs a doom-word with a FOMO recap promise.
- **The "breaking the law, by design" frame:** `This new <thing> is breaking the law, by design…` → *"This new Linux distro is breaking the law, by design…"*

### Breakthrough-Narrator formulas (Two Minute Papers)
- **`<Company/Developer>'s New AI <Action>`** — the core extracted structure. Note the possessive + "New AI" is near-mandatory.
- **The "Game Changer / Changed X Forever":** *"DeepSeek's New AI Is A Game Changer"* (2.8x) · *"DeepMind's New AI Just Changed Science Forever"* (2.2x).
- **The "Beats Billion Dollar Systems…For Free":** `<Underdog> Beats <Expensive incumbent>…For Free` — the **…For Free** tag is the unique selling point that the teardown flags as what top titles do that lower ones don't.
- **The "Just Broke My Brain":** `<Company>'s New AI Just Broke My Brain` — first-person astonishment.
- **The "Solves Problems…By Cheating":** `<Company>'s New AI Solves Problems…By Cheating` — the contradiction/twist after the ellipsis is the curiosity engine.
- **The "Gift To Humanity":** `<Company>'s New AI: A Gift To Humanity` — grandiose stakes elevation.

### Title laws (apply to both)
1. **Name a recognizable proper noun.** Every single top title cites a known entity — Anthropic, Google, GitHub, NVIDIA, DeepMind, DeepSeek, Claude. The teardown explicitly notes top titles "reference a specific and recognizable company." No generic "this AI tool."
2. **Lead with an emotional verdict, not the neutral fact.** "Tragic mistake" beat "GitHub is having some major issues" — the teardown's own comparison. The judgment word is the hook.
3. **Use the trailing ellipsis `…` to open the loop.** Nearly every top title ends mid-thought. The ellipsis *is* the curiosity gap.
4. **Put the twist after the ellipsis/dash.** "…By Cheating", "…For Free", "…by design". The setup is mundane; the tag reverses expectation.
5. **One idea per title.** Don't stack two claims. One company, one shocking verb.

**Power-word bank (extracted, use verbatim or as a thesaurus):** tragic mistake · just changed · just disrupted · casually disrupted · crawled through hell · too dangerous · endgame · major issues · breaking the law · game changer · changed [X] forever · beats billion dollar systems · broke my brain · by cheating · a gift to humanity · for free.

---

## 2. Cold-open / hook structure (first 0:00–0:15)

The hook must land the stakes before 0:30 (Intrigue Doctrine), and in this lane the winners do it inside the first 1-2 sentences.

### News-Reactor cold-open (3-beat, from Fireship teardown §4)
1. **Beat 1 — Shocking statement (0:00–0:05).** Open on the surprising/unexpected event as a flat, declarative shock. No "hey guys, today we're going to talk about." Drop the reader mid-explosion.
2. **Beat 2 — Context snap (0:05–0:12).** Provide just enough background to make the shock legible. Fast, compressed.
3. **Beat 3 — Anticipation hook (0:12–0:15).** Hint at consequences/further details — tease the open loop you'll pay off ("…and it's worse than you think" / "…here's everything you missed").

The teardown's recipe verbatim: *"Start with a shocking statement → provide context → build anticipation by hinting at further details or consequences."* Plus its open-loop levers: **highlight the irony/contradiction**, **pose a question about the implications**, **emphasize the impact on a specific group/industry.**

### Breakthrough-Narrator cold-open (from 2MP teardown §4)
1. **Beat 1 — Intriguing topic (0:00–0:05).** Introduce the surprising development in sentence one.
2. **Beat 2 — Challenge question (0:05–0:15).** Immediately pose a question that challenges existing knowledge — the teardown's literal examples: *"Why is this new deep sea AI system necessary?" / "How can an AI write research papers?" / "What makes DeepSeek 4 unique among AI models?"*
3. **Beat 3 — Rhythm lock.** Maintain a fast, engaging cadence so the question's pull doesn't sag.

**Hook anti-patterns (never do):** channel intro, self-introduction, "before we start, smash like," slow throat-clearing, defining the topic academically. Stakes must be live by 0:15, fully framed by 0:30.

---

## 3. Narrative arc & pacing

### News-Reactor arc (4-7 min)
- **0:00–0:15 Hook** (§2). **0:15–0:45 The setup** — what's the thing, who did it, why it's a big deal. **0:45–end Rapid escalation** — stack 4-8 micro-segments, each a new wrinkle/consequence/reaction, each ~20-40s. End on a verdict + forward-looking jab.
- **Pacing law: density over duration.** A 3.5x outlier was only 7 minutes ("Anthropic leaks Claude's source code"). Cut every dead second. Joke-per-30s cadence. Visual/B-roll change on nearly every sentence. The currency is information-per-second.

### Breakthrough-Narrator arc (7-21 min)
- **0:00–0:15 Hook + challenge question** (§2). **0:15–2:00 Establish the problem** the breakthrough solves (this is the "why necessary" payoff). **2:00–end Escalating demonstration** — walk through what the AI/model now does, each example *more impressive than the last*. The arc is a rising staircase of "wait, it gets better." **Close on the implication** — what this means for science/society ("A Gift To Humanity" energy).
- **Pacing law: accelerating awe.** Slower start is allowed (you have 7-21 min), but each segment must escalate. The audience stays for the next "and then it did THIS." Never plateau.

---

## 4. Transition tactics

- **News-Reactor:** hard cut + new visual + a contrastive connective — "but here's where it gets worse," "and then it gets stupid," "plot twist." Transitions are *escalators* — every one raises stakes or reverses expectation. The "…by design / …by cheating" title twist logic applies inside the body too: set up mundane, snap to the reversal.
- **Breakthrough-Narrator:** the signature **"but hold onto your papers"** escalation cue and "and just look at this" demonstration pivot. Transitions are *reveal triggers* — each one ushers in a more impressive result. Use "now watch what happens when…" / "but here's the part that broke my brain."

---

## 5. Recurring phrases / tonal register

### News-Reactor (Fireship) register
Sardonic, deadpan, hyper-literate, slightly chaotic. Treats billion-dollar drama with dry irony. The teardown notes the mechanism is **irony/contradiction** — lean into "the richest company on earth just did the dumbest thing." Phrasing palette: "casually," "tragic," "crawled through hell," "too dangerous," "endgame," "by design." Punch up at giants, never explain the joke.

### Breakthrough-Narrator (2MP) register
Earnest wonder, first-person astonishment, accelerating excitement. The teardown's emotional triggers are **awe-based**: "broke my brain," "game changer," "gift to humanity." Phrasing palette: "just look at this," "absolutely incredible," "and it gets better," first-person reactions ("broke MY brain"). The host is a delighted guide, not a critic.

**Register law:** pick one and commit for the whole script. News-Reactor = irony. Breakthrough-Narrator = awe. Mixing flattens both.

---

## 6. CTA patterns

Neither teardown surfaces a hard mid-roll sell — consistent with the Intrigue Doctrine (don't break the loop). Operator defaults derived from the lane:
- **No early CTA.** Stakes-first; never spend the first 30s on subscribe asks (would kill APV/retention).
- **Soft tail CTA only** after the verdict/implication lands, when the loop is closed.
- **Loop-forward CTA:** end on the next question this breakthrough/event opens — the implicit "subscribe to see what's next" rather than an explicit beg. News breaks daily; breakthroughs compound — the channel itself is the CTA.
- _This is the lane's biggest open data gap — fill from retention graphs after first 3 shipped videos (the teardown "steal list" flags this exact TODO)._

---

## 7. Thumbnail patterns

Captions-only teardown, so thumbnails are inferred from title logic + Intrigue Doctrine (one idea per thumbnail):
- **One recognizable logo/face.** Titles always name a known entity; the thumbnail shows it — the Anthropic/Google/NVIDIA/DeepSeek logo or a known founder's face (Hassabis). Instant recognition = instant click.
- **One emotional idea, no clutter.** Match the title's single shocking verb with one visual (a leak = exposed code/red alert; a breakthrough = a jaw-drop demo frame).
- **News-Reactor:** high-contrast, slightly chaotic, often a logo + a 1-3 word screaming overlay or an emoji/expression that telegraphs the irony.
- **Breakthrough-Narrator:** the single most impressive result frame (the "just look at this" moment) + an awed expression. Show the payoff, not the process.
- **Packaging-contrast is the named edge.** Both teardown "steal lists" say copy the title formula but **beat them on packaging contrast + upload cadence** — so the thumbnail must out-contrast the competitor's in-feed (bolder color, clearer single idea, bigger recognizable entity).

---

## 8. The fill-in-the-blank script skeleton (operator template)

**News-Reactor (4-7 min):**
1. TITLE: `<emotional verdict>... <known company> <dramatic action>…`
2. 0:00 Shock sentence (the event, flat and stunning).
3. 0:05 Context snap (who/what, 2 sentences).
4. 0:12 "…but here's where it gets [worse/stupid/dangerous]" — open loop.
5. Body: 4-8 escalating beats, each a new wrinkle, joke per 30s, B-roll change per sentence, irony throughout.
6. Verdict + forward jab. Soft tail CTA.

**Breakthrough-Narrator (7-11 min):**
1. TITLE: `<known company>'s New AI <action>…<twist>`
2. 0:00 Intriguing development (sentence one).
3. 0:05 Challenge question ("How can an AI…?").
4. 0:15 Establish the problem it solves.
5. Body: rising staircase of demos, each more impressive, "hold onto your papers" between each.
6. Close on the implication (science/society stakes). Soft tail CTA.

---

## 9. Verification checklist (before shipping any ai-dev script)
- [ ] Title names a recognizable company/person (no generic "this AI").
- [ ] Title leads with an emotional verdict and ends on `…` or a post-dash twist.
- [ ] Stakes live by 0:15, fully framed by 0:30; zero intro/throat-clearing.
- [ ] One archetype committed top to bottom (irony OR awe, not both).
- [ ] News-Reactor: ≤7 min, density maxed, joke/30s, B-roll churn. Breakthrough: escalating staircase, accelerating awe.
- [ ] No early CTA; loop stays closed until the verdict/implication.
- [ ] Thumbnail = one recognizable entity + one emotional idea, out-contrasting the feed.
