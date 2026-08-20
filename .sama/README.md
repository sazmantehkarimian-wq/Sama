# SAMA AI Software Factory

This directory defines the controlled engineering operating system for SAMA.

The factory separates project truth (requirements, rules, architecture) from execution roles (agents/skills) and release controls (QA/security/release).

## Operating loop

DISCOVER → PLAN → DESIGN → IMPLEMENT → TEST → REVIEW → FIX → VERIFY → DOCUMENT → COMMIT

## Source-of-truth hierarchy

1. Approved SAMA requirements and project constitution
2. Approved business rules and workflows
3. Architecture decisions
4. Design system / Figma design source
5. Implementation
6. Tests and evidence

Lower layers must not silently override higher layers.
