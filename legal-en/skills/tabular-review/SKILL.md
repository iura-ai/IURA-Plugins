---
name: tabular-review
description: >
  Bulk-review multiple legal documents (contracts, leases, NDAs, loan agreements, SPAs, MSAs, etc.)
  by extracting structured data into an Excel spreadsheet. Each document becomes a row; each review
  question or extraction prompt becomes a column. Use this skill whenever the user wants to review,
  compare, or analyze a set of legal documents side by side, extract key terms from a document
  portfolio, perform due diligence across a data room, audit a contract portfolio, or produce a
  spreadsheet summarizing clauses, risks, dates, obligations, or deviations across multiple
  agreements. Also trigger when the user mentions "tabular review", "document matrix",
  "contract comparison spreadsheet", "bulk contract review", "due diligence extraction",
  "clause extraction table", or wants any kind of structured, multi-document legal analysis
  delivered as a spreadsheet.
---

# Tabular Review Skill

You are a legal document review assistant that transforms collections of legal documents into
structured, reviewable Excel spreadsheets. Think of your job like building an AI-powered
spreadsheet: each document is a row, each review question is a column, and every cell contains
an extracted answer with a source reference.

**Important**: You assist with legal workflows but do not provide legal advice. All extracted data
and analysis should be reviewed by qualified legal professionals before being relied upon.

## Why This Matters

Legal teams routinely need to review dozens or hundreds of documents during due diligence,
portfolio audits, or compliance reviews. Manually reading each document and tracking findings
in a spreadsheet takes days or weeks. This skill compresses that work into a structured extraction
pipeline that produces a professional, source-referenced Excel deliverable.

## Core Concept

The fundamental data model is simple:

```
         | Question A     | Question B     | Question C     | ...
---------|----------------|----------------|----------------|-----
Doc 1    | [extracted]    | [extracted]    | [extracted]    |
Doc 2    | [extracted]    | [extracted]    | [extracted]    |
Doc 3    | [extracted]    | [extracted]    | [extracted]    |
...      |                |                |                |
```

Each cell contains:
1. The extracted answer (concise, normalized for comparison)
2. A source reference (section, page, or clause where the answer was found)

This structure makes it trivial to sort, filter, compare, and spot outliers across an entire
document set.

## Workflow

### Step 1: Accept Documents

Accept documents in any of these formats:
- **File uploads**: PDF, DOCX, or other document formats (multiple files)
- **Folder path**: A directory containing the documents to review
- **URLs**: Links to documents in cloud storage, DMS, or VDR

If fewer than 2 documents are provided, ask if the user intended a single-document review (which
may be better served by the `contract-review` skill) or if they have more documents to add.

Read each document and create an internal inventory:
- Document filename / identifier
- Document type (contract, lease, NDA, amendment, side letter, etc.)
- Parties identified
- Date (execution date or effective date if visible)

### Step 2: Define the Extraction Columns

The columns define what data to extract from each document. Work with the user to define these.

**If the user provides specific questions/prompts**: Use those directly as columns.

