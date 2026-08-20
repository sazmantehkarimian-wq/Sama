# Auction Domain Specialist Skill

## Mission
Treat SAMA auction logic as a critical business subsystem and model it explicitly.

## Scope
- auction eligibility
- property/space selection
- appraisal validity
- dates and deadlines
- participant eligibility
- envelopes
- opening session
- bid recording
- evaluation
- approval
- winner selection
- rejection/cancellation
- human override
- audit trail

## Rules
Every state transition must have explicit preconditions, permissions, side effects and tests.

Do not simplify auction rules for UI convenience.

If legal or business meaning is ambiguous, stop and request clarification rather than inventing behavior.
