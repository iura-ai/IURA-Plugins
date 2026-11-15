---
name: eu-annulment-action
description: >
  Assessing and outlining an action for annulment under Article 263 TFEU before the General
  Court — reviewable acts, standing (addressee, direct and individual concern under Plaumann,
  regulatory acts not entailing implementing measures under Inuit), the two-month time limit
  with the 14-day publication and 10-day distance extensions, the four grounds of review,
  jurisdiction and appeal, effects (Articles 264, 266), interim relief (Articles 278-279),
  plea of illegality (Article 277), the national-court route via Article 267 (TWD limits) and
  representation. Produces an admissibility and merits assessment and an application outline
  following the General Court's model application and Practice Rules. Trigger terms: action
  for annulment, Article 263, annul Commission decision, challenge EU act, General Court
  application, direct and individual concern, locus standi, plea in law, form of order sought,
  nietigheidsberoep, skarga o stwierdzenie nieważności, recours en annulation, talan om
  ogiltigförklaring.
---

# Action for Annulment (Article 263 TFEU)

You help counsel decide whether an EU act can be challenged directly before the EU Courts, assess admissibility and the prospects on the merits, and prepare the outline of an application in the form the General Court expects.

**Important**: The output is a draft for review by a qualified lawyer, not legal advice. Before the EU Courts a party other than a Member State or institution must be represented by a lawyer authorised to practise before a court of a Member State or EEA State (Article 19 of the Statute); this skill does not lodge anything.

**Hard rule**: no Treaty articles, Rules of Procedure provisions, time limits, case numbers, ECLIs or OJ references from memory. Cite only tool results from this conversation, official pages checked here, or documents the user supplied. Time limits are fatal: every date calculation must show its inputs and be confirmed by the responsible lawyer. If the tools are unavailable, say so at the top and mark everything unverified.

---

## Tools

- `search_eu_legislation` (English, `in_force_as_of` = date of the contested act and today): Articles 256, 263-266, 277-279 TFEU; the contested act and its legal basis; Rules of Procedure of the General Court (CELEX `32015Q0423(01)`); Practice Rules for the implementation of the Rules of Procedure of the General Court (CELEX `32024Q02097`); Rules of Procedure of the Court of Justice (`32012Q0929(01)`) and Practice directions to parties (`32024Q02173`); Statute of the Court and Regulation (EU, Euratom) 2024/2019.
- `search_eu_court_of_justice_case_law`, `find_ruling_by_case_number`, `read_legal_document`: standing, reviewable act, grounds, similar challenges, pending cases.
- `search_european_court_of_human_rights_case_law`: where Article 47 of the Charter / Article 6 ECHR arguments matter.
- `search_web`: OJ C notices of actions against the same act ("Action brought on … – … v Commission"), curia case status, the General Court's model documents.

Observed quirks: the Rules of Procedure of the General Court come back in the 2015 wording (e.g. references to telefax); the current consolidated version (2024) and the Practice Rules (amended 28.4.2025, OJ L 2025/810) are on curia.europa.eu — check there. Article 263 is also returned from the EC Treaty (Article 230 EC) and the 2008/2012 TFEU texts; cite the TFEU. `find_ruling_by_case_number` needs "C-25/62", not "25/62". Case-law summaries are AI-generated: confirm holdings in the text.

---

## Verified framework (checked 2026-11-15 — re-verify before citing)

**Reviewable acts — Article 263, first paragraph, TFEU**: legislative acts; acts of the Council, Commission and ECB other than recommendations and opinions; acts of the Parliament and European Council intended to produce legal effects vis-à-vis third parties; acts of bodies, offices and agencies intended to produce such effects.

**Applicants**
- Privileged (second paragraph): Member States, Parliament, Council, Commission.
- Semi-privileged (third paragraph): Court of Auditors, ECB, Committee of the Regions, to protect their prerogatives.
- Natural and legal persons (fourth paragraph): (1) acts addressed to them; (2) acts of direct and individual concern to them; (3) regulatory acts of direct concern to them that do not entail implementing measures. Acts setting up agencies may lay down specific conditions (fifth paragraph).

**Individual concern — Plaumann**: judgment of 15 July 1963, Plaumann v Commission, 25/62, EU:C:1963:17 — persons other than addressees are individually concerned only if the decision affects them by reason of attributes peculiar to them or circumstances differentiating them from all other persons, distinguishing them individually just as the addressee; a commercial activity that may be practised by anyone does not suffice (text read in `read_legal_document`).

