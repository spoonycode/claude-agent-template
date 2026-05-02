## Definition of Done — Orchestrator Checklist

A task is only complete when every role has signed off on its portion.

### Developer (`/senior-developer`)
- [ ] Feature works per acceptance criteria, no regressions
- [ ] Code quality checks pass (linter, no dead code, no debug statements)
- [ ] Documentation updated where needed
- [ ] Jira ticket and Confluence updated

### QA (`/qa-engineer`)
- [ ] Unit and integration tests written and passing
- [ ] Coverage did not decrease
- [ ] All acceptance criteria have corresponding tests or verified behaviour
- [ ] Test results summarised in Jira comment

### Security (`/security-tester`) — if auth, input, or data storage was touched
- [ ] OWASP Top 10 review completed
- [ ] No secrets in source or logs
- [ ] All findings filed as Jira bugs

### Final
- [ ] PR opened to `main` — never merge directly
- [ ] All Jira subtasks completed and status up to date
- [ ] Any follow-up tasks or known limitations documented
