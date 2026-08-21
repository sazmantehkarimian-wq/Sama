# SAMA Data Architecture v0.1

## Logical layers
1. Master data: Property, CommercialSpace, Party.
2. Transactional data: Contract, Auction, Approval, Obligation.
3. Historical/evidence data: Appraisal, Document, AuditEvent, StatusHistory.
4. Quality-control data: ReviewItem, validation results, import batches.

## Identity
CommercialSpace has a stable business identifier (space code). Internal database primary keys remain implementation details and must not replace the business identifier.

## History
Business records with legal/operational significance retain history and auditability. Current-state projections may be optimized for reads but must not destroy source history.

## Imports
External spreadsheets are source/import material, not the runtime system of record. Import processing must validate, normalize, detect duplicates/conflicts, preserve provenance and route uncertain records to review.

## Document evidence
Documents are linked to the relevant domain record/workflow and retain provenance and metadata. The original evidence must not be overwritten by extracted values.

## Performance direction
Design for a small internal LAN deployment and weak hardware: normalized transactional writes, targeted indexes, paginated reads, bounded queries and asynchronous processing only where it materially helps without adding unnecessary infrastructure.
