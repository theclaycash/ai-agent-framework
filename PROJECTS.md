# PROJECTS.md — Project Registry & Priority Dashboard

This is the single source of truth for what the team is working on, in what order.

## Active Projects

| Priority | Project | Slug | Status | Focus Agents | Notes |
|----------|---------|------|--------|-------------|-------|
| 🔴 P0 | cDiscovery Main Site & Business | `cdiscovery-main` | Active | All | Core business — always active |

## Priority Levels

- **🔴 P0 — Critical:** Drop everything. All agents prioritize this project.
- **🟠 P1 — High:** Active work. Agents dedicate scheduled time to this project.
- **🟡 P2 — Normal:** Steady progress. Work on this between P0/P1 tasks.
- **🔵 P3 — Low:** Background. Only pick up when higher priorities are clear.
- **⚪ Paused:** On hold. No active work. Preserve state for when it resumes.

## Priority Rules

1. **When Clay shifts priority**, update this table immediately. The table IS the priority.
2. **Agents check this file at session start** to know what to work on.
3. **Only one project can be P0 at a time.** Multiple P1s are fine.
4. **Paused projects keep their full state.** Nothing gets deleted — just frozen.
5. **New projects start at P2** unless Clay says otherwise.

## How to Add a New Project

1. Create directory: `projects/{slug}/`
2. Copy the template: `cp -r projects/_template/* projects/{slug}/`
3. Fill in `PROJECT.md` with the project brief
4. Add a row to the table above
5. Assign priority and focus agents

## How to Shift Priority

Update the Priority column in the table above. That's it. Agents read this file at session start and adjust accordingly. If a project moves to Paused, agents stop all scheduled work on it but preserve everything in place.

## Project History

Track major priority shifts here so the team has context on why things moved.

| Date | Change | Reason |
|------|--------|--------|
| 2026-04-05 | Created registry. cdiscovery-main set as P0. | Initial setup |
