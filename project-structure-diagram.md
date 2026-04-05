# Agent Team — Project Structure

```
agent-team/
│
├── README.md ........................ Framework overview, team intro, rollout plan
├── AGENTS.md ........................ Shared operating rules for all agents
├── PROJECTS.md ...................... Priority dashboard (P0–P3 + Paused)
│
├── agents/
│   │
│   ├── researcher/
│   │   └── SOUL.md ................. 🔬 Curie (Marie Curie)
│   │                                  Research, competitive intel, industry analysis
│   │                                  Serves entire team on demand
│   │
│   ├── architect/
│   │   └── SOUL.md ................. 📐 Da Vinci (Leonardo da Vinci)
│   │                                  System design, tech selection, workflows
│   │                                  "Simple first, always"
│   │
│   ├── marketing/
│   │   └── SOUL.md ................. ✍️  King (Stephen King)
│   │                                  LinkedIn 1x/week, Blog 2x/month
│   │                                  Writes in Clay's authenticated voice
│   │
│   ├── geo/
│   │   └── SOUL.md ................. 🧭 Magellan (Ferdinand Magellan)
│   │                                  Generative Engine Optimization
│   │                                  AI search citation strategy
│   │
│   └── webbuilder/
│       └── SOUL.md ................. ⚡ Edison (Thomas Edison)
│                                      Ecommerce site, brochure, AI chatbot
│                                      "Perfection is the enemy of shipped"
│
└── projects/
    │
    ├── _template/ ................... Copy this to create any new project
    │   ├── PROJECT.md
    │   └── CHANGELOG.md
    │
    └── cdiscovery-main/ ............. P0 — Core business (active)
        │
        ├── PROJECT.md ............... Brief, agent assignments, key decisions
        ├── CHANGELOG.md ............. Decision log
        │
        ├── intel/
        │   ├── research/ ........... Curie writes here
        │   │   ├── voice-profile-clay-cash.md
        │   │   └── linkedin-post-history.md
        │   ├── architecture/ ....... Da Vinci writes here (empty — Week 3)
        │   └── geo/ ................ Magellan writes here (empty — Week 2)
        │
        └── content/
            ├── blog/ ............... King writes here (empty — Week 2)
            ├── linkedin/ ........... King writes here (empty — Week 2)
            └── site/ ............... Edison writes here (empty — Week 4)
```

## File Flow

```
                    ┌──────────┐
                    │  Clay    │
                    │ Directs  │
                    └────┬─────┘
                         │
         ┌───────────────┼───────────────────┐
         │               │                   │
         ▼               ▼                   ▼
   ┌──────────┐   ┌──────────┐        ┌──────────┐
   │  Curie   │   │ Da Vinci │        │ Magellan │
   │ Research │   │ Architect│        │   GEO    │
   └────┬─────┘   └────┬─────┘        └────┬─────┘
        │               │                   │
        │  WRITES       │  WRITES           │  WRITES
        ▼               ▼                   ▼
   intel/research/ intel/architecture/  intel/geo/
        │               │                   │
        │  READS        │  READS            │  READS
        ▼               ▼                   ▼
   ┌──────────┐   ┌──────────┐        ┌──────────┐
   │   King   │   │  Edison  │◄───────│  Edison  │
   │Marketing │   │Web Builder│       │(GEO reqs)│
   └────┬─────┘   └────┬─────┘        └──────────┘
        │               │
        │  WRITES       │  WRITES
        ▼               ▼
  content/blog/    content/site/
  content/linkedin/
```

## What Exists vs What's Coming

| Directory | Status | Agent | Goes Live |
|-----------|--------|-------|-----------|
| intel/research/ | **Has files** | Curie | Week 1 |
| intel/architecture/ | Empty | Da Vinci | Week 3 |
| intel/geo/ | Empty | Magellan | Week 2 |
| content/blog/ | Empty | King | Week 2 |
| content/linkedin/ | Empty | King | Week 2 |
| content/site/ | Empty | Edison | Week 4 |
