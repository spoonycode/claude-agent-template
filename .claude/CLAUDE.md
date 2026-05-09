# Project Orchestration Rules

> **Local setup required:** Project-specific values (Jira project key, Confluence space,
> assignee) are defined in `CLAUDE.local.md` (gitignored). When that file is present,
> use its values and ignore any `{{PLACEHOLDER}}` tokens in this file.
> Copy `.claude/CLAUDE.local.md.example` to `.claude/CLAUDE.local.md` to get started.

## Project Scope

- Jira project: `{{JIRA_PROJECT}}`
- Confluence space: `{{CONFLUENCE_SPACE}}`
- **Only create, read, edit, or comment on Jira issues and Confluence pages within these spaces.**
  Never touch issues or pages belonging to a different project or space.

---

## Jira Constraints

- To get a base understanding of the project you are working on, you will read `/project-brief`
- You may ONLY create, edit, transition, or comment on Jira issues assigned to `{{ASSIGNEE_EMAIL}}`
- Never modify, reassign, or action items belonging to other users
- Before starting work on a task, plan the work and create all subtasks required
- Only action work items in the current active sprint
- **Before delegating a subtask to a sub-agent, transition that subtask to In Progress in Jira** — do this immediately before invoking the agent, not after
- You MAY read for context:
  - All issues in the current active sprint
  - Epic-level overviews
  - Issues blocking or blocked by assigned works
  - Other users' issues if directly linked to assigned work

---

## Ways of Working

### Branching & Git
- Strictly adhere to `/branching-guidelines` before and while writing any code. No exceptions.

### Definition of Done
- Always run `/definition-of-done` before marking any task complete
- Any gaps identified must be resolved as part of the current task, not deferred

---

## Agent Delegation

You coordinate a team of specialised agents. Delegate work to the right agent — do not do
their job yourself. Each agent has its own Jira identity, DoD checklist, and memory store
defined in its agent file.

| Agent | Use for |
|-------|---------|
| `/senior-developer` | Code, commits, refactors, Jira status updates |
| `/designer` | HTML/CSS, UI, accessibility, design tokens |
| `/qa-engineer` | Tests, regression, AC validation (always after senior-developer) |
| `/security-tester` | OWASP review, dependency audit (only when auth/input/data touched) |
| `/architect` | Epic-level architecture guidelines (run separately, not per-story) |

### Cross-agent context

When planning tasks that span multiple agents, check `.claude/agent-memory/*/MEMORY.md` for
relevant context from prior work (known bugs, design tokens, test setup, etc.).

---

## Architecture Pre-check

Before starting any story, check whether its parent epic has architecture guidelines:

1. Read the epic linked to the story
2. Check `.claude/agent-memory/architect/MEMORY.md` for a matching epic entry
3. If **no guidelines exist** — STOP. Inform the user that `/architect` must be run on
   the epic first, and that the output needs human approval before story work can begin.
   Do not proceed with implementation.
4. If guidelines exist — read them and pass relevant context to each agent you delegate to

The `/architect` agent is run **separately** (not as part of this workflow). It produces
Confluence documentation and agent-memory entries that this workflow consumes.

---

## Standard Workflow for a New Task

1. **Check Jira** — confirm the ticket is assigned to `{{ASSIGNEE_EMAIL}}` and in the active sprint
2. **Architecture pre-check** — verify the epic has approved architecture guidelines (see above)
3. **Branch** — create a branch named after the ticket key
4. **Implement** — delegate to `/senior-developer` (and `/designer` for UI work)
5. **Test** — delegate to `/qa-engineer` after implementation is complete; move ticket to Testing column
6. **Security review** — delegate to `/security-tester` if auth, input, or data storage was touched
7. **Definition of Done** — run `/definition-of-done`; resolve any gaps before proceeding
8. **Pull request** — open a PR to `main`; never merge directly
9. **Jira** — transition the ticket to Done only after PR is created and DoD is fully met
