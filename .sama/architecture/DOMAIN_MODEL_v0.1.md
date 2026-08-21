# SAMA Domain Model v0.1

## Core aggregates
- Property: parent real-estate asset.
- CommercialSpace: independently identified commercial unit; keyed by stable space code.
- Operator: current/historical exploiter or occupant.
- Contract: time-bounded contractual relationship for a commercial space.
- Appraisal: historical expert valuation record; multiple records may exist.
- Auction: lifecycle aggregate for disposal/lease auction processes.
- Approval: managerial/organizational decision record.
- Document: evidence attached to a business record or workflow.
- ReviewItem: unresolved or suspicious data requiring human review.

## Supporting concepts
- Party
- Address/Location
- AuctionParticipant
- AuctionRound
- AuctionEvent
- AuditEvent
- Obligation
- Attachment
- StatusHistory

## Invariants
1. CommercialSpace code is stable and unique within SAMA.
2. Historical appraisal records are append-only from the domain perspective; corrections create auditable revisions rather than silently replacing history.
3. A contract has explicit temporal boundaries and cannot create overlapping active relationships when the governing business rule forbids overlap.
4. Auction state transitions are explicit and authorized; UI visibility never grants authority.
5. Unverified imported data cannot silently become verified master data.
6. Material business changes produce audit evidence.

## Boundary rule
This is an independent new model. Legacy repositories are not implementation sources. Only explicitly authorized business facts may influence it.
