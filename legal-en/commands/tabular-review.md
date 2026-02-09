---
description: Bulk-review multiple legal documents by extracting structured data into an Excel spreadsheet — each document a row, each review question a column
argument-hint: "<document files or folder path>"
---

# /tabular-review -- Tabular Document Review

> If you see unfamiliar placeholders or need to check which tools are connected, see [CONNECTORS.md](../CONNECTORS.md).

Bulk-review multiple legal documents (contracts, NDAs, leases, loan agreements, SPAs, MSAs, etc.) by extracting structured data into an Excel spreadsheet. Each document becomes a row, each review question becomes a column, and every cell contains an extracted answer with a source reference.

**Important**: This command assists with legal workflows but does not provide legal advice. All extracted data and analysis should be reviewed by qualified legal professionals before being relied upon.

## Invocation

```
/tabular-review
```

## Workflow

### Step 1: Accept Documents

Accept documents in any format:
- **Files**: PDF, DOCX, or other document formats (multiple files at once)
- **Folder path**: Directory containing documents to review
- **URL**: Link to a cloud folder, DMS, or virtual data room (VDR)

If no documents are provided, prompt the user to supply them.

If fewer than 2 documents are provided, suggest using `/review-contract` for a single-document review instead.

### Step 2: Inventory

Read each document and create an inventory:
- File name
- Document type (contract, amendment, NDA, power of attorney, etc.)
- Identified parties
- Execution date or effective date

Present the inventory to the user for confirmation before proceeding.

### Step 3: Define Extraction Columns

Determine review columns in collaboration with the user:

**If the user provides specific questions**: Use them directly as columns.

**If the user describes a general goal** (e.g., "due diligence these lease agreements"): Propose a column set based on document type and present for confirmation.

**If the user has a playbook**: Derive columns from standard playbook positions.

Available column types:

| Type | Description | Example |
|------|-------------|---------|
| **Text** | Text extraction | "Governing law" → "New York law" |
| **Date** | Normalized date | "Effective date" → "2024-01-15" |
| **Party/Entity** | Entity name | "Counterparty" → "Acme Corp." |
| **Currency** | Monetary value | "Liability cap" → "$500,000" |
| **Duration** | Time period | "Term" → "36 months" |
| **Yes/No** | Binary finding | "Contains non-compete?" → "Yes" |
| **List** | Multiple items | "Cap exclusions" → "IP infringement; Willful misconduct" |
| **Risk** | GREEN/YELLOW/RED flag | "Liquidated damages" → "YELLOW — no aggregate cap" |

### Step 4: Extract Data

For each document, systematically extract an answer to each column question.

**Extraction rules:**
- **Be concise**: Values should be compact and comparable across rows
- **Be precise**: Extract actual terms, not interpretation
- **Note absence**: Enter "Not addressed" or "Silent" instead of leaving cells blank
- **Flag ambiguity**: E.g., "Unclear — §8.2 references 'reasonable efforts' without defining standard"
- **Include sources**: Note section/clause/page for each value
- **Cross-reference law**: Where applicable, reference governing statutes or regulations

**For Risk columns:**
- **GREEN**: Consistent with market standards and applicable law
- **YELLOW**: Outside preferred position but negotiable; seen in the market
- **RED**: Outside acceptable range; requires escalation — includes potentially unenforceable clauses

If a playbook is available, evaluate against its positions. Otherwise, apply general market standards.

### Step 5: Build the Excel Spreadsheet

Generate an Excel file with the following sheets:

**Sheet 1: "Summary"**
- Title row with review name, date, and document count
- Statistics: risk distribution (GREEN/YELLOW/RED)
- Color legend
- Key findings

**Sheet 2: "Tabular Review" (main)**
- Headers: bold, autofilter, dark blue background (1F4E79), white text
- Frozen pane, alternating row shading, auto-width, text wrap
- Risk columns: GREEN → light green (C6EFCE), YELLOW → light yellow (FFEB9C), RED → light red (FFC7CE)

**Sheet 3: "Sources"** (recommended)
- Source references for each cell from the main sheet

**Sheet 4: "Extraction Parameters"** (metadata)
- List of columns with extraction questions

### Step 6: Verify and Deliver

1. **Completeness**: Every document processed, every column filled
2. **Consistency**: Normalize analogous provisions across the set
3. **Spot-check**: Re-read 2-3 documents and verify extractions

Save the Excel file and present to the user with a concise summary:

```
## Tabular Review — Summary

**Documents reviewed**: [count]
**Review date**: [date]
**Review basis**: [Playbook / General market standards]

### Key Findings

- **RED**: [count] — [brief description of most serious issues]
- **YELLOW**: [count] — [brief description of main negotiation areas]
- **GREEN**: [count] — [confirmation of compliance]

### Next Steps

[Recommendations: deep-dive into flagged documents, adjust risk thresholds, add columns]
```

## Handling Large Document Sets

- **10+ documents**: Process in batches, report progress
- **50+ documents**: Recommend prioritizing a subset, iterative processing for the rest
- **Mixed types**: Group by document type, apply appropriate column sets

## Integration with Other Commands

- Documents flagged as RED can be deep-dived with `/review-contract`
- NDAs in the set can be pre-triaged with `/triage-nda`
- Identified risks can be formally assessed using the `legal-risk-assessment` skill

## Notes

- For sets containing mixed document types, propose separate sheets per type or a superset of columns with "N/A"
- If a playbook is configured in `legal.local.md`, use its risk thresholds; otherwise apply general market standards
- Always remind that extracted data should be verified by a qualified attorney before reliance
- For very long documents (50+ pages each), suggest focusing on key sections first
