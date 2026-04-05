# cdiscovery.ai — 5-Agent Autonomous Team

```
                          ┌─────────────────────┐
                          │     🧑 CLAY CASH     │
                          │   Owner / Operator   │
                          │  Directs & Reviews   │
                          └──────────┬──────────┘
                                     │
            ┌────────────┬───────────┼───────────┬────────────┐
            │            │           │           │            │
            ▼            ▼           ▼           ▼            ▼
   ┌──────────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────────┐
   │ 🔬 CURIE     │ │📐DA VINCI│ │ ✍️ KING   │ │🧭MAGELLAN│ │ ⚡ EDISON    │
   │ Researcher   │ │ Architect│ │ Marketing│ │   GEO    │ │ Web Builder  │
   │ Marie Curie  │ │ Leonardo │ │ S. King  │ │Ferdinand │ │ T. Edison    │
   └──────┬───────┘ └────┬─────┘ └────┬─────┘ └────┬─────┘ └──────┬───────┘
          │              │            │             │              │
          │ WRITES       │ WRITES     │ WRITES      │ WRITES       │ WRITES
          ▼              ▼            ▼             ▼              ▼
   ┌──────────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────────┐
   │  intel/      │ │  intel/  │ │ content/ │ │  intel/  │ │  content/    │
   │  research/   │ │architec- │ │  blog/   │ │  geo/    │ │  site/       │
   │              │ │  ture/   │ │linkedin/ │ │          │ │              │
   └──────────────┘ └──────────┘ └──────────┘ └──────────┘ └──────────────┘
```

---

## Agent Roles

| Agent | Named After | What They Do | Cadence |
|-------|-------------|-------------|---------|
| **Curie** | Marie Curie | Research, competitive intel, industry analysis | On demand — serves entire team |
| **Da Vinci** | Leonardo da Vinci | System design, tech selection, workflows | On demand |
| **King** | Stephen King | LinkedIn posts, blog content, Clay's voice | LinkedIn 1x/week, Blog 2x/month |
| **Magellan** | Ferdinand Magellan | AI search visibility, citation optimization | Supports King + Edison |
| **Edison** | Thomas Edison | Ecommerce site, brochure, AI chatbot | Implements architecture |

---

## How They Feed Each Other

```
  CURIE ─────research briefs────▶ KING (data for content)
    │                              │
    ├───tech recommendations──▶ DA VINCI
    │                              │
    └───UX insights───────────▶ EDISON ◀──blueprints── DA VINCI
                                   ▲
  MAGELLAN ──optimization──────▶ KING
    │                              │
    └───technical GEO reqs────▶ EDISON ◀──hosts────── KING's blog
```

---

## File-Based Coordination

No APIs. No message queues. Just files.

```
  One writer per file.  Everyone can read.

  agent-team/
  ├── AGENTS.md .................. Shared operating rules
  ├── PROJECTS.md ................ Priority dashboard (P0-P3)
  │
  ├── agents/
  │   ├── researcher/
  │   │   ├── SOUL.md ........... Curie's identity
  │   │   └── memory/ ........... Cross-project learnings
  │   ├── architect/
  │   │   ├── SOUL.md ........... Da Vinci's identity
  │   │   └── memory/
  │   ├── marketing/
  │   │   ├── SOUL.md ........... King's identity + Clay's voice
  │   │   └── memory/
  │   ├── geo/
  │   │   ├── SOUL.md ........... Magellan's identity
  │   │   └── memory/
  │   └── webbuilder/
  │       ├── SOUL.md ........... Edison's identity
  │       └── memory/
  │
  └── projects/
      ├── _template/ ............. Copy to create new project
      └── cdiscovery-main/ ....... P0 — core business
          ├── PROJECT.md ......... Brief + status
          ├── CHANGELOG.md
          ├── intel/
          │   ├── research/ ..... Curie writes here
          │   ├── architecture/ . Da Vinci writes here
          │   └── geo/ .......... Magellan writes here
          └── content/
              ├── blog/ ......... King writes here
              ├── linkedin/ ..... King writes here
              └── site/ ......... Edison writes here
```

---

## Priority System

| Level | Meaning | Behavior |
|-------|---------|----------|
| **P0** | Critical | Drop everything |
| **P1** | High | Active work alongside P0 |
| **P2** | Normal | Steady progress |
| **P3** | Low | Background only |
| **Paused** | Frozen | No work until reactivated |

---

## Rollout Plan

```
  Week 1 ──▶ Curie only (research on cdiscovery-main)
  Week 2 ──▶ King + Magellan (content + GEO)
  Week 3 ──▶ Da Vinci (real architecture project)
  Week 4 ──▶ Edison (build the site)
  Week 5+ ──▶ Scale horizontally (add new projects)
```

---

## The Rule

Every agent, every output, every piece of content passes the same test:

**If it reads like a marketing department wrote it, it's wrong.**
**If it reads like a smart friend who works in your industry told you something useful, it's right.**
