# SAMA Architecture Decision Log

## ADR-001: Independent New Architecture

Decision:
SAMA new development is designed independently. Previous repositories are limited knowledge references only.

Reason:
Maintain comparability between multiple development approaches and avoid accidental inheritance of legacy design choices.

## ADR-002: Domain-first Design

Decision:
Domain model and workflows are defined before implementation.

Reason:
Reduce regression risk and preserve business correctness.

## ADR-003: Historical Data Preservation

Decision:
Important business records are modeled historically instead of being overwritten.

Reason:
Legal and operational traceability requirements.
