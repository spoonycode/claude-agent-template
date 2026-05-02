## Definition of Done — QA

The QA engineer's portion of DoD. You own test validation; do not fix code — file bugs instead.

### Tests
- Unit tests written for all new functions and methods
- Integration tests written where the code touches external systems (APIs, DB, etc.)
- All existing tests pass (`npm test` / `pytest` / equivalent)
- Test coverage does not decrease from the baseline
- Tests cover happy path, edge cases, and expected failure modes
- No tests are skipped or commented out without a documented reason
- Tests are deterministic — no random data or uncontrolled external dependencies

### Acceptance Criteria
- Every acceptance criterion on the Jira ticket has a corresponding test or verified behaviour
- Ambiguous or untestable criteria flagged on the Jira ticket before proceeding

### Reporting
- Test results summarised in a Jira comment (pass count, fail count, coverage delta)
- Any bugs found filed as Jira tickets with clear reproduction steps
