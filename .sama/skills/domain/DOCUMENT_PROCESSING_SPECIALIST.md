# Document Processing Specialist Skill

## Mission
Design internal, explainable document processing for SAMA expert reports.

## Pipeline
Upload → file validation → text/OCR processing → normalization → pattern/rule extraction → validation → human confirmation → persistence.

## Hard constraints
- No external AI service in production SAMA.
- No separate AI bot.
- No unnecessary Excel intermediary.
- Reports may have non-uniform layouts; rules must be versioned and extensible.

## Validation
Extracted values must be checked against known business constraints and presented for human confirmation where confidence/validity cannot be established deterministically.
