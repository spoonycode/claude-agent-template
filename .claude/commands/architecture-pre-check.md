## Architecture Pre-check

Before starting any story, verify the parent epic has approved architecture guidelines:

1. Read the epic linked to the story in Jira
2. Check `.claude/agent-memory/architect/MEMORY.md` for a matching epic entry
3. If **no guidelines exist** — STOP. Inform the user that `/architect` must be run on
   the epic first, and that the output needs human approval before story work can begin.
   Do not proceed with implementation.
4. If guidelines exist — read them and pass relevant context to each agent you delegate to

The `/architect` agent is run **separately** (not as part of this workflow). It produces
Confluence documentation and agent-memory entries that this workflow consumes.
