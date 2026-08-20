# SAMA Architecture Principles

## 1. Requirement-first
Architecture exists to implement approved business requirements; it must not invent them.

## 2. Explicit business logic
Critical workflows and rules must be explicit, testable, and independent of presentation.

## 3. Security by default
Authentication, authorization, input validation, secure file handling, auditability, and least privilege are mandatory.

## 4. Data integrity
Use constraints and transaction boundaries to prevent invalid states, duplicates, orphan data, and partial writes.

## 5. Modular design
Separate domains and responsibilities so changes remain localized.

## 6. Internal-first deployment
Optimize for SAMA's internal/LAN environment and weak hardware constraints.

## 7. No production AI dependency
Development may use AI tools; production SAMA must remain independent of external AI services.

## 8. Reversible change
Prefer small, testable, reviewable changes over broad rewrites.
