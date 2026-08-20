# SAMA Quality Gates

A feature may progress only when applicable gates pass.

## Gate A — Requirements

- Requirement identified.
- Business rule identified.
- Acceptance criteria defined.
- No unauthorized requirement change.

## Gate B — Architecture

- Correct module/layer.
- Dependencies understood.
- Data contract defined.
- Security boundary defined.

## Gate C — Data Integrity

- Duplicate handling.
- Transaction boundaries.
- Concurrency behavior.
- Failure recovery.

## Gate D — Security

Check authorization bypass, IDOR, injection, XSS, CSRF, path traversal, file-upload abuse, secret leakage, privilege escalation, and race conditions as applicable.

## Gate E — UX

Check RTL, Persian typography, hierarchy, accessibility, loading/empty/error states, form behavior, tables, navigation, and operational efficiency.

## Gate F — Performance

Check query efficiency, N+1, pagination, memory/CPU impact, file handling, and realistic LAN concurrency.

## Gate G — Regression

Run targeted tests for all affected workflows, APIs, database structures, reports, and UI.

## Release rule

Critical failures block release.
