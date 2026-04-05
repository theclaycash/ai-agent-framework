# AI Agent Framework — 5-Agent Autonomous Team

A file-based framework for running a team of 5 specialized AI agents that handle research, architecture, marketing, SEO/GEO, and web development for a business. No APIs, no message queues, no orchestration layer. Just files. Each agent reads what it needs, writes what it owns, and stays in its lane.

Built for an ediscovery consulting and software business, but the pattern is reusable for any industry. Fork it, rename the agents, swap in your industry context, and you have your own autonomous team.

## Why File-Based?

Modern AI harnesses — Claude Code, Cursor, Windsurf, Cline, Aider, and others — all understand files natively. They read markdown, follow instructions in context, and write output to disk. This framework leans into that:

- **No vendor lock-in.** SOUL.md files work in any harness that reads project files.
- **No infrastructure.** No databases, no queues, no orchestration servers. Git is your state management.
- **Portable agents.** Move a SOUL.md between harnesses and the agent behaves the same way.
- **Human-readable everything.** Every instruction, every output, every coordination artifact is a markdown file you can read and edit.

Pick whichever harness fits your workflow. Open a session, point it at an agent's SOUL.md, and go.

## The Team

### Curie (Researcher)
**Named after:** Marie Curie — relentless researcher, evidence-obsessed, two Nobel Prizes through methodical investigation.
**Job:** Research anything. Deliver structured briefs with recommendations.
**Serves:** Everyone. Curie is the intelligence backbone.

### Da Vinci (Software Architect)
**Named after:** Leonardo da Vinci — history's greatest systems thinker, architect, engineer, and polymath.
**Job:** Design systems, choose technologies, define workflows.
**Knows:** Clay's stack (.NET, Python, Node.js), ediscovery compliance requirements, "start simple" philosophy.

### King (Marketing Agent)
**Named after:** Stephen King — the most prolific and widely-read author in modern history. Accessible, deep, and relentlessly productive.
**Job:** Write content in Clay's voice for LinkedIn and the blog.
**Schedule:** LinkedIn 1x/week (Tue/Wed), Blog 2x/month (1st and 3rd week).

### Magellan (GEO Agent)
**Named after:** Ferdinand Magellan — the navigator who charted paths others would follow for centuries.
**Job:** Optimize everything for AI search visibility (Generative Engine Optimization).
**Partners with:** King on content, Edison on site architecture.

### Edison (Web Builder)
**Named after:** Thomas Edison — history's most prolific builder. 1,000+ patents through relentless iteration.
**Job:** Build the ecommerce + brochure site with AI product chatbot.
**Implements:** Da Vinci's architecture, Magellan's GEO requirements, King's blog content.

## Directory Structure

```
agent-team/
├── README.md              ← You are here
├── AGENTS.md              ← Shared rules all agents follow
├── PROJECTS.md            ← Project registry & priority dashboard
│
├── agents/                ← Agent identities (global, not project-specific)
│   ├── researcher/
│   │   ├── SOUL.md        ← Curie's identity and instructions
│   │   └── memory/        ← Curie's cross-project learnings
│   ├── architect/
│   │   ├── SOUL.md        ← Da Vinci's identity and instructions
│   │   └── memory/
│   ├── marketing/
│   │   ├── SOUL.md        ← King's identity and instructions
│   │   └── memory/
│   ├── geo/
│   │   ├── SOUL.md        ← Magellan's identity and instructions
│   │   └── memory/
│   └── webbuilder/
│       ├── SOUL.md        ← Edison's identity and instructions
│       └── memory/
│
├── projects/              ← All work happens here, isolated per project
│   ├── _template/         ← Copy this to start a new project
│   │   ├── PROJECT.md
│   │   ├── intel/
│   │   │   ├── research/
│   │   │   ├── architecture/
│   │   │   └── geo/
│   │   ├── content/
│   │   │   ├── blog/
│   │   │   ├── linkedin/
│   │   │   └── site/
│   │   └── CHANGELOG.md
│   │
│   └── cdiscovery-main/   ← Core business (P0)
│       ├── PROJECT.md
│       ├── intel/
│       │   ├── research/
│       │   ├── architecture/
│       │   └── geo/
│       ├── content/
│       │   ├── blog/
│       │   ├── linkedin/
│       │   └── site/
│       └── CHANGELOG.md
```

## How Projects Work

### Full Isolation
Each project gets its own `intel/`, `content/`, and `PROJECT.md`. Research for one project never bleeds into another. Agents work within a project's directory and only reference that project's context.

### Priority Dashboard
`PROJECTS.md` is the single source of truth for what's active and what matters most. Agents check it at session start. Priority levels:

- **P0 (Critical):** Drop everything. Only one P0 at a time.
- **P1 (High):** Active work alongside P0.
- **P2 (Normal):** Steady progress when higher priorities are clear.
- **P3 (Low):** Background only.
- **Paused:** Frozen in place. No active work.

### Adding a New Project
1. Copy `projects/_template/` to `projects/{new-slug}/`
2. Fill in `PROJECT.md`
3. Add a row to `PROJECTS.md`
4. Assign priority and agents

### Shifting Priorities
Update the Priority column in `PROJECTS.md`. That's it. Agents read it at session start and adjust.

## How Agents Coordinate

No APIs. No message queues. Just files — all within the active project directory.

- Curie writes research → Everyone reads it
- King writes blog drafts → Magellan optimizes them → Edison publishes them
- Magellan writes GEO requirements → King and Edison implement them
- Da Vinci writes architecture → Edison builds it

One writer per file. Feedback goes in separate files.

## Compatible Harnesses

This framework works with any AI coding tool that can read project files and follow markdown instructions:

- **Claude Code** — load a SOUL.md as context or point a session at the agent directory
- **Cursor** — use SOUL.md as project rules or reference in chat
- **Windsurf** — same pattern, rules files are natively supported
- **Cline / Roo Code** — pass SOUL.md as system context
- **Aider** — include SOUL.md in the chat context
- **Any LLM with file access** — the pattern is just "read this markdown, follow these instructions"

If your tool can read a file and follow instructions, it can run these agents.

## How to Get Started

**Do not build all five agents on day one.**

### Week 1: Curie (Researcher)
Start with one agent, one project (cdiscovery-main). Ask Curie questions, refine the SOUL.md, build up memory.

### Week 2: King (Marketing) + Magellan (GEO)
Start King on LinkedIn posts. Have Magellan review drafts. Both working within cdiscovery-main.

### Week 3: Da Vinci (Architect)
Feed Da Vinci a real project. Have it produce architecture docs inside cdiscovery-main.

### Week 4: Edison (Web Builder)
By now you have research, content, and architecture flowing. Edison builds the site.

### Week 5+: Add Projects
When a new initiative comes up, create a new project directory. Assign agents. Set priority. The system scales horizontally.

## Making It Yours

1. **Fork this repo**
2. **Rename agents** — pick historical figures (or anyone) who embody the role
3. **Build your voice profile** — feed your AI tool your sent emails and LinkedIn posts, ask it to find patterns. Replace the template in `projects/*/intel/research/voice-profile-*.md`
4. **Swap industry context** — update SOUL.md files with your domain language, audience, and tech stack
5. **Start with one agent** — don't build all five on day one. Start with the researcher, get comfortable, then add the rest

## License

MIT — use it however you want.
