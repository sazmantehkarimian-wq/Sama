# SAMA Master Excel Schema Analysis

**Source:** User-provided primary SAMA Excel workbook set, analyzed 2026-08-20.

## Scope
The supplied Excel workbook is treated as the current operational data baseline. It is not automatically treated as a legal requirements specification.

### Master workbook sheets
- 00_شروع
- املاک مادر
- بهره‌برداری سازمانی
- مالکیت و اسناد
- فضاهای مرتبط
- بهره‌برداران فضا
- قراردادها
- کارشناسی‌ها
- مزایده‌ها
- مصوبات و دستورات
- انشعابات و تعهدات
- اسناد
- سوابق و توضیحات
- موارد نیازمند بررسی

### Additional active/out-of-cycle workbooks
- کد فضاهای تجاری فعال
- کد فضاهای از دور خارج شده

## Observed domain structure

```text
Property (ملک مادر)
  └── Commercial Space (کد فضای تجاری)
        ├── Occupant / Beneficiary
        ├── Contract
        ├── Appraisal (historical, multiple records)
        ├── Auction (historical, multiple records)
        ├── Decisions / Orders
        ├── Utilities / Obligations
        ├── Documents
        ├── History / Notes
        └── Data Review Issues
```

## Identity observations
- `شناسه ملک مادر` is a technical reference for the parent property.
- `کد فضای تجاری` is the primary operational reference for commercial-space records and is used as the bridge across most domain sheets.
- The master workbook explicitly describes `فضاهای مرتبط` as the bridge between parent properties and commercial-space codes.
- A commercial-space code must not be silently changed as a side effect of data cleanup.

## Important data-model observations

### 1. Parent property and commercial space are distinct entities
The workbook deliberately separates parent-property data from commercial-space data. The application should preserve this distinction rather than flattening everything into one property table.

### 2. Historical records are first-class data
Appraisals and auctions contain multiple rows for the same commercial-space code. The application must support historical records rather than overwriting a single current value.

### 3. Contracts are temporal
Contract records include dates, status, monetary fields, termination/evacuation fields, investment obligation and document-version status. Contract history must therefore be modeled explicitly.

### 4. Decisions contain semi-structured text
The decisions/orders sheet contains text that may embed dates, letter numbers, amounts and actors. This should be treated as source evidence; deterministic extraction may be added later but must preserve the original text and review state.

### 5. Data-quality review is part of the domain
`موارد نیازمند بررسی` is an explicit operational sheet. Ambiguous mappings are not to be guessed. The future application should have a first-class review queue with reason, evidence, status, reviewer and resolution history.

### 6. Legacy uncertainty must remain visible
Examples observed include unknown beneficiary roles, missing appraisal metadata, unclear contract period amounts, and unresolved property-space mappings. These should not be silently normalized into authoritative values.

## Representative fields observed

### Parent property
- شناسه ملک مادر
- نام ملک / مجموعه
- منطقه شهرداری
- وضعیت ملک
- نوع مرکز
- کاربری اصلی
- گروه کاربری
- مساحت اعیان
- نشانی
- ملاحظات
- تعداد فضای مرتبط
- کدهای فضای مرتبط

### Commercial space bridge
- کد فضای تجاری
- نام فضا / مرکز
- منطقه شهرداری
- گروه / وضعیت فضا
- نام ملک مادر
- شناسه ملک مادر
- وضعیت تطبیق

### Occupant
- کد فضای تجاری
- نام بهره‌بردار / شخص
- نوع نقش
- تاریخ شروع / پایان
- وضعیت رابطه
- توضیحات
- وضعیت بررسی

### Contract
- شماره قرارداد
- تاریخ انعقاد
- تاریخ شروع / پایان
- وضعیت قرارداد
- مبلغ با ارزش افزوده
- وضعیت اقاله
- وضعیت تخلیه
- تعهد سرمایه‌گذاری
- وضعیت نسخه قرارداد
- توضیح دوره مبلغ
- وضعیت بررسی

### Appraisal
- سال
- نوبت
- مبلغ کارشناسی
- نام کارشناس
- مرجع نامه
- تاریخ کارشناسی / گزارش
- وضعیت بررسی

### Auction
- سال
- نوبت
- نتیجه / وضعیت
- مرحله فرایند
- توضیحات

### Decisions / orders
- نوع تصمیم
- تاریخ تصمیم
- شماره نامه
- مرجع جلسه
- متن تصمیم / مصوبه
- وضعیت بررسی

## Architecture consequences
1. Do not model SAMA as one flat spreadsheet/table.
2. Preserve immutable identifiers and historical records.
3. Introduce explicit audit/history where records can change.
4. Introduce a review/issue subsystem rather than silently fixing uncertain legacy data.
5. Preserve source documents/text as evidence alongside normalized values.
6. Build domain services around stateful workflows, especially auction and contract processes.

## Boundary
This document records facts observed in the supplied Excel source. It does **not** approve business rules that are not explicit in the source. Legal/organizational requirements must be confirmed from authoritative requirements and approval documents before implementation.
