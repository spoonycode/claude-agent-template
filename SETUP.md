# New Project Setup

## Steps

### 1. Copy this template
```bash
cp -r /home/spoon/Projects/_template /home/spoon/Projects/MY-NEW-PROJECT
cd /home/spoon/Projects/MY-NEW-PROJECT
git init
```

### 2. Fill in `.mcp.json`
Open `.mcp.json` and replace all placeholder values:

| Placeholder | Value |
|---|---|
| `YOUR_DOMAIN` | e.g. `wotherspoon` |
| `YOUR_EMAIL@example.com` | your Atlassian account email |
| `YOUR_API_TOKEN` | from https://id.atlassian.com/manage-profile/security/api-tokens |
| `YOUR_JIRA_PROJECT_KEY` | e.g. `MYAPP` |
| `YOUR_CONFLUENCE_SPACE_KEY` | e.g. `MyAppSpace` |

### 3. Fill in `.claude/CLAUDE.local.md`
```
JIRA_PROJECT="MYAPP"
CONFLUENCE_SPACE="MyAppSpace"
ASSIGNEE_EMAIL="your@email.com"
```

### 4. Update `.claude/commands/project-brief.md`
Replace the placeholder text with a 2-3 sentence description of your project.

### 5. Load the MCP server in Claude Code
In Claude Code, run `/mcp` and connect the `jira` server defined in `.mcp.json`.

### 6. Start working
- Run `/architect EPIC-KEY` before starting any story work on a new epic.
- Claude will only see Jira issues and Confluence pages in the scoped project.

---

## What each file does

| File | Purpose |
|---|---|
| `.mcp.json` | Configures the Jira/Confluence MCP server, scoped to this project |
| `.claude/CLAUDE.md` | Orchestration rules — do not edit per project |
| `.claude/CLAUDE.local.md` | **Edit this per project** — project key, space key, assignee email |
| `.claude/agents/*.md` | Agent definitions (architect, dev, designer, QA, security) |
| `.claude/commands/*.md` | Slash commands including DoD checklists and project brief |
| `.claude/settings.local.json` | Pre-approved MCP permissions to reduce prompts |
| `.claude/agent-memory/` | Written by agents during work — do not pre-populate |

## Security note
`.mcp.json` contains your API token. It is gitignored by default. Never commit it.
