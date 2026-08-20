# SAMA Workflow Specification

Every critical business process must be represented as an explicit stateful workflow.

## Minimum model
- Actor
- Input
- Preconditions
- Current state
- Allowed transition
- Authorization
- Validation
- Side effects
- Audit event
- Failure behavior
- Recovery/rollback
- Output

## High-risk workflows
- Auction
- Contracts
- Appraisal validity
- Expert report intake/extraction
- Approval flows
- Document/signature processes

UI actions must invoke valid workflow transitions; UI visibility is never authorization.
