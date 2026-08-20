# SAMA Project Constitution

**Project:** سامانه جامع املاک «سَما» (SAMA)

**Author / Designer:** سید محمد کریمیان (smk)

**Version:** 1.0

## Purpose

This repository is the source of truth for the SAMA system and its AI Software Factory operating model.

## Non-negotiable principles

1. Approved requirements are authoritative.
2. Version 1.0 requirements are frozen unless changed through a documented Change Request.
3. Critical business rules must be explicit, testable, and traceable.
4. Production SAMA must not depend on external AI services.
5. Expert-report extraction must use internal, rule-based processing; no external AI service and no unnecessary Excel intermediary.
6. Security, data integrity, authorization, and auditability are release-blocking concerns.
7. No critical business logic may live only in frontend code.
8. Changes must be reviewed for regression, race conditions, duplication, data corruption, authorization bypass, SQL injection, XSS, CSRF, IDOR, path traversal, file-upload abuse, and secret leakage.
9. Design quality must not compromise correctness, performance, accessibility, or maintainability.
10. Destructive or ambiguous changes require explicit human approval.

## Development principle

The factory operates as:

DISCOVER → PLAN → DESIGN → IMPLEMENT → TEST → REVIEW → FIX → VERIFY → DOCUMENT → COMMIT

A feature is not considered complete merely because code exists.
