# SAMA Data Source Analysis — 2026-08-20

## Source
User-provided ZIP: `اکسل نهایی اداره املاک و مستغلات.zip`

## Important provenance note
The ZIP was inspected locally. The raw workbook files have not yet been imported into GitHub. This document records verified observations from that inspection; it is not a replacement for the source workbooks.

## Files found
- `(سما )املاک مادر .xlsx`
- `(سما) کد فضاهای از دور خارج شده.xlsx`
- `(سما) کد فضاهای تجاری فعال.xlsx`
- `~$MA_Final_Requirements_Review_v0.9_1405-05-20.docx` — Office temporary file; NOT treated as an authoritative requirements document.

## Active commercial spaces workbook
Sheets observed:
- `00_شروع`
- `فضاها`
- `بهره‌برداران`
- `قراردادها`
- `کارشناسی‌ها`
- `مزایده‌ها`
- `مصوبات و دستورات`
- `انشعابات و تعهدات`
- `اسناد`
- `سوابق و توضیحات`
- `موارد نیازمند بررسی`

The workbook explicitly states that `کد فضای تجاری` is a fixed identifier and should not change. It is used to connect contracts, appraisals, auctions and related records.

## Parent properties workbook
Sheets observed:
- `مالکیت و اسناد`
- `فضاهای مرتبط`
- `بهره‌برداران فضا`
- `قراردادها`
- `کارشناسی‌ها`
- `مزایده‌ها`
- `مصوبات و دستورات`
- `انشعابات و تعهدات`
- `اسناد`
- `سوابق و توضیحات`
- `موارد نیازمند بررسی`

The `فضاهای مرتبط` sheet is explicitly described as the main bridge between a parent property and a commercial-space code. Parent properties use identifiers such as `P-0001`.

## Observed domain entities / relationships
- ParentProperty (`شناسه ملک مادر`)
- CommercialSpace (`کد فضای تجاری`)
- Occupant / Party
- Contract
- Appraisal
- Auction
- Decision / Instruction
- Utility / Obligation
- Document
- History / Event
- DataIssue / ReviewItem

Primary relationship observed:
`ParentProperty 1..N CommercialSpace`

CommercialSpace is the operational anchor for many child records:
`CommercialSpace 1..N Occupancy, Contract, Appraisal, Auction, Decision, Utility, Document, History`

## Observed appraisal fields
The active workbook contains fields including:
- commercial space code
- year
- round/sequence (`نوبت`)
- monthly appraisal amount (`مبلغ کارشناسی اجاره ماهانه (ریال)`)
- expert name
- appraisal letter/reference
- appraisal/report date
- review status

This confirms that appraisal is a historical, multi-record domain rather than a single current value.

## Observed auction fields
The active workbook contains:
- commercial space code
- year
- round/sequence
- auction result/status
- auction process stage
- notes

Examples in the source include multiple auction rounds and stages such as a two-stage auction. The current workbook is therefore a source for history, but it is NOT sufficient by itself to define the complete auction state machine or legal rules.

## Data quality model
Both workbooks contain dedicated `موارد نیازمند بررسی` sheets. The source text explicitly says unresolved values must not be guessed and should be reviewed/resolved. This is an important domain requirement for the future data-quality subsystem.

## Architecture implications
1. `CommercialSpace.code` should be treated as an immutable business identifier, subject to the formal requirements document.
2. `ParentProperty.id` should be a distinct entity identifier.
3. Historical records should not overwrite prior appraisal/contract/auction events.
4. Data-quality issues need first-class persistence and workflow, not just spreadsheet notes.
5. Documents should be modeled as records linked to domain entities, with file metadata and auditability.
6. Auction requires a real state machine rather than a single status field.
7. Appraisal requires version/history semantics and validity rules.

## Not yet concluded
- Exact cardinalities and legal constraints
- authoritative approval matrix
- exact auction rules
- RBAC matrix
- required database technology
- exact document extraction rules
- final UI information architecture

These must be derived from the authoritative requirements/approval documents before implementation.
