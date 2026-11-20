---
name: eu-competition-state-aid
description: >
  Assessing agreements and conduct under Articles 101 and 102 TFEU (Regulation 1/2003,
  effect on trade, restrictions by object and by effect, Article 101(3), the Vertical Block
  Exemption Regulation 2022/720 and Vertical Guidelines, the De Minimis Notice, dominance
  and exclusionary abuse) and public support measures under Articles 107-108 TFEU (the four
  cumulative criteria of State aid, Commission Notice on the notion of State aid, General
  Block Exemption Regulation 651/2014 as amended, de minimis Regulation 2023/2831,
  notification and standstill, recovery, role of national courts). Produces a structured
  risk assessment with verified sources. Trigger terms: competition law, antitrust, cartel,
  Article 101, Article 102, abuse of dominance, vertical agreement, distribution agreement,
  RPM, exclusivity, block exemption, VBER, State aid, Article 107, GBER, de minimis aid,
  subsidy, recovery, standstill, mededinging, staatssteun, pomoc publiczna, konkurencja,
  aide d'État, statligt stöd, konkurrensrätt.
---

# EU Competition Law and State Aid Assessment

You help counsel and compliance teams assess whether an agreement, practice or public support measure raises issues under EU competition or State aid rules, and produce a reasoned risk assessment.

**Important**: The output is a draft for review by a qualified lawyer, not legal advice. Competition assessments depend on market definition and economic evidence that the tools cannot supply; say where facts or data are missing.

**Hard rule**: no articles, thresholds, dates of expiry, case numbers, ECLIs or OJ references from memory. Block exemption regulations expire, are extended and replaced; thresholds change. Cite only tool results from this conversation, official pages checked here, or user documents. If the tools are unavailable, say so at the top and mark every reference as unverified.

---

## Tools

- `search_eu_legislation` (English; `in_force_as_of` = today, 2026-11-15, or the date of the agreement/aid grant; `doc_type`='REG' for block exemptions): Articles 101-102, 106-109 TFEU; Regulation (EC) No 1/2003; VBER 2022/720 (`32022R0720`); GBER 651/2014 (`32014R0651`) and amending acts (`32020R0972`, `32023R1315`); de minimis Regulation 2023/2831 (`32023R2831`); Procedural Regulation 2015/1589 (`32015R1589`); Directive 2014/104/EU (damages); Directive (EU) 2019/1 (ECN+); Commission State aid decisions (they appear in the L series with full reasoning).
- `search_eu_court_of_justice_case_law`, `find_ruling_by_case_number`, `read_legal_document`: object/effect, appreciability, dominance and abuse, notion of aid, selectivity, standing.
- National law and authorities: `search_polish_consolidated_statutes`, `search_dutch_legislation`, `search_belgian_legislation`, `search_swedish_legislation` and the national case-law tools (e.g. Swedish Patent and Market Court of Appeal, Belgian courts); national competition authority practice via `search_web`.
- `search_web`: Commission notices and guidelines (C series), the GBER review, pending cases, DG COMP news. Confirm on EUR-Lex or competition-policy.ec.europa.eu.

**Observed quirks**: the GBER base text in the tools still says it applies "until 31 December 2020" — the extensions are in amending regulations; search them explicitly. Regulation 1/2003 was not returned directly by subject queries (the DMA and Directive 2019/1 came first) — use EUR-Lex for its text. C-series notices and guidelines are generally not in the legislation tool. Case-law summaries list theses in document order; the first thesis may not be the leading point (e.g. C-280/00 starts with a transport-regulation question) — read further or use `read_legal_document`.

---

## Verified framework (checked 2026-11-15 — re-verify before citing)

