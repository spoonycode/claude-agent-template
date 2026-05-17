## Definition of Done — Developer

The developer's portion of DoD. Tests and security are owned by other agents; do not validate
their sections yourself — just confirm the handoff happened.

### Functionality
- The feature or fix works as described in the acceptance criteria
- Edge cases and error conditions are handled gracefully
- No regressions introduced to existing functionality
- No hardcoded values, magic numbers, or placeholder code left behind

### Code Quality
- Code follows existing conventions in the codebase
- No dead code, unused imports, or console/debug statements
- Linter passes with no errors (`eslint` / `ruff` / equivalent)
- Functions are small and single-purpose
- No duplication where a shared utility could be used instead
- Errors are handled explicitly — never silently swallowed

### Documentation
- Public functions, classes, and modules have docstrings/JSDoc
- README updated if setup steps, env vars, or usage changed
- Inline comments added only for non-obvious logic
- New environment variables documented with purpose and example values
- API changes reflected in API docs or OpenAPI spec
- Architecture or decision notes added to Confluence where relevant

### Handoff
- QA has been delegated to run the test suite and validate acceptance criteria
- Security review has been delegated if auth, input handling, or data storage was touched
- Jira ticket status is up to date; branch linked to the issue
- Commit messages describe what changed and why
