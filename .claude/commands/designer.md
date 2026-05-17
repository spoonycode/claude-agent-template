## Run Design Review

Launch the `/designer` agent to establish design guidelines for a story or epic before UI work begins.

**Usage:** `/designer SCRUM-45` (pass the epic or story key as the argument)

### Steps

1. Take the issue key from the user's argument
2. Delegate to the `designer` agent with the prompt:
   "Review issue {ISSUE_KEY} and produce design guidelines. Read the issue and any linked
   stories from Jira, review existing UI code and design tokens in the codebase, then
   define component patterns, design tokens, accessibility requirements, and visual
   consistency guidelines relevant to this work. Save key decisions to
   `.claude/agent-memory/designer/MEMORY.md` and add a link to the branch or design
   output on the Jira issue — do not add a Jira comment."
3. When the agent completes, summarise what was produced and remind the user to review
   and approve the design output before starting UI story work
