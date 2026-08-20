# SAMA Security Gate

Security review is release-blocking for critical findings.

## Required review areas

- Authentication and session security
- Server-side authorization / RBAC
- IDOR and privilege escalation
- SQL injection
- XSS
- CSRF where applicable
- Path traversal
- File-upload abuse
- Secret leakage
- Mass assignment
- Race conditions
- Duplicate submissions
- Sensitive data exposure
- Audit integrity

## Evidence requirement

Do not approve with statements such as "looks secure". Record the tested scenario, expected behavior, observed behavior, and remediation status.
