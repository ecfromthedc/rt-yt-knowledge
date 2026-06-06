# rt-yt-knowledge

The **corpus** for the Rising Tides YouTube Growth Arm — the shared brain every operator and every Claude clones to learn what works. This is where reverse-engineering compounds: one operator's teardown becomes every operator's edge.

> If the playbook (`youtube-growth-playbook`) is the *method* and the substrate (`rt-yt-substrate`) is the *machine*, this repo is the *memory*. Empty memory = every operator relearns the same lessons. Fill it.

## Structure

```
rt-yt-knowledge/
├── lanes/                  # per-operator, per-niche knowledge (cross-readable)
│   ├── aviation/           # Glitch
│   ├── history/            # Sam
│   ├── ai-dev/             # John Smathers
│   └── meditation/         # unassigned
│       ├── teardowns/      # competitor channel teardowns
│       ├── script-bible.md
│       ├── hook-patterns.md
│       ├── thumbnail-patterns.md
│       └── rpm-notes.md
├── _templates/             # fill-in templates (teardown, winner-log entry, script bible)
├── winner-log/             # cross-lane log of what over-indexed and why
└── format-library/         # reusable format/structure patterns, lane-agnostic
```

## The two rules

1. **Every teardown uses the template.** Consistency is what makes the corpus queryable by the agent swarm.
2. **Every over-indexer gets a winner-log entry.** When a video pops, the lesson belongs to the whole portfolio, not one operator's head.

## How it's fed
- **Operators** drop teardowns + winner-log entries as they research/ship.
- **The teardown swarm** (agents) proactively tears down target competitors and opens PRs.
- **The substrate** syncs winning patterns back via `/winner-log`, `/teardown`, `/format-extract` skills.