**Regulatory act — Inuit**: judgment of 3 October 2013, C-583/11 P, EU:C:2013:625 — upheld the General Court's finding that "regulatory act" covers acts of general application other than legislative acts; legislative acts remain subject to direct and individual concern (confirm the Court's paragraph numbers in the text before citing; the AG opinion is EU:C:2013:21). "Does not entail implementing measures" is read in the light of the aim of not forcing an individual to break the law to obtain access to a court; where implementing measures exist (EU or national), protection lies in challenging those measures: T-818/16, EU:T:2018:274 (16 May 2018) and C-313/19 P, EU:C:2020:869 (28 October 2020). Direct concern: the act directly affects the applicant's legal situation and leaves no discretion to those implementing it (General Court reasoning recited in C-583/11 P).

**State aid standing** (examples returned by the tools): a competitor may challenge a decision not to raise objections to safeguard its procedural rights as an interested party, but to challenge the merits it must show a substantial effect on its market position (e.g. T-135/17, 6 May 2019; T-79/16, 15 October 2018). Confirm ECLIs with `find_ruling_by_case_number`.

**Time limit — Article 263, sixth paragraph, TFEU**: two months from publication, from notification to the applicant, or, failing both, from the day the applicant learned of it.
- If the time limit runs from publication in the OJ, it is calculated from the end of the 14th day after publication (Article 59 of the Rules of Procedure of the General Court; Article 50 of the Rules of Procedure of the Court of Justice).
- Extension on account of distance: a single period of 10 days (Article 60 GC Rules; Article 51 CJ Rules).
- Calculation (Article 58 GC Rules / Article 49 CJ Rules): the day of the event is not counted; months end on the same date in the last month (or the last day of that month); weekends and holidays are included and the period is not suspended during vacations; if it ends on a Saturday, Sunday or official holiday it is extended to the end of the next working day.
- For an addressee, time normally runs from notification; where an act is both notified and published, or the applicant only learned of it later, research the case law on the starting point before relying on a later date.

**Grounds — Article 263, second paragraph, TFEU**: lack of competence; infringement of an essential procedural requirement (incl. statement of reasons, Article 296 TFEU, right to be heard); infringement of the Treaties or of any rule of law relating to their application (incl. Charter, general principles, manifest error of assessment); misuse of powers.

**Jurisdiction — Article 256(1) TFEU**: the General Court hears at first instance actions under Articles 263, 265, 268, 270 and 272 except those reserved to the Court of Justice by the Statute; its decisions may be appealed to the Court of Justice on points of law only. Appeal grounds (Article 58 Statute): lack of competence of the General Court, breach of procedure adversely affecting the appellant, infringement of EU law; no appeal on costs alone. Appeals against interim orders: two months (Article 57 Statute). For appeals concerning boards of appeal of the agencies listed in Article 58a of the Statute (as amended by Regulation 2024/2019, incl. EUIPO, ECHA, EASA, SRB, EBA, ESMA, EIOPA), the appeal must first be allowed to proceed.

**Effects**: the act is declared void; the Court may state which effects remain definitive (Article 264 TFEU). The institution must take the necessary measures to comply (Article 266 TFEU). General Court decisions annulling a regulation take effect only after the appeal period or dismissal of an appeal (Article 60 Statute).

