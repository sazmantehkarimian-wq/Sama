# SAMA Domain Model v1 Draft

Status: Draft
Source: Approved project knowledge + operational data analysis

## Core Aggregates

### Property
Represents parent real-estate records.

### Commercial Space
Represents operational commercial units linked to a property.

Key concepts:
- Stable space code
- Current and historical states
- Documents
- Related contracts
- Appraisals
- Auctions

### Operator
Represents entities/persons using or managing commercial spaces.

### Contract
Time-bound legal relationship between space and operator.

### Appraisal
Historical valuation records. Multiple appraisals may exist for one space.

### Auction
A controlled workflow entity with explicit states, participants, approvals and audit history.

### Document
Evidence attached to business entities.

### Review Queue
Handles incomplete, ambiguous or suspicious data requiring human review.

## Design Principles

- Preserve history instead of overwriting facts.
- Business state transitions must be explicit.
- Critical decisions require audit evidence.
- UI is not an authorization boundary.
- This model is independent from previous implementations.
