# IURA Plugin (EU)

AI plugin for EU law practitioners, designed for [Cowork](https://claude.com/product/cowork) — also works in Claude Code.

Integrated with **IURA MCP** — legal knowledge base for European Union law, covering case law from the highest European courts and the complete EU legislative acquis.

> **Disclaimer:** This plugin supports legal work; it does not provide legal advice. Every output is a draft for review by a qualified lawyer.

## Coverage

### Case Law

**European Court of Human Rights (ECtHR / ECHR)**
- Source: [HUDOC](https://hudoc.echr.coe.int/)
- Coverage: Grand Chamber and Chamber judgments
- Convention rights, admissibility, just satisfaction, margin of appreciation
- Searchable by article, keyword, respondent state, and date

**Court of Justice of the European Union (CJEU)**
- Source: [InfoCuria](https://infocuria.curia.europa.eu/)
- Coverage: ~60,000-70,000 court rulings
- Judgments, orders, and opinions from the Court of Justice, General Court, and (historical) Civil Service Tribunal
- Preliminary references (Art. 267 TFEU), direct actions, appeals
- Opinions of Advocates General

### EU Legislation (EUR-Lex)

| Sector | Content |
|--------|---------|
| **Sector 1: Treaties** | TEU, TFEU, Charter of Fundamental Rights, Accession Treaties |
| **Sector 3: Legal Acts** | Regulations, Directives, Decisions, Recommendations, Opinions |

Full legislative texts with consolidated versions, tracking amendments over time.

## Skills

| Skill | Description |
|-------|-------------|
| **eu-legal-research** | EU legal research across EUR-Lex legislation, CJEU and General Court case law, and ECtHR case law, with national-transposition checks |
| **eu-legal-memo** | Objective legal memoranda under EU law — Treaty provisions, secondary legislation and case-law |
| **eu-preliminary-reference** | Drafting or assessing a request for a preliminary ruling under Art. 267 TFEU |
| **eu-annulment-action** | Admissibility and merits assessment of an action for annulment under Art. 263 TFEU, with an application outline |
| **eu-gdpr-compliance** | GDPR compliance analysis and DPIA-style assessment, with a gap list and risk ratings |
| **eu-competition-state-aid** | Assessment of agreements and conduct under Arts 101-102 TFEU and of measures under the State-aid rules (Arts 107-108 TFEU) |

## MCP Tools

```
IURA MCP (EU)
├── search_european_court_of_human_rights_case_law  — European Court of Human Rights rulings (HUDOC)
├── search_eu_court_of_justice_case_law             — Court of Justice of the European Union (InfoCuria)
├── search_eu_legislation                           — EU Legislation: Treaties, Regulations, Directives, Decisions
└── read_legal_document                             — Full text of any ruling or legislative act
```

## Why EU Law?

EU law is uniquely challenging for AI-assisted legal research because of its multi-layered structure:

- **Primary law** (Treaties) sets the constitutional framework
- **Secondary law** (Regulations, Directives) creates specific obligations
- **CJEU case law** interprets both — and has supremacy implications for national courts
- **ECtHR case law** adds the human rights dimension that all EU member states must respect

A legal question in any EU member state often requires navigating all four layers simultaneously. IURA MCP will make this cross-referencing seamless.