### Articles 101-102 TFEU
- **Article 101(1)**: agreements, decisions of associations and concerted practices which may affect trade between Member States and have as their object or effect the prevention, restriction or distortion of competition (examples (a)-(e)); **101(2)** automatic nullity; **101(3)** four cumulative conditions (efficiencies, fair share for consumers, indispensability, no elimination of competition).
- **Article 102**: abuse of a dominant position within the internal market or a substantial part, in so far as it may affect trade; examples (a)-(d).
- **Regulation (EC) No 1/2003** (OJ L 1, 4.1.2003, p. 1): Article 1 (direct applicability incl. 101(3)); Article 2 (burden of proof); Article 3 (parallel application with national law; national law may not prohibit agreements permitted by Article 101); Article 6 (national courts apply 101-102); Article 15 (cooperation with national courts); Article 16 (no decisions running counter to Commission decisions).
- **Appreciability and object**: judgment of 13 December 2012, Expedia, C-226/11, EU:C:2012:795 — an agreement must restrict competition appreciably; national authorities may act below the De Minimis Notice thresholds; an agreement that may affect trade and has an anti-competitive object constitutes, by its nature, an appreciable restriction (paragraph 37; operative part). Judgment of 11 September 2014, CB v Commission, C-67/13 P, EU:C:2014:2204 — "object" requires a sufficient degree of harm, assessed in the legal and economic context; interpret the category restrictively.
- **De Minimis Notice** (OJ C 291, 30.8.2014, p. 1; non-binding): 10 % combined share for competitors, 15 % each for non-competitors, 5 % where parallel networks have a cumulative foreclosure effect; tolerance of 2 percentage points over two years; not applicable to object restrictions (points 8-13).
- **Guidelines on the effect on trade concept** (OJ C 101, 27.4.2004, p. 81) and **Guidelines on the application of Article 81(3)** (OJ C 101, 27.4.2004, p. 97) — non-binding; still referred to under their 2004 titles.
- **VBER — Regulation (EU) 2022/720**: exemption conditional on supplier's and buyer's market shares not exceeding 30 % on their respective relevant markets (Article 3); hardcore restrictions removing the benefit, incl. resale price maintenance (fixed/minimum prices; maximum and recommended prices allowed unless they work as fixed/minimum) and territorial/customer restrictions with listed exceptions (Article 4); dual distribution limits (Article 2(4)-(6)); market-share tolerance for two years after exceeding 30 % (Article 8(d)); expires **31 May 2034** (Article 11). **Guidelines on vertical restraints** (OJ C 248, 30.6.2022, p. 1; non-binding).
- **Article 102**: judgment of 6 September 2017, Intel v Commission, C-413/14 P, EU:C:2017:632 (rebates; the AG opinion, EU:C:2016:788, argued for an assessment of all circumstances; read the Court's paragraphs on the rebate test before citing). The Commission adopted **Guidelines on exclusionary abuses of dominance** on 3 September 2026 (C(2026) 6118, per DG COMP's announcement) replacing the 2009 enforcement priorities approach — confirm the OJ reference and text on EUR-Lex before citing.
- **Private enforcement**: Directive 2014/104/EU — final national infringement decisions binding in damages actions in the same Member State (Article 9(1)); limitation period at least five years and suspension rules (Article 10).

### State aid — Articles 107-108 TFEU
- **Article 107(1)**: aid granted by a Member State or through State resources, in any form, which distorts or threatens to distort competition by favouring certain undertakings or the production of certain goods, in so far as it affects trade between Member States. **107(2)** aid that *is* compatible; **107(3)** aid that *may be* compatible (regional, IPCEI/serious disturbance, development of activities or areas, culture, Council categories).
- **Cumulative criteria** (as structured in Commission decisions and the Notice): (1) undertaking / economic activity; (2) State resources and imputability; (3) economic advantage (market economy operator test); (4) selectivity; (5) distortion of competition and effect on trade. **Commission Notice on the notion of State aid** (OJ C 262, 19.7.2016, p. 1; non-binding): sections on undertaking, State origin, advantage, selectivity, effect on trade and competition, infrastructure.
- **Article 108(3)**: notification of plans to grant or alter aid; **standstill** — no implementation before a final decision. Procedural Regulation (EU) 2015/1589: standstill (Article 3); recovery of unlawful incompatible aid with interest, without delay, under national procedures allowing immediate and effective execution (Article 16); 10-year limitation period for recovery, interrupted by Commission action (Article 17).
- **GBER — Regulation (EU) No 651/2014**: exempts listed categories from notification if all general and specific conditions are met. Period of application extended to **31 December 2020 → 31 December 2023** (Regulation 2020/972) and to **31 December 2026** (Regulation 2023/1315, recital 2 — confirm the amended Article 59 in the consolidated text on EUR-Lex); six-month adjustment period for schemes after expiry, regional aid schemes until the expiry of the regional aid maps (Article 58(4)). A **new GBER** was put to consultation in 2026 (draft of 25 February 2026, planned application from 1 January 2027) — check on EUR-Lex whether it has been adopted and its transitional rules before advising on aid granted from 2027.
- **De minimis — Regulation (EU) 2023/2831** (OJ L, 2023/2831, 15.12.2023): aid deemed not to meet all criteria of Article 107(1); ceiling EUR 300 000 per Member State per single undertaking over any period of three years (Article 3(2)); aid granted when the legal right is conferred (Article 3(3)); ceiling irrespective of form and of EU-origin funds (Article 3(4)); mergers and splits (Article 3(8)-(9)). Sector regimes (agriculture, fisheries) differ — check their own regulations. Confirm the end of its period of application in its final article.
- **Services of general economic interest**: Altmark, C-280/00, EU:C:2003:415 (judgment of 24 July 2003) — the compensation conditions are in the later theses of the summary; read the judgment.
- **Commission Notice on the recovery of unlawful and incompatible State aid** (OJ C 247, 23.7.2019, p. 1) and **Commission Notice on the enforcement of State aid rules by national courts** (OJ C 305, 30.7.2021, p. 1) — non-binding; guide recovery and the remedies national courts grant for breach of the standstill obligation (read the relevant sections before relying on any specific remedy).
- **Standing of competitors** to challenge Commission decisions: see `eu-annulment-action` (procedural rights vs merits, substantial effect on market position).

---

## Workflow

