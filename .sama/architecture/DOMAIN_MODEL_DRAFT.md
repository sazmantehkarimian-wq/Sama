# SAMA Domain Model — Draft from Workbook Evidence

**Status:** DRAFT / SOURCE-BASED, NOT APPROVED

## Core entities

### ParentProperty
- Identifier: `parent_property_id` (source: شناسه ملک مادر)
- Name
- Municipality region
- Ownership type / owner
- Ownership-document status

### CommercialSpace
- Identifier: `commercial_space_code` (source: کد فضای تجاری)
- Name / center
- Municipality region
- Organizational domain
- Space status
- Space/asset type
- Area and base attributes

### Occupancy / PartyRelation
- Commercial space
- Party/person
- Role
- Start/end dates
- Relationship status

### Contract
- Commercial space
- Contract number
- Contract dates
- Status
- Amount
- Termination/vacate/obligation attributes
- Contract document status

### Appraisal
- Commercial space
- Year
- Round
- Monthly rent appraisal amount
- Expert
- Reference
- Report date
- Review status

### Auction
- Commercial space
- Year
- Round
- Result/status
- Process stage
- Notes

### Decision / Instruction
- Commercial space / parent property context
- Decision type
- Decision date
- Letter/reference
- Meeting reference
- Decision details

### Utility / Obligation
- Commercial space
- Utility/obligation type
- Calculation type
- Amount / percentage
- Standard explanation
- Notes

### Document
- Related entity
- Document type
- Reference number
- Document status
- File location/metadata
- Notes

### HistoryEvent
- Related entity
- Event type
- Event date
- Category
- Description

### DataIssue
- Related entity/key
- Issue type
- Current value
- Expected/target value
- Control description
- Review status

## Relationships observed

`ParentProperty 1..N CommercialSpace`

`CommercialSpace 1..N Occupancy`
`CommercialSpace 1..N Contract`
`CommercialSpace 1..N Appraisal`
`CommercialSpace 1..N Auction`
`CommercialSpace 1..N Decision`
`CommercialSpace 1..N UtilityObligation`
`CommercialSpace 1..N Document`
`CommercialSpace 1..N HistoryEvent`
`CommercialSpace 1..N DataIssue`

## Critical modeling rule
The workbook structure is evidence of data organization, not automatically the final relational/domain model. Final cardinalities, constraints, state transitions and legal rules must be approved from authoritative requirements.
