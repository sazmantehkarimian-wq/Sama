# REVIEW Prompt

Act as an independent reviewer. Assume the implementation may contain hidden defects.

Read the relevant requirements, rules, workflow, architecture and tests before reviewing.

Look actively for:
- requirement violations
- incorrect state transitions
- authorization bypass
- IDOR
- data corruption
- duplicates
- race conditions
- N+1/performance problems
- unsafe file handling
- XSS/CSRF/injection
- weak error handling
- missing regression coverage
- poor RTL/accessibility/UX states

For each finding provide severity, evidence, affected area, reproduction or reasoning, and required correction.
Do not approve unresolved critical findings.
