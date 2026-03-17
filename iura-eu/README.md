# IURA Plugin (EU) — Coming Soon

AI plugin for EU law practitioners, designed for [Cowork](https://claude.com/product/cowork) — also works in Claude Code.

Integrated with **IURA MCP** — legal knowledge base for European Union law, covering case law from the highest European courts and the complete EU legislative acquis.

> **Status:** This plugin is currently under development. We're building the MCP connectors, skills, and data pipelines. Stay tuned.

## What's Coming

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

## Planned Skills

| Skill | Description |
|-------|-------------|
| **iura** | Legal research across ECtHR case law, CJEU rulings, and EU legislation |
| **eu-legal-memo** | Legal memoranda with IRAC analysis under EU law — cross-referencing Treaty provisions, secondary legislation, and court jurisprudence |
| **gdpr-compliance** | GDPR compliance analysis — mapping data processing activities against the Regulation, EDPB guidelines, and CJEU/national DPA case law |
| **eu-contract-review** | Contract review focusing on EU regulatory dimensions — competition law (Art. 101-102 TFEU), state aid, data protection, digital services |

## Planned MCP Databases

```
IURA MCP (EU)
├── Search_ECtHR    — European Court of Human Rights rulings (HUDOC)
├── Search_CJEU     — Court of Justice of the European Union (InfoCuria)
├── Search_EU_Leg   — EU Legislation: Treaties, Regulations, Directives, Decisions
└── Read_Document   — Full text of any ruling or legislative act
```

## Why EU Law?

EU law is uniquely challenging for AI-assisted legal research because of its multi-layered structure:

- **Primary law** (Treaties) sets the constitutional framework
- **Secondary law** (Regulations, Directives) creates specific obligations
- **CJEU case law** interprets both — and has supremacy implications for national courts
- **ECtHR case law** adds the human rights dimension that all EU member states must respect

A legal question in any EU member state often requires navigating all four layers simultaneously. IURA MCP will make this cross-referencing seamless.

## Timeline

We're actively building. Follow [@iaborucki](https://x.com/iaborucki) for updates.
