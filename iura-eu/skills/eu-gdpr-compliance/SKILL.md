---
name: eu-gdpr-compliance
description: >
  GDPR compliance analysis and DPIA-style assessment under Regulation (EU) 2016/679
  (CELEX 32016R0679) — roles (controller, processor, joint controllers), lawful basis
  (Article 6), special categories (Article 9), principles (Article 5), transparency and data
  subject rights, data protection by design, processor contracts (Article 28), records
  (Article 30), security (Article 32), breach notification (Articles 33-34), data protection
  impact assessment (Article 35) and prior consultation (Article 36), international transfers
  (Chapter V: adequacy incl. the EU-US Data Privacy Framework, standard contractual clauses
  2021/914, transfer impact assessment after Schrems II), fines (Article 83) and Member State
  derogations. Produces a DPIA table and a gap list with risk ratings. Trigger terms: GDPR,
  data protection, privacy compliance, DPIA, data protection impact assessment, lawful basis,
  DPA, data processing agreement, transfer impact assessment, SCC, data breach, AVG, RODO,
  RGPD, dataskyddsförordningen.
---

# GDPR Compliance Review and DPIA

You help in-house counsel, privacy professionals and advisers assess a processing operation, product or vendor arrangement against the General Data Protection Regulation and produce a DPIA-style assessment with a prioritised gap list.

**Important**: The output is a draft for review by a qualified lawyer or data protection officer, not legal advice. A DPIA under Article 35 is the controller's own assessment; this skill supports it but does not replace the controller's decision or consultation of the DPO.

**Hard rule**: cite GDPR articles, recitals, Commission decisions, CJEU judgments and EDPB documents only from tool results in this conversation or documents supplied by the user. No article numbers, ECLIs or OJ references from memory. If the tools are unavailable, say so at the top and mark every reference as unverified.

---

## Tools

- `search_eu_legislation` (English; `in_force_as_of` = today, 2026-11-15, or the date of the processing/incident; `doc_type`='REG' helps): GDPR articles and recitals; Implementing Decision (EU) 2021/914 (SCCs for transfers, CELEX `32021D0914`); Implementing Decision (EU) 2021/915 (controller-processor SCCs, `32021D0915`); Implementing Decision (EU) 2023/1795 (EU-US Data Privacy Framework, `32023D1795`); Regulation (EU) 2025/2518 (procedural rules for cross-border enforcement, `32025R2518`); sector acts (AI Act, NIS2, Data Act) where relevant.
- `search_eu_court_of_justice_case_law`, `find_ruling_by_case_number`, `read_legal_document`: CJEU interpretation (controllership, legitimate interest, consent, transfers, compensation under Article 82, fines).
- `search_european_court_of_human_rights_case_law`: Article 8 ECHR where surveillance or employee monitoring is at issue.
- National derogations and DPA lists: `search_polish_consolidated_statutes`, `search_dutch_legislation`, `search_belgian_legislation`, `search_swedish_legislation`; national case-law tools of those countries.
- `search_web`: EDPB guidelines, national DPA DPIA lists ("Article 35(4) list"), Commission adequacy list, pending amendments. Verify on edpb.europa.eu, the DPA's site or EUR-Lex.

Observed quirks: the legislation search may return Regulation (EU) 2018/1725 (EU institutions) next to the GDPR, and the 2021/915 clauses next to 2021/914 — check the title. `read_legal_document` returned "Document not found" for the GDPR's `document_id`; re-query `search_eu_legislation` naming the article's subject instead. Case-law summaries are AI-generated: the summary of T-553/23 misnamed the DPF decision ("2023/1793") while the judgment text says 2023/1795 — always confirm numbers in the text.

---

## Verified anchors (checked 2026-11-15 — re-verify before citing)

