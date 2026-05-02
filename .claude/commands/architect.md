## Run Architecture Review

Launch the `/architect` agent to review an epic and produce architecture guidelines.

**Usage:** `/architect SCRUM-45` (pass the epic key as the argument)

### Steps

1. Take the epic key from the user's argument
2. Delegate to the `architect` agent with the prompt:
   "Review epic {EPIC_KEY} and produce architecture guidelines. Read the epic and all
   linked stories from Jira, review the current codebase, then write a Confluence page
   covering architecture overview, technology choices, implementation patterns, Azure
   production architecture, and constraints for other agents. Save key decisions to
   `.claude/agent-memory/architect/MEMORY.md` and comment on the epic with a link to
   the Confluence page."
3. When the agent completes, summarise what was produced and remind the user to review
   and approve the Confluence output before starting story work
