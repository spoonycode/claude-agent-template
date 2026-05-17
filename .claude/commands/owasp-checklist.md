## OWASP Review Checklist

For every security review, check for:

- OWASP Top 10 vulnerabilities
- Injection flaws (SQL, command, XSS, XXE)
- Broken authentication or session management
- Insecure direct object references
- Sensitive data exposure (secrets, tokens, PII in logs or responses)
- Missing or misconfigured authorisation checks
- Insecure dependencies (run dependency audit via Bash)
- Security misconfigurations (CORS, headers, environment variables)
- Insecure file operations or path traversal risks

For every finding, file a Jira bug with:
- **Title**: clear description of the vulnerability
- **Severity**: Critical / High / Medium / Low
- **Location**: file path and line number(s)
- **Description**: what the vulnerability is and why it is dangerous
- **Reproduction**: how to trigger it
- **Recommendation**: what needs to be fixed (do not write the fix yourself)

Every finding must be a Jira ticket — do not surface findings only in chat.
