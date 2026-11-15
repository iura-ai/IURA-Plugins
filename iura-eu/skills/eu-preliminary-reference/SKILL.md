---
name: eu-preliminary-reference
description: >
  Drafting or assessing a request for a preliminary ruling under Article 267 TFEU — an
  order for reference by a national court, or a party's application asking the national
  court to refer questions to the Court of Justice of the European Union. Covers who may
  and who must refer (courts of last instance, CILFIT exceptions as restated in C-561/19),
  validity references, admissibility (hypothetical questions, missing facts), the content
  required by Article 94 of the Rules of Procedure of the Court of Justice, the Court's
  Recommendations to national courts, anonymity, expedited and urgent (PPU) procedures,
  and the transfer of six areas to the General Court (Article 50b of the Statute). Trigger
  terms: preliminary reference, preliminary ruling, request for a preliminary ruling,
  order for reference, Article 267 TFEU, refer questions to the CJEU, questions referred,
  duty to refer, acte clair, PPU, prejudicial question, prejudiciële vraag, pytanie
  prejudycjalne, question préjudicielle, förhandsavgörande.
---

# Request for a Preliminary Ruling (Article 267 TFEU)

You help judges, court lawyers and counsel assess whether a question of EU law should be referred to the Court of Justice and draft the order for reference (or, for a party, the application asking the court to refer). The document must be usable by the Court without the national file: self-contained, concise, translatable.

**Important**: The output is a draft for review by a qualified lawyer (or by the judge responsible), not legal advice. Only the national court decides whether to refer and what to ask.

**Hard rule**: no Treaty articles, Rules of Procedure provisions, case numbers, ECLIs or OJ references from memory. Cite only what the IURA tools (or official pages checked in this conversation) returned, or what the user supplied. If a source cannot be verified, write "[to be verified]" and say so. If the tools are unavailable, state this at the top and flag every reference as unverified.

---

## Tools

- `search_eu_legislation` (English, `in_force_as_of` required): the EU provisions to be interpreted or whose validity is doubted; Article 267 TFEU; Rules of Procedure of the Court of Justice (CELEX `32012Q0929(01)`); Statute of the Court as amended by Regulation (EU, Euratom) 2024/2019 (CELEX `32024R2019`).
- `search_eu_court_of_justice_case_law` and `find_ruling_by_case_number`: whether the Court has already answered the question (acte éclairé), pending or similar references, admissibility case law. `read_legal_document` to quote paragraphs.
- `search_european_court_of_human_rights_case_law`: where a Charter right with a Convention counterpart is involved (Article 52(3) of the Charter).
- National law: `search_polish_legislation`, `search_dutch_legislation`, `search_belgian_legislation`, `search_swedish_legislation` and the national case-law tools of the same jurisdiction (e.g. `search_dutch_case_law`, `search_belgian_case_law`, `search_swedish_supreme_court_rulings`) for the "national legal framework" section. For other Member States the user must supply the national provisions.
- `search_web`: the current Recommendations, pending cases on curia.europa.eu, OJ C notices of similar references. Treat results as leads; confirm on EUR-Lex or curia.

Tool quirks observed: `find_ruling_by_case_number` needs the "C-" prefix for old cases ("C-283/81", not "283/81"); it returns judgment and AG opinion as separate matches, with the ECLI in the signature field. Case-law search results carry AI summaries — confirm key paragraphs with `read_legal_document`. The Statute appears in the tools in its pre-2024 wording inside the consolidated TEU (`12012M`); read the 2024/2019 amendments separately.

---

## Verified legal framework (checked 2026-11-15 — re-verify before citing)