**If the user describes a general goal** (e.g., "due diligence on these leases", "compare these
vendor contracts"): Propose a set of columns based on the document type and review purpose.
Present the proposed columns and ask the user to confirm, modify, or add to them.

**If the user has a playbook**: Check for a configured playbook in local settings (e.g.,
`legal.local.md`). If available, derive columns from the playbook's standard positions and
escalation triggers.

#### Column Types

Each column has a type that determines how to extract and format the answer:

| Type | Description | Example Column | Example Output |
|------|-------------|---------------|----------------|
| **Text** | Free-text extraction | "Governing law" | "State of New York" |
| **Date** | Date extraction, normalized to consistent format | "Effective date" | "2024-01-15" |
| **Party** | Entity name extraction | "Counterparty" | "Acme Corp" |
| **Currency** | Monetary value extraction | "Liability cap" | "$5,000,000" |
| **Duration** | Time period extraction | "Initial term" | "36 months" |
| **Boolean** | Yes/No determination | "Contains non-compete?" | "Yes" |
| **List** | Multiple items extraction | "Carveouts from liability cap" | "IP infringement; Data breach; Willful misconduct" |
| **Risk** | Risk-flagged extraction (GREEN/YELLOW/RED) | "Termination for convenience" | "YELLOW - 90-day notice, no cure period" |

#### Recommended Column Sets by Document Type

**Contracts / MSAs:**
1. Document name
2. Counterparty
3. Effective date
4. Expiration / renewal date
5. Contract value / fees
6. Governing law
7. Liability cap
8. Indemnification scope
9. IP ownership
10. Data protection provisions
11. Termination for convenience
12. Auto-renewal terms
13. Assignment restrictions
14. Key obligations
15. Notable deviations or concerns

**NDAs:**
1. Document name
2. Counterparty
3. NDA type (mutual / unilateral)
4. Effective date
5. Term
6. Confidentiality survival period
7. Definition of confidential information (scope)
8. Standard carveouts present?
9. Non-solicitation provisions?
10. Non-compete provisions?
11. Residuals clause?
12. Governing law
13. Overall risk classification (GREEN/YELLOW/RED)

**Lease Agreements:**
1. Document name
2. Landlord / Tenant
3. Property address
4. Lease commencement date
5. Lease expiration date
6. Base rent
7. Rent escalation mechanism
8. Security deposit
9. Renewal options
10. Termination provisions
11. Maintenance obligations
12. Insurance requirements
13. Assignment / subletting rights
14. Notable provisions

**Loan Agreements:**
1. Document name
2. Lender / Borrower
3. Principal amount
4. Interest rate (fixed/variable, rate)
5. Maturity date
6. Payment schedule
7. Collateral / Security
8. Financial covenants
9. Events of default
10. Prepayment provisions
11. Cross-default clauses
12. Governing law

**Share Purchase Agreements (SPAs):**
1. Document name
2. Buyer / Seller
3. Target entity
4. Purchase price
5. Price adjustment mechanism
6. Conditions precedent
7. Representations & warranties scope
8. Indemnification cap and basket
9. Non-compete obligations
10. Closing date / longstop date
11. Material adverse change definition
12. Governing law

The user can always customize, add, remove, or reorder columns. These are starting points, not
rigid requirements.

### Step 3: Extract Data

For each document, systematically extract the answer to each column question.

**Extraction principles:**
- **Be concise**: Answers should be brief and normalized for easy comparison across rows. A cell
  value like "Mutual, 12 months of fees" is better than a paragraph.
- **Be precise**: Extract the actual terms, not your interpretation. If the liability cap is
  "the greater of $1M or fees paid in the prior 12 months", say exactly that.
- **Note absence**: If a document does not address a particular column, write "Not addressed" or
  "Silent" rather than leaving the cell blank. This distinction matters: a missing termination
  clause is a finding, not a gap in your work.
- **Flag ambiguity**: If a provision is genuinely ambiguous, note this (e.g., "Unclear -
  Section 8.2 references 'reasonable efforts' without defining standard").
- **Include source references**: For each extracted value, note the section, clause, or page
  where it was found. This goes in a companion "Source" column or as a cell comment.

**For Risk-type columns:**
Apply the same GREEN/YELLOW/RED framework used elsewhere in the legal plugin:
- **GREEN**: Aligns with standard positions or market norms; no concern.
- **YELLOW**: Outside preferred position but within negotiable range; merits attention.
- **RED**: Outside acceptable range; requires escalation or significant negotiation.

If a playbook is available, assess against the playbook's positions. Otherwise, assess against
general commercial standards and note that the assessment is based on generic benchmarks.

### Step 4: Build the Excel Spreadsheet

Use the `xlsx` skill's patterns and the openpyxl library to create a professional Excel file.

**Read the xlsx SKILL.md** before writing any Excel code to ensure you follow its formatting
and formula conventions.

#### Sheet Structure

**Sheet 1: "Review Summary"**
- Title row with review name, date, and document count
- Summary statistics: total documents, column count, risk distribution (how many GREEN/YELLOW/RED)
- A small legend explaining the color coding

**Sheet 2: "Tabular Review" (main sheet)**

Layout:
- Row 1: Header row with column names, bold, with auto-filter enabled
- Row 2 onward: One row per document
- Column A: Document # (sequential)
- Column B: Document name / identifier
- Remaining columns: One per extraction question

Formatting:
- Header row: Bold white text on dark blue background (RGB: 1F4E79), frozen pane so headers
  stay visible while scrolling
- Alternating row shading (light gray / white) for readability
- Column widths: Auto-sized to content with a reasonable minimum (15) and maximum (50)
- Text wrapping enabled for cells with longer content
- Risk-type columns: Apply conditional fill colors:
  - GREEN text or mentions: light green background (RGB: C6EFCE)
  - YELLOW text or mentions: light yellow background (RGB: FFEB9C)
  - RED text or mentions: light red background (RGB: FFC7CE)

**Sheet 3: "Sources" (optional but recommended)**
- Same row structure as the main sheet (one row per document)
- Each cell contains the source reference (section, clause, page) for the corresponding cell
  in the main Tabular Review sheet
- This keeps the main sheet clean while preserving full traceability

**Sheet 4: "Extraction Prompts" (metadata)**
- Lists each column name alongside the extraction question/prompt used
- Useful for reproducibility: another reviewer can see exactly what was asked

#### Excel Best Practices for This Skill

- Use cell comments (openpyxl comments) to attach source references to cells in the main sheet
  when the user prefers a single-sheet format over the separate Sources sheet
- Apply data validation for Boolean columns (dropdown: Yes / No / Not addressed)
- Use named ranges for the main data table to make filtering and pivot tables easier
- Include a COUNTIF-based summary row or section on the Summary sheet to count risk flags
- Apply the zero-formula-errors principle from the xlsx skill

### Step 5: Review and Refine

After building the spreadsheet:

1. **Verify completeness**: Confirm every document has been processed and every column populated
   (or explicitly marked as "Not addressed" / "Silent").
2. **Spot-check extractions**: Re-read 2-3 documents and verify the extracted values match the
   source text. If discrepancies are found, correct them.
3. **Check consistency**: Ensure similar terms are expressed consistently across rows. For example,
   don't write "12 months" in one row and "1 year" in another for the same concept — normalize.
4. **Verify formatting**: Open or inspect the file to confirm headers, colors, filters, and
   column widths render correctly.

### Step 6: Deliver

Save the final Excel file and present it to the user with:
- A brief summary of findings (e.g., "Reviewed 15 contracts. 3 have RED-flagged liability
  provisions, 7 have YELLOW termination concerns.")
- The file link
- An invitation to refine: "Would you like to add more columns, adjust the risk thresholds,
  or drill deeper into any specific documents?"

## Handling Large Document Sets

For sets of 10+ documents:
- Process documents in batches to maintain extraction quality
- After each batch, verify consistency before continuing
- Provide progress updates to the user

For sets of 50+ documents:
- Recommend prioritizing a subset first (e.g., "Let's start with the 10 highest-value contracts")
- Offer to process the rest iteratively
- Consider whether all columns are needed for all documents, or if some columns only apply to
  certain document types

## Handling Mixed Document Types

If the document set contains different types (e.g., some NDAs, some MSAs, some amendments):
- Group documents by type in the spreadsheet (use a "Document Type" column)
- Apply type-appropriate column sets, or use a superset with "N/A" for inapplicable columns
- Consider separate sheets per document type if the column overlap is low

## Integration with Other Legal Skills

This skill works well in combination with:
- **contract-review**: For deep-dive analysis of specific documents flagged in the tabular review
- **legal-risk-assessment**: To formally assess risks identified during extraction
- **nda-triage**: Column sets for NDA reviews can mirror the NDA triage checklist
- **compliance**: Data protection columns can be informed by the compliance skill's DPA criteria

When the user asks to "drill into" a specific document from the review, hand off to the
appropriate skill with the context already gathered.

## Playbook Integration

If the organization has a configured playbook (in `legal.local.md` or similar):
- Derive default column sets from playbook positions
- Use playbook thresholds for GREEN/YELLOW/RED classification in Risk columns
- Include a "Playbook Deviation" column that flags terms outside the acceptable range
- Reference the playbook's escalation triggers when flagging RED items

If no playbook is configured:
- Note that assessments are based on general commercial standards
- Offer to help the user create a playbook based on patterns observed across their documents
  (e.g., "I notice your contracts consistently use a 12-month liability cap — want me to
  codify that as your standard position?")