**Interim relief**: actions have no suspensory effect, but the Court may order suspension (Article 278) or other interim measures (Article 279). Apply by separate document, showing urgency (serious and irreparable harm) and a prima facie case (fumus boni juris), with weighing of interests (the Court of Justice's Practice directions, point 24, describe the same requirements for its own procedure). Check the General Court's Rules of Procedure for the current article numbers.

**Plea of illegality — Article 277 TFEU**: notwithstanding the expiry of the Article 263 time limit, any party may, in proceedings where an act of general application is at issue, plead its inapplicability on Article 263 grounds. It is incidental: it does not create a free-standing action.

**National route and Article 267**: where direct standing is lacking, the act can be contested through national proceedings against implementing measures, with a request for a preliminary ruling on validity (national courts cannot declare EU acts invalid: 314/85, EU:C:1987:452). Limit: a person who could undoubtedly have brought an annulment action and let the time limit expire cannot plead invalidity before the national court — judgment of 9 March 1994, C-188/92, EU:C:1994:90, paragraphs 17-18 and 24-25. See `eu-preliminary-reference`.

**Representation — Article 19 Statute**: Member States and institutions by an agent; other parties by a lawyer authorised to practise before a court of a Member State or EEA State. Lodge the lawyer's certificate and authority to act (Article 51(2)-(3) GC Rules, referred to in Article 78(4)).

**Content of the application — Article 76 GC Rules**: (a) applicant's name and address; (b) status and address of the representative; (c) the main party against whom the action is brought; (d) subject-matter, pleas in law and arguments, and a summary of the pleas; (e) form of order sought; (f) evidence produced or offered, where appropriate. Annexes (Article 78): the contested act (Article 21 Statute), proof of existence in law for a legal person, the representation documents. A notice is published in the OJ (Article 79).

**Practice Rules of the General Court (OJ L 2024/2097, 12.8.2024, consolidated 2025)**: maximum 50 pages for the application in direct actions other than staff and IP cases (point 156); table of contents if over five pages (point 110); A4, common font at least 12 pt (footnotes 10 pt), single line spacing, margins at least 2.5 cm, paragraphs numbered consecutively, pages numbered (point 109); arguments in the body, not in footnotes or annexes (points 111, 120); exact references to legislation (date, publication, temporal applicability) and to case law with case name, number, ECLI and paragraph (point 113); schedule of annexes A.1, A.2 … with description, pages and paragraph of first mention (points 114-115); introduction followed by a brief account of the facts (point 163); form of order at the beginning or the end (point 164); arguments grouped by plea, each plea with a heading and a summary statement (point 165); a separate summary of pleas of at most two pages in the language of the case, following the online model, sent via e-Curia (points 167-168); a table of applicants if more than ten (point 169); all procedural documents lodged exclusively through e-Curia (point 121).

---

## Workflow

### Step 1 — Inputs (ask only for what is missing)
1. The contested act: author, date, reference (e.g. C(2025) …), publication (OJ reference) or notification date and how notified.
2. The client: identity, legal form, seat; relationship to the act (addressee, competitor, beneficiary, association, member of a closed class).
3. What the act does to the client legally (not only economically); any implementing measures (EU or national), discretion of implementing authorities.
4. Administrative procedure: participation, complaint, comments, access to file.
5. Urgency and harm (for interim measures).
6. Parallel proceedings: national litigation, other actions against the same act (OJ C notices), pending appeals.

### Step 2 — Research
- The act and its legal basis (`search_eu_legislation`; Commission decisions often appear in the results in the L series with their recitals).
- Standing case law for the type of act (State aid, competition, trade defence, restrictive measures, agency decisions).
- Substantive case law per plea.
- `search_web` for actions already brought against the same act and their pleas.

### Step 3 — Admissibility assessment (table)

| Condition | Assessment | Sources | Risk |
|---|---|---|---|
| Reviewable act (binding legal effects, not preparatory/confirmatory) | | | |
| Applicant category | | | |
| Addressee / direct concern / individual concern (Plaumann) / regulatory act without implementing measures (Inuit) | | | |
| Interest in bringing proceedings (existing and current) | | | |
| Time limit: start date, +14 days if from OJ publication, +2 months, +10 days distance, weekend/holiday rule → **last day** | | Art. 263(6) TFEU; Arts 58-60 GC Rules | |
| Court competent (General Court / Court of Justice) | | Art. 256 TFEU | |
| Alternative route (national courts + Art. 267) and TWD risk | | C-188/92 | |

Show the deadline calculation step by step; recommend filing well before the last day.

### Step 4 — Merits assessment
For each candidate plea: the rule (verified source), the facts supporting it, the institution's likely answer, the standard of review (full review vs. limited review of complex economic or technical assessments — source it), and a rating **Strong / Arguable / Weak**. Drop weak pleas or merge them; the Court prefers a few precise pleas.

### Step 5 — Output
1. Executive summary: admissible? deadline? prospects per plea? interim relief? recommendation (bring the action / national route / complaint / do nothing).
2. Admissibility table; deadline computation.
3. Merits table.
4. Application outline (below) and draft summary of pleas.
5. Sources and open points.

---

## Template: application (General Court, direct action)

Structure mirrors the General Court's indicative "Model application for direct actions other than those relating to intellectual property rights" (September 2024) and the Practice Rules; adapt headings to the case.

```
APPLICATION

[Name of applicant], [address / registered office]
                                                            Applicant
represented by [name], [lawyer / avocat / advocaat …], [address]

v

[European Commission / Council / agency], [address]
                                                            Defendant

UNDER ARTICLE 263 TFEU
FOR: annulment of [Commission Decision C(…) final of [date] on …] [(OJ …)]

TABLE OF CONTENTS
INTRODUCTION
FACTS
LEGAL CONTEXT
[ADMISSIBILITY — optional section where standing or the time limit is not obvious]
FIRST PLEA IN LAW, ALLEGING [infringement of …]
SECOND PLEA IN LAW, ALLEGING [infringement of an essential procedural requirement …]
…
FORM OF ORDER SOUGHT
SCHEDULE OF ANNEXES

INTRODUCTION
1. [Contested act, what it decides, why the applicant challenges it — one page at most.]

FACTS
2. [Brief, chronological, each fact supported by an annex: "(Annex A.3)".]

LEGAL CONTEXT
n. [Legal basis of the act and relevant provisions, with OJ references.]

ADMISSIBILITY
n. [Reviewable act; standing (addressee / direct and individual concern / regulatory act);
   interest; time limit with dates.]

FIRST PLEA IN LAW, ALLEGING [state the plea]
n. [Summary statement of the plea.]
n. [First part … second part … — rule, application, conclusion; case law cited as
   "judgment of [date], [name], C-…/…, EU:C:…:…, paragraph …".]

FORM OF ORDER SOUGHT
ON THOSE GROUNDS, THE APPLICANT CLAIMS THAT THE COURT SHOULD:
– annul [the contested act] [in its entirety / in so far as …];
– [in the alternative, annul Article … / reduce the fine — only where the Treaty or the act
  confers unlimited jurisdiction];
– order the [defendant] to pay the costs.

[Place, date] [Signature of the lawyer]

SCHEDULE OF ANNEXES
| Annex no. | Description (date, author, addressee) | First and last page | First mentioned in § |
| A.1 | Contested decision, [date] | 1-25 | § 1 |
```

Form of order: state it identically at the beginning and end if you use both places (model application note). Do not ask for declarations or orders the Court cannot give in annulment proceedings (e.g. ordering the Commission to adopt a specific act); seek damages only through a separate head of claim under Article 268 TFEU if justified.

### Separate summary of pleas (max. two pages, Practice Rules points 167-168)

Following the Court's "Model summary of the pleas in law and main arguments", which mirrors the notice published in the OJ ("Action brought on [date] – [Applicant] v Commission (Case T-…/…)"):

```
I.   PARTIES
     Applicant(s): …   Seat: [town, country]   Representative(s): …   Defendant(s): …
II.  SUBJECT MATTER
     Application under Article 263 TFEU for annulment of [reference to the contested measure]
III. FORM OF ORDER SOUGHT
     The applicant claims that the Court should:
     – annul …;
     – order the defendant to pay the costs.
IV.  PLEAS IN LAW AND MAIN ARGUMENTS
     In support of the action, the applicant relies on [number] pleas in law.
     1. First plea in law, alleging [that the Commission …].
        – [main argument] – [main argument]
     2. Second plea in law, alleging …
```

### Interim measures (if needed)
Separate application lodged with or after the action: subject-matter, urgency (specific, evidenced, serious and irreparable harm), prima facie case per plea, balance of interests, precise measures requested.

---

## Drafting rules

- Few, well-built pleas; each plea one legal ground; parts numbered.
- Every factual assertion linked to an annex; arguments in the body (annexes are generally not translated).
- Clear, translation-friendly language; avoid national legal jargon; define abbreviations.
- Cite case law with case name, number, ECLI and paragraph — only from tool results.
- Respect the 50-page limit; ask for authorisation to exceed only for particularly complex cases (Article 75(2) GC Rules).
- Language of the case: chosen by the applicant among the official languages (verify rules for the case type). Use fonts supporting all diacritics (ą ł ż, é ç ë, å ä ö).
- Create a .docx if the environment can create files; otherwise give the full text in the reply.

> Claude: use the `docx` skill for the application and summary.

## Checklist before delivery

- [ ] Contested act identified precisely (reference, date, publication/notification)
- [ ] Reviewable act; applicant category and standing argued with verified case law
- [ ] Deadline computed step by step (2 months, +14 days if OJ publication, +10 days distance, weekend/holiday rule) and flagged for lawyer confirmation
- [ ] Each plea maps to an Article 263(2) ground, with sources and a strength rating
- [ ] Alternative route (national court + Article 267; TWD risk) considered
- [ ] Interim relief assessed (urgency, fumus, balance of interests)
- [ ] Form of order sought precise and within the Court's powers; costs claimed
- [ ] Schedule of annexes (A.1 …), contested act, proof of existence, lawyer's certificate and authority
- [ ] Page limit, format and e-Curia requirements of the Practice Rules met
- [ ] Separate two-page summary of pleas prepared
- [ ] Every reference traced to a tool result, official page or user document

## When to ask or decline

- Ask for the notification/publication date and the method of notification before saying anything about the deadline; if unknown, give the calculation method only.
- If the deadline may already have expired, say so plainly and look at alternatives (Article 277 incidentally, national route, new act, complaint, damages under Article 268).
- Do not promise admissibility for non-addressees; present the Plaumann and Inuit tests with the facts and the risk.
- For general research use `eu-legal-research`; for a reference from a national court `eu-preliminary-reference`; for State aid and competition substance `eu-competition-state-aid`.
- This skill prepares drafts; it does not file documents or contact the Registry.
