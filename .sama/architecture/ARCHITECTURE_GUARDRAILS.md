# SAMA Architecture Guardrails

## Architecture-first rule

Do not implement major business functionality before its domain boundary, data contract, workflow, authorization model, and test strategy are understood.

## Layering

Critical business logic must remain in appropriate backend/domain/service layers and must not depend on presentation-only behavior.

## Data integrity

Use explicit constraints, transactions, validation, idempotency where required, and concurrency controls for high-risk operations.

## Security

Authorization must be enforced server-side. Frontend visibility is not authorization.

## Performance

SAMA is intended for an internal LAN and may run on weak hardware. Prefer simple, efficient architecture; avoid unnecessary services and heavy dependencies.

## Documents

Document processing must support the actual SAMA document formats and use internal rule-based extraction. External AI is prohibited in production.

## UI

SAMA is Persian-first and RTL. Use a reusable design system and professional enterprise interaction patterns. Visual complexity must not reduce operational speed or readability.

## Change control

Architectural changes with material impact require an Architecture Decision Record (ADR).