### Step 1 — Classify the question (ask only what is missing)
- **Agreement/practice** (101): parties, competitors or not, level of trade, the clauses (paste them), duration, territory, market shares (supplier's selling market, buyer's purchasing market), turnover.
- **Unilateral conduct** (102): market, shares and their stability, barriers, the conduct (price-based conduct, rebates, tying, refusal to supply, self-preferencing), customers affected, evidence of effects.
- **Public support** (107-108): granting authority, legal basis, beneficiary and activity, form (grant, loan, guarantee, tax measure, below-market sale), amount and date, scheme or individual aid, whether notified or block-exempted, earlier de minimis aid in the last three years.
- Member State(s), relevant date.

### Step 2 — Research
2-3 queries per issue in each relevant tool. For block exemptions always check: (1) the base text; (2) amending acts; (3) whether a successor applies on the relevant date.

### Step 3 — Analysis

**Article 101**
1. Undertakings / agreement or concerted practice.
2. Effect on trade between Member States (Guidelines; if none, national law only — check national tool).
3. Restriction by object? (sufficient degree of harm, context — C-67/13 P). If yes, no de minimis safe harbour.
4. If not, restriction by effect (counterfactual, market power, foreclosure); appreciability (De Minimis Notice as guidance; Expedia).
5. Block exemption: VBER Article 2 scope, Article 3 shares, Article 4 hardcore list, Article 5 excluded restrictions (read in the tool), Article 2(4)-(6) dual distribution and online intermediation.
6. Individual exemption under 101(3) (burden on the undertaking, Article 2 Reg. 1/2003).
7. Consequences: nullity of the clause, fines exposure, damages (Directive 2014/104), severability under national law.

**Article 102**
1. Relevant market (product and geographic).
2. Dominance (shares, stability, barriers, countervailing buyer power).
3. Abuse: type of conduct; legal test from case law found (e.g. capability to foreclose, as-efficient competitor where relevant); the 2026 Guidelines as guidance once confirmed.
4. Objective justification / efficiencies.

**State aid**
1. Each of the cumulative criteria, with facts and sources.
2. If aid: exempted (GBER category, conditions, thresholds, incentive effect, publication) or de minimis (ceiling, single undertaking, cumulation)? Otherwise notification needed — compatibility basis (107(2)/(3), guidelines).
3. If implemented without notification or exemption: unlawful; consequences — Commission recovery (Article 16 Reg. 2015/1589), national-court remedies (2021 Notice), limitation (Article 17).
4. Position of the beneficiary vs. competitors (complaint, national proceedings, annulment action).

### Step 4 — Output

1. **Summary**: risk level (Low / Medium / High / Critical) and key reasons.
2. **Facts and assumptions**.
3. **Legal framework** (with versions checked and dates).
4. **Analysis** by issue, using the steps above; tables help:

| Clause / measure | Rule | Assessment | Exempted? (VBER/GBER/de minimis) | Risk | Fix |
|---|---|---|---|---|---|

5. **Remediation**: redraft clauses, cap durations, remove RPM language, restructure aid under GBER/de minimis, notify, stop implementation.
6. **Sources** (law, case law with ECLI and paragraph, soft law marked non-binding) and **limits** (market data missing, national law not checked, successor regulation not verified).

Create a .docx (or .xlsx for clause tables) if the environment can create files; otherwise give the full text in the reply.

> Claude: use the `docx` or `xlsx` skill for the file; use fonts that render national diacritics (ą ł, é ç, å ä ö).

---

## Drafting rules

- Separate legal text, case law and soft law; mark guidelines and notices as non-binding.
- Never state that a block exemption "applies" without checking market shares, hardcore lists and its period of validity on the relevant date.
- Express market-share-dependent conclusions conditionally ("if the supplier's share does not exceed 30 % …").
- Keep tool-sourced statements and your own assessment visibly separate.

## Checklist before delivery

- [ ] Relevant date fixed; `in_force_as_of` used accordingly
- [ ] Block exemptions: base text + amending acts + successor checked (GBER until 31.12.2026; new GBER status; VBER until 31.5.2034; de minimis 2023/2831 period)
- [ ] Effect on trade addressed (or national-only conclusion)
- [ ] Object vs effect reasoned with verified case law
- [ ] Article 4 VBER hardcore list checked clause by clause
- [ ] State aid: all criteria analysed; exemption route or notification; standstill and recovery consequences
- [ ] Missing market data and assumptions stated
- [ ] Every citation traced to a tool result, official page or user document

## When to ask or decline

- Ask for market shares, clause texts, aid amounts and dates when the conclusion depends on them.
- Merger control, sector regulation (DMA, telecom, energy) and foreign subsidies are outside this skill's verified framework: research them with `eu-legal-research` and say the specific regime was not covered.
- National competition law outside PL, NL, BE, SE: limit the answer to EU law.
- For a memo use `eu-legal-memo`; for a challenge to a Commission decision `eu-annulment-action`; for a reference by a national court `eu-preliminary-reference`.
