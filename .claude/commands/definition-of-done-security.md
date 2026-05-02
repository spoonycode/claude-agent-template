## Definition of Done — Security

The security tester's portion of DoD. You find vulnerabilities — you do not fix them.

### Security Review
- No secrets, API keys, tokens, or credentials in source code or logs
- All user inputs validated and sanitised (OWASP A03 — Injection)
- Authentication and authorisation checks on any new endpoints (OWASP A01, A07)
- Sensitive data not logged, exposed in error messages, or returned unnecessarily (OWASP A02, A09)
- Dependencies from trusted sources and not known-vulnerable
- SQL queries use parameterised statements, never string concatenation (OWASP A03)
- File uploads (if any) validated for type and size
- CORS, rate limiting, and input length limits respected where applicable
- Security misconfigurations checked (headers, env vars, CORS)

### Reporting
- Every finding filed as a Jira bug with severity, location, description, reproduction, and recommendation
- Summary of total findings by severity provided after review