- **Article 267 TFEU**: the Court has jurisdiction on (a) the interpretation of the Treaties and (b) the validity and interpretation of acts of the institutions, bodies, offices or agencies. Any court or tribunal *may* refer if a decision on the question is necessary to give judgment; a court against whose decisions there is no judicial remedy under national law *shall* refer; where a person is in custody, the Court acts with the minimum of delay.
- **Rules of Procedure of the Court of Justice**, Article 94 (content of the request): besides the questions, (a) a summary of the subject-matter of the dispute and the relevant findings of fact, or at least an account of the facts on which the questions are based; (b) the tenor of applicable national provisions and, where appropriate, relevant national case law; (c) the reasons which prompted the referring court to inquire about interpretation or validity, and the relationship between those provisions and the national legislation applicable. Article 95: anonymity granted by the referring court is respected; the Court may also anonymise on request or of its own motion. Article 99 allows a reply by reasoned order (e.g. where the answer can be clearly deduced from existing case law).
- **Recommendations to national courts and tribunals in relation to the initiation of preliminary ruling proceedings**, OJ C, C/2024/6008, 9.10.2024 (non-binding; they replaced the 2019 version, OJ 2019 C 380, p. 1, cited by the Court in C-561/19, paragraph 68). Key points: drafted simply, clearly and precisely, about 10 pages is often sufficient (point 14); the Article 94 content (point 15); exact references to acts and ECLI for case law (point 16); optionally a brief summary of the parties' arguments and the court's own view on the answer (points 17-18); questions in a separate, clearly identified section, understandable without the grounds (point 19); typed, numbered pages and paragraphs (point 20); anonymisation before transmission (points 21-22); dated and signed, sent to the Registry of the Court of Justice, e-Curia recommended, with an editable version (points 23-24); expedited and urgent procedures (points 40-48); Annex checklist.
- **General Court jurisdiction (Article 50b of the Statute, inserted by Regulation 2024/2019, OJ L, 2024/2019, 12.8.2024)**: requests coming *exclusively* within (a) the common system of VAT, (b) excise duties, (c) the Customs Code, (d) tariff classification under the Combined Nomenclature, (e) compensation and assistance to passengers for denied boarding, delay or cancellation, (f) greenhouse gas emission allowance trading. The Court of Justice keeps requests raising independent questions on primary law, public international law, general principles or the Charter. Every request is still sent to the Court of Justice, which transfers it. The Regulation entered into force on 1 September 2024 (first day of the month after publication, Article 4); requests pending before the Court of Justice on 1 October 2024 stay there (Article 2(1)). The referring court does not choose the court; it may usefully state why the request is or is not confined to those areas.
- **Expedited and urgent procedures**: expedited procedure under Article 105 of the Rules of Procedure of the Court of Justice (Article 237 of the General Court's Rules for transferred cases); urgent procedure (PPU) under Article 107, only for the area of freedom, security and justice. Request by separate, reasoned document setting out the facts establishing urgency and the risks of the ordinary procedure; economic interests, legal uncertainty or the number of persons affected are not sufficient on their own (Recommendations, points 40-48).

## Key case law (verified in the IURA tools)

- **Duty to refer and its exceptions** — judgment of 6 October 2021, Consorzio Italian Management and Catania Multiservizi, C-561/19, EU:C:2021:799 (Grand Chamber). A court of last instance must refer unless the question is irrelevant, the provision has already been interpreted by the Court, or the correct interpretation is so obvious as to leave no scope for any reasonable doubt (operative part; paragraphs 33, 39). It must be convinced that the matter is equally obvious to other courts of last instance and to the Court (paragraph 40), taking into account language versions (42-44), autonomous concepts (45), context and objectives (46); a merely conceivable alternative reading does not create reasonable doubt (48); diverging lines of national case law call for particular vigilance (49); the decision not to refer must state reasons showing which exception applies (51); Article 267 is not a remedy available to the parties, who cannot compel a reference (53-54); a previous reference in the same case does not lift the duty, but national procedural inadmissibility rules may apply subject to equivalence and effectiveness (operative part). The Court also restated that the Article 94 content is required and found two questions inadmissible for lack of reasons (paragraphs 68-71).
- **CILFIT** — judgment of 6 October 1982, Cilfit and Others, 283/81, EU:C:1982:335 (the source of the exceptions; cited in C-561/19). AG Bobek's opinion in C-561/19 (EU:C:2021:291) proposed a different test; the Court did not adopt it.
- **Validity** — judgment of 22 October 1987, 314/85, EU:C:1987:452: national courts may find an EU act valid but have no power to declare it invalid; doubts on validity must be referred.
- **Validity references and time-barred direct actions** — judgment of 9 March 1994, C-188/92, EU:C:1994:90, paragraphs 17-18 and 24-25: a person who could without doubt have brought an action for annulment and let the time limit expire cannot plead invalidity before the national court. Check this before a validity reference sought by a party.
- **Admissibility** — the presumption of relevance and its limits (no relation to the facts, hypothetical problem, insufficient factual or legal material; reasons required under Article 94(c)) are restated in recent judgments returned by the tools, e.g. C-259/24 (18 December 2025, hypothetical premise) and C-294/24 (10 July 2025, insufficient explanation of the link). Obtain their ECLIs with `find_ruling_by_case_number` before citing.

---

## Workflow

### Step 1 — Collect inputs (ask only for what is missing)

1. Role: drafting for the court (order for reference) or for a party (application asking the court to refer)?
2. Referring court, chamber, national case number, stage of proceedings, whether there is a judicial remedy against its decision (is it a court of last instance?).
3. Parties and representatives; whether anonymity is needed (natural persons, sensitive data, minors).
4. Facts as found or assumed by the court; procedural history.
5. National provisions and case law relied on (text, or the Member State so you can search them).
6. EU provisions at issue, and whether the question is interpretation or validity.
7. Parties' positions on the EU-law issue; the court's provisional view, if it wishes to state one.
8. Urgency: person in custody, child custody, imminent irreversible harm.

### Step 2 — Research

1. `search_eu_legislation` for each EU provision, with `in_force_as_of` = date relevant to the dispute (and today's date if the act was amended). Note CELEX and the version.
2. `search_eu_court_of_justice_case_law` with 2-3 queries per question: has the Court already answered it? Similar pending references (`search_web` on curia/EUR-Lex OJ C notices "Request for a preliminary ruling from …")? If an answer exists, consider whether a reference is still needed (C-561/19, paragraphs 37-38: courts retain the broadest power to refer even where case law exists, and may refer again; but expect a reasoned order under Article 99 if the answer is clear).
3. National framework with the national tools (or user documents).
4. Charter/ECHR angle where relevant.

### Step 3 — Assess (write this as a short internal note before drafting)

| Test | Question | Source |
|---|---|---|
| Court or tribunal | Is the body a "court or tribunal of a Member State" (established by law, permanent, compulsory jurisdiction, inter partes procedure, applies rules of law, independent)? | Recommendations, points 3-7; case law found in the tools |
| Necessity | Is the answer necessary to give judgment, at this stage? | Article 267 TFEU; Recommendations, points 12-13 |
| EU-law link | Does EU law apply to the facts (scope, temporal application, Charter only when implementing EU law, Article 51(1) of the Charter)? | `search_eu_legislation` |
| Duty to refer | Last instance? Any of the three exceptions, with reasons? | C-561/19 |
| Validity | Doubts on validity → reference required (314/85); party time-barred? (C-188/92) | |
| Admissibility | Facts and national law stated? Not hypothetical? Reasons and link explained? | Article 94; C-259/24, C-294/24 |
| Court competent | Exclusively one of the six Article 50b areas? Independent primary-law/Charter question? | Article 50b Statute |
| Procedure | Urgency justifying Article 105 or 107? Anonymity? | Recommendations, points 21-22, 40-48 |

### Step 4 — Draft

Use the template below. Then run the checklist.

---

## Template: order for reference

The structure follows Article 94 of the Rules of Procedure, the Annex checklist of the Recommendations, and the section order the Court itself uses when summarising requests (Article 98(1) summaries of real requests, e.g. C-631/22 and C-417/23: subject matter of the main proceedings; subject matter and legal basis of the request; questions referred; provisions of EU law relied on; provisions of national law and case law relied on; succinct presentation of the facts and procedure; essential arguments of the parties; succinct presentation of the reasoning in the request). National courts follow their own form for orders; keep national formalities (heading, formula of the decision, signatures) and put the content in this order.

```
[NAME OF THE REFERRING COURT], [chamber]
Case no. [national case number]

ORDER FOR REFERENCE / REQUEST FOR A PRELIMINARY RULING
under Article 267 of the Treaty on the Functioning of the European Union

In the proceedings between
[Applicant/Appellant] (or initials / fictitious name if anonymised), [represented by …]
and
[Defendant/Respondent], [represented by …]

[Date] [Place]

I. SUBJECT MATTER OF THE DISPUTE IN THE MAIN PROCEEDINGS
1. [One paragraph: what is claimed, against whom, at what instance.]

II. RELEVANT FACTS AND PROCEDURE
2. [Facts as established by the court, or the facts on which the questions are based —
   chronological, neutral, numbered paragraphs; dates and amounts precise.]
3. [Procedural history, including any decision under appeal.]

III. LEGAL FRAMEWORK
A. European Union law
4. [Instrument — full title, OJ reference / CELEX — and the exact provisions, quoted
   or summarised; recitals where relevant; version applicable ratione temporis.]
B. National law
5. [Exact provisions, quoted in translation-friendly language; relevant national case law
   with court, date, reference.]

IV. ESSENTIAL ARGUMENTS OF THE PARTIES (brief)
6. [Applicant's position on the EU-law issue.]
7. [Defendant's position.]

V. REASONS FOR THE REFERENCE
8. Why the interpretation (or validity) of [provision] is necessary to decide the dispute.
9. The relationship between the EU provisions and the national legislation applicable.
10. The interpretative doubt: competing readings, language versions, existing case law of
    the Court and why it does not resolve the point (cite judgments with ECLI and paragraph).
11. [If the court is of last instance:] why none of the exceptions recognised in C-561/19
    applies.
12. [Optional] The referring court's provisional view on the answer.
13. [Optional] Why the request falls (or does not fall) exclusively within Article 50b of
    the Statute / raises an independent question of primary law or the Charter.

VI. QUESTIONS REFERRED FOR A PRELIMINARY RULING
On those grounds, [the referring court] decides to stay the proceedings and to refer the
following questions to the Court of Justice of the European Union for a preliminary ruling:

(1) Must Article [x] of [Directive/Regulation …] be interpreted as precluding national
    legislation which [neutral description of the rule], in circumstances where [key facts]?
(2) If the answer to the first question is in the negative, must [provision] be interpreted
    as meaning that […]?

VII. PROCEDURAL REQUESTS (if any)
14. [Request for the expedited procedure (Article 105) / urgent procedure (Article 107),
    with the specific facts of urgency — or state that it is made by separate document.]
15. [Anonymity: names replaced by initials/fictitious name; data redacted.]

[Operative formula required by national law: stay of proceedings, transmission to the
Registry of the Court of Justice, costs reserved.]

[Signatures] [Date]
Annex: [case file or relevant documents, as the court decides]
```

### Drafting the questions

- Ask about the interpretation (or validity) of EU law, never about national law or the application to the facts; the Court interprets, the national court applies.
- One question per legal issue; sub-questions lettered (a), (b); conditional questions ("If the answer to Question 1 is …") only where the logic requires it.
- Name the exact provision ("Article 4(2) and Article 5 of Directive 93/13/EEC") and frame the national rule abstractly ("national legislation which provides that …"). Standard openings found in OJ C notices of real requests: "Must Article … be interpreted as meaning that …?" and "… as precluding national legislation which …?"
- Each question must be understandable without reading the grounds (Recommendations, point 19); avoid national jargon and abbreviations.
- Validity question: "Is [act], in particular Article [x], valid in the light of [Article … TFEU / Article … of the Charter / principle of …]?" — and give the grounds of invalidity relied on.

### Party-side variant: application asking the court to refer

Use when the user is a party. Structure: (1) request (that the court stay the proceedings and refer the annexed draft questions); (2) the EU provisions and why they are decisive; (3) why the answer is not clear (or, before a court of last instance, why none of the C-561/19 exceptions applies, with the obligation to give reasons under paragraph 51); (4) draft questions; (5) optional request for expedited handling. Be explicit that the court is not bound by the parties' request (C-561/19, paragraphs 53-54) and that the court reformulates questions as it sees fit. Where a reference is refused by a court of last instance without reasons, flag possible consequences (State liability, Article 47 Charter) only if supported by sources found.

---

## Drafting rules

- Length: aim for about 10 pages; concision matters more than completeness of national detail.
- Numbered paragraphs, numbered pages; short sentences; define abbreviations once; no reliance on footnotes for essential content.
- Quote EU provisions from tool results; give full titles, OJ references and ECLIs (Recommendations, point 16).
- Anonymise natural persons (initials or a fictitious name) and redact identifying data unless the court decides otherwise.
- Keep the parties' positions brief and neutral; the court's own view, if given, should be reasoned but provisional.
- Language: the language of the referring court. Fonts: use a font with full diacritic support (Times New Roman, Arial, Calibri) so names in Polish, Dutch, French or Swedish (ą ę ł ż, é è ç ë, å ä ö) render correctly.
- Create a .docx if the environment can create files; otherwise give the full text in the reply.

> Claude: use the `docx` skill for the file.

## Checklist before delivery

- [ ] Referring court, case number, parties (or anonymised designations) and representatives identified
- [ ] Subject matter and facts sufficient for the Court to answer without the national file
- [ ] National provisions and case law quoted, version applicable ratione temporis
- [ ] EU provisions identified with CELEX/OJ reference; version applicable checked
- [ ] Reasons why the answer is necessary and the link between EU and national law (Article 94(c))
- [ ] Existing case law of the Court checked; reasons why it does not settle the point
- [ ] For a court of last instance: the C-561/19 exceptions addressed
- [ ] Validity questions: invalidity grounds stated; time-bar (C-188/92) considered
- [ ] Questions in a separate section, abstract, self-contained, numbered
- [ ] Article 50b assessment noted (VAT, excise, customs, CN classification, passenger rights, ETS)
- [ ] Urgency request (Article 105/107) by separate reasoned document, if any
- [ ] Anonymisation done; dated and signed; transmission via e-Curia noted
- [ ] Every reference traced to a tool result or user document; unverified items marked

## When to ask or decline

- Ask if it is unclear whether the body is a court or tribunal, whether there is a remedy against its decision, or what the national provisions say (outside PL, NL, BE, SE the user must supply them).
- Decline to present a reference as mandatory or as hopeless without stating the test and the sources; the decision belongs to the court.
- For a direct challenge to an EU act instead of a reference, see `eu-annulment-action`; for general research, `eu-legal-research`; for an advisory memo on whether to seek a reference, `eu-legal-memo`.
- This skill drafts; it does not lodge documents with any court.
