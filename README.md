# rt-yt-knowledge

Knowledge corpus for the Rising Tides YouTube long-form growth lab.

Per `rt-yt-substrate`, this repo owns:

- **Channel teardowns** — niche intelligence, competitive comps, RPM bands, asset feasibility
- **Format library** — replicable video templates and script skeletons
- **Prompt evolutions** — versioned prompt history per stage
- **Tool evals** — production-tool comparisons and stack decisions

Every Claude that needs the corpus clones this repo. Postgres (`rt-yt-automations`) remains the source of truth for pipeline *state*; this repo holds the durable *knowledge*.

## Layout

```
rt-yt-knowledge/
├── teardowns/      ← niche + channel teardowns (one .md per niche)
├── formats/        ← format library (templates, script skeletons)   [tbd]
├── prompts/        ← prompt evolutions per stage                     [tbd]
└── tool-evals/     ← production-tool comparisons                     [tbd]
```

## Teardowns

| Niche | Lane owner | RPM band | Status |
|---|---|---|---|
| [AI / Software-Dev](teardowns/ai-dev-niche.md) | Sam | $10–14 ($18+ on SaaS/dev-tool) | Draft |

Teardown format: TL;DR call → channel comps → RPM bands → sub-lane map → asset feasibility (vs our stack) → strike risk → SEO/topics → format templates → evergreen-vs-trending math → path to monetization → name candidates → launch recipe → repo placement.