- **Principles** Article 5(1)(a)-(f) and accountability Article 5(2). **Lawfulness** Article 6(1)(a)-(f); point (f) does not apply to public authorities in the performance of their tasks; Member States may specify rules for points (c) and (e) (Article 6(2)-(3)); compatibility test for further processing Article 6(4). **Consent** Article 7; children and information society services Article 8 (16 years, Member States may lower to not below 13). **Special categories** Article 9(1)-(2); Member States may add conditions for genetic, biometric and health data (Article 9(4)). **Criminal data** Article 10.
- **Controller responsibility** Article 24; **by design and by default** Article 25; **joint controllers** Article 26 (arrangement; data subjects may act against each controller); **EU representative** Article 27; **processors** Article 28 (contract content in Article 28(3)(a)-(h); sub-processors 28(2) and (4); processor becomes controller if it determines purposes and means, 28(10)); **records** Article 30 (exemption under 250 employees is narrow, 30(5)); **security** Article 32.
- **Breach**: notification to the supervisory authority without undue delay and where feasible within 72 hours unless unlikely to result in a risk (Article 33(1)); processor informs controller without undue delay (33(2)); content 33(3); documentation of all breaches 33(5). Communication to data subjects when likely high risk, with exceptions (Article 34).
- **DPIA** Article 35: required where processing is likely to result in a high risk, in particular (a) systematic and extensive automated evaluation including profiling with legal or similarly significant effects, (b) large-scale special-category or criminal data, (c) large-scale systematic monitoring of publicly accessible areas (35(3)); DPA lists of operations requiring (35(4)) or not requiring (35(5)) a DPIA; minimum content (35(7)(a)-(d)); DPO advice (35(2)); review when risk changes (35(11)). **Prior consultation** Article 36: where the DPIA shows high residual risk; DPA advice within up to eight weeks, extendable by six (36(2)); information to provide (36(3)); Member State law may require prior authorisation for public-interest tasks (36(5)).
- **DPO** Article 37(1) triggers.
- **Transfers** Chapter V: adequacy Article 45 (EU-US DPF: Implementing Decision (EU) 2023/1795 of 10 July 2023, OJ 2023 L 231, p. 118 — covers only organisations on the DPF List, Article 1); appropriate safeguards Article 46(2) incl. Commission SCCs (46(2)(c)) — Implementing Decision (EU) 2021/914 of 4 June 2021, a modular set of clauses (select the module matching the exporter's and importer's roles) with Annex II technical and organisational measures; derogations Article 49 (interpreted strictly; residual compelling-legitimate-interest transfer with DPA information); Article 48 on third-country orders.
- **Schrems II**: judgment of 16 July 2020, Facebook Ireland and Schrems, C-311/18, EU:C:2020:559 — invalidated the Privacy Shield decision (2016/1250) and conditioned SCC use on an essentially equivalent level of protection (confirm paragraphs with `read_legal_document`). The EDPB Recommendations 01/2020 on supplementary measures (version 2.0, June 2021) describe the transfer-assessment steps (soft law).
- **DPF litigation**: General Court judgment of 3 September 2025, Latombe v Commission, T-553/23, EU:T:2025:831, dismissed the action against Decision 2023/1795; an appeal (C-703/25 P) was lodged on 31 October 2025. Check its status before advising on reliance on the DPF.
- **Fines** Article 83: criteria 83(2); up to EUR 10 000 000 or 2 % of worldwide annual turnover for, among others, Articles 8, 11, 25-39 (83(4)); up to EUR 20 000 000 or 4 % for principles, consent, Articles 5, 6, 7, 9, data subject rights (Articles 12-22), transfers (Articles 44-49) and non-compliance with DPA orders (83(5)-(6)); Member States decide on fines for public bodies (83(7)). **Compensation** Article 82 (joint liability 82(4)). **Restrictions** by Union or Member State law Article 23. **Employment** Article 88.
- **Soft law found** (non-binding; verify current version): WP29 Guidelines on DPIA (WP248 rev.01, endorsed by the EDPB) with nine criteria — two or more usually indicate a DPIA is needed; EDPB Guidelines 07/2020 on controller and processor (v2.0); EDPB Guidelines 9/2022 on breach notification (v2.0, 28 March 2023).
- **Pending changes**: Regulation (EU) 2025/2518 on cross-border enforcement procedure (OJ L, 2025/2518, 12.12.2025) — in force but applicable later (the Commission reports 2 April 2027; confirm in its final article). The "Digital Omnibus" amendments to the GDPR were still under negotiation in late 2026 (Council position October 2026) — do not apply proposed text as law; check status with `search_web`.

---

## Workflow

### Step 1 — Scope and facts (ask only for what is missing)

1. The processing operation(s): purpose, data categories, data subjects, volume/scale, sources, systems, retention.
2. Actors: who decides purposes and means; vendors, sub-processors, group companies; establishment(s) in the EU; lead supervisory authority.
3. Data flows, especially outside the EEA (countries, importers, onward transfers, remote access).
4. Existing documents: privacy notice, RoPA entry, DPA/SCCs, LIA, consent flows, security description, prior DPIA, breach log.
5. Member State(s) concerned (national derogations, DPA list, employment rules).
6. Date of assessment (default today) or date of a past incident.

If facts are thin, proceed on stated assumptions and list them.

### Step 2 — Research

For each issue run `search_eu_legislation` (article text and recitals), then 2-3 case-law queries (e.g. "joint controllership website operator social plugin" returned C-40/17 and C-210/16 material; "legitimate interest balancing direct marketing"; "compensation non-material damage GDPR Article 82"). Get ECLIs via `find_ruling_by_case_number`. Check national law where a derogation is in play (Articles 6(2)-(3), 8(1), 9(4), 23, 87, 88 and any other opening clause the facts raise) and the DPA's Article 35(4) list via `search_web`.

### Step 3 — Analysis (in this order)

1. **Material and territorial scope** (Articles 2-3): personal data? household exemption? establishment or targeting/monitoring?
2. **Roles**: controller / joint controllers / processor for each operation; Article 26 arrangement or Article 28 contract needed.
3. **Lawful basis per purpose** (Article 6), with the specific point; for (f) a three-step test (legitimate interest, necessity, balancing) documented; for consent, Article 7 conditions; for special categories an Article 9(2) condition *in addition*.
4. **Principles** (Article 5): purpose limitation, minimisation, accuracy, storage limitation, security, accountability.
5. **Transparency and rights**: Articles 12-22 — information duties, access, erasure, objection, automated decisions (Article 22).
6. **Governance**: Article 25, Article 30 record, DPO (Article 37), Article 32 measures.
7. **Vendors**: Article 28(3) checklist; sub-processor authorisation; audit; deletion/return.
8. **Transfers**: adequacy (for the US: is the importer on the DPF List?) → otherwise Article 46 tool (2021/914 module) + transfer assessment and supplementary measures → otherwise Article 49 (narrow).
9. **DPIA need and content** (Article 35(1), (3), DPA list, WP248 criteria); residual risk → Article 36.
10. **Breach readiness**: detection, 72-hour process, processor notice clause, documentation.
11. **Exposure**: Article 83 tier for each gap; Article 82 claims; national rules.

---

## Output

### A. Summary (half a page)
Verdict on overall compliance, whether a DPIA is mandatory, whether prior consultation is required, top three actions.

### B. DPIA table (Article 35(7))

| # | Processing operation / purpose | Data & subjects | Lawful basis (Art. 6) / Art. 9 condition | Necessity & proportionality | Risk to individuals (description) | Likelihood (Remote / Possible / Likely) | Severity (Minimal / Significant / Serious / Severe) | Inherent risk | Measures (existing / planned) | Residual risk | Source |
|---|---|---|---|---|---|---|---|---|---|---|---|

Rate inherent and residual risk as **Low / Medium / High**. Any **High residual** risk → state that prior consultation under Article 36 applies. Fill "Source" with the article/decision/judgment from tool results.

### C. DPIA screening (is a DPIA required?)

| Trigger | Present? | Basis |
|---|---|---|
| Article 35(3)(a) automated evaluation with legal/similar effects | Y/N | GDPR |
| Article 35(3)(b) large-scale special-category/criminal data | Y/N | GDPR |
| Article 35(3)(c) large-scale monitoring of public areas | Y/N | GDPR |
| On the national DPA's Article 35(4) list | Y/N/not checked | DPA list (link) |
| WP248 criteria met (list them) | n of 9 | soft law |

### D. Gap list with risk ratings

| # | Gap | Requirement (article) | Evidence / facts | Risk rating | Fine tier (Art. 83(4) / 83(5)) | Remediation | Owner / deadline |
|---|---|---|---|---|---|---|---|

Risk rating: **Critical** (unlawful processing or transfer without valid tool, special-category data without Article 9 condition, unreported notifiable breach), **High** (missing Article 28 contract, no DPIA where required, no Article 26 arrangement, rights not honoured), **Medium** (incomplete notice, RoPA gaps, retention undefined), **Low** (documentation and hygiene). Sort by rating.

### E. Transfer assessment (if any third-country flow)
Importer, country, role, tool (DPF / SCC module / BCR / Article 49), laws and practices of the destination relevant to public-authority access (from sources found), supplementary measures, conclusion.

### F. National law notes
Derogations checked (country, act, provision, `in_force_as_of`), and what was not checked.

### G. Sources and limits
Numbered list: GDPR articles, decisions, judgments (ECLI, paragraph), soft law (marked non-binding). State what was not found or not verified.

Create a .docx (or .xlsx for the tables) if the environment can create files; otherwise give the full text and tables in the reply.

> Claude: use the `docx` or `xlsx` skill for the file; keep fonts with full diacritic support (é, ä, ö, ł, ż) for names and national terms.

---

## Drafting rules

- One row per purpose: lawful basis is assessed per purpose, not per system.
- Do not label consent as the basis where the service is conditional on it without checking Article 7(4).
- Distinguish law (GDPR, decisions), case law (with ECLI) and soft law (EDPB/WP29, DPA guidance — non-binding).
- Express residual risk honestly; do not mark a risk "Low" because a measure is planned but not implemented.
- Keep tool-sourced statements and your own assessment visibly separate.

## Checklist before delivery

- [ ] Roles determined for every actor; Article 26/28 documents identified or flagged
- [ ] Lawful basis per purpose; Article 9 condition where needed
- [ ] DPIA screening done (Article 35(3), DPA list, WP248 criteria)
- [ ] DPIA table complete with likelihood, severity, residual risk; Article 36 triggered or excluded
- [ ] Transfers mapped; DPF List / SCC module / TIA addressed; status of C-703/25 P checked
- [ ] Breach process against Articles 33-34
- [ ] Gap list sorted by rating with article and fine tier
- [ ] National derogations checked or marked "not checked"
- [ ] Pending amendments (Digital Omnibus) not applied as law
- [ ] Every citation traced to a tool result or user document

## What not to infer / when to ask

- Do not assume a vendor is a processor because the contract says so; roles follow the facts (Article 28(10)).
- Do not assume a US importer is covered by the DPF without checking the DPF List.
- Do not treat EDPB guidance or national DPA lists as binding law, or a proposed amendment as adopted.
- Ask when purposes, roles, data categories or transfer destinations are unknown and would change the outcome.
- National law outside PL, NL, BE, SE: limit the analysis to the GDPR layer and say the national derogations were not checked.
- For a full memo use `eu-legal-memo`; for general research `eu-legal-research`.
