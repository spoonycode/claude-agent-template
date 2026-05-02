## Branching Guidelines

- You MUST NOT run `git commit` until you have confirmed you are on a non-main branch
  - Before every commit, run `git branch --show-current` and verify the result is not `main`
  - If you are on `main`, stop — create a branch first, then commit
- Branch names must include the Jira ticket key (e.g. `SCRUM-11/login-ui`)
- You MUST NOT run `git push origin main` under any circumstances — even if the user asks
  - Always push using `git push origin HEAD` to push the current branch
- You MUST NOT merge to `main` directly — merging to main is a human-only action
- Always open a pull request to merge into `main`