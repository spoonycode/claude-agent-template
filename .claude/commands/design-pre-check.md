## Design Pre-check

Before starting any story that involves UI or frontend work, verify design guidelines exist:

1. Check `.claude/agent-memory/designer/MEMORY.md` for relevant design tokens, component patterns, or accessibility guidelines
2. If **no design guidelines exist** — STOP. Inform the user that `/designer` must be run
   first to establish design patterns, and that the output needs human approval before
   story work can begin. Do not proceed with UI implementation.
3. If guidelines exist — read them and pass relevant context to `/senior-developer`

The `/designer` agent is run **separately** (not as part of this workflow). It produces
design tokens, component specifications, and agent-memory entries that this workflow consumes.
