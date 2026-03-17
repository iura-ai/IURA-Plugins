# IURA Plugin (NL)

AI-plugin voor Nederlandse juridische teams, ontworpen voor [Cowork](https://claude.com/product/cowork) — werkt ook in Claude Code.

Geïntegreerd met **IURA MCP** — juridische kennisbank voor Nederlands recht (jurisprudentie van Rechtbanken, Gerechtshoven en Hoge Raad).

> **Disclaimer:** Deze plugin ondersteunt juridische werkprocessen maar vormt geen juridisch advies. Verifieer conclusies altijd met gekwalificeerde advocaten.

## Installatie

```
claude plugin install iura-nl@iura-plugins
```

## Skills

| Skill | Omschrijving |
|-------|-------------|
| **iura** | Juridisch onderzoek in het Nederlandse rechtssysteem — zoeken naar jurisprudentie, verifiëren van wetsbepalingen |
| **contract-review** | Contractbeoordeling volgens onderhandelingsplaybook naar Nederlands recht (BW) |
| **nda-triage** | Voorlopige beoordeling van inkomende NDA's — GROEN/GEEL/ROOD-classificatie |
| **nda-generation** | Genereren van NDA-concepten in Word-formaat conform Nederlands recht |
| **legal-memo** | Opstellen van juridische notities met IRAC-analyse naar Nederlands recht |
| **tabular-review** | Massale beoordeling van meerdere juridische documenten in Excel-spreadsheets |
| **conclusie-van-antwoord** | Genereren van een conclusie van antwoord in Nederlandse civiele procedures |

## Structuur

```
iura-nl/
├── .claude-plugin/plugin.json
├── .mcp.json
├── CONNECTORS.md
├── README.md
├── LICENSE
└── skills/
    ├── iura/SKILL.md
    ├── contract-review/SKILL.md
    ├── nda-triage/SKILL.md
    ├── nda-generation/SKILL.md
    ├── legal-memo/SKILL.md
    ├── tabular-review/SKILL.md
    └── conclusie-van-antwoord/SKILL.md
```

## Juridische context

Deze plugin is ontworpen voor Nederlands recht, met verwijzing naar:
- **Burgerlijk Wetboek (BW)** — Nederlands burgerlijk recht
- **Wet bescherming bedrijfsgeheimen (Wbb)** — bescherming van bedrijfsgeheimen
- **Auteurswet (Aw)** — auteursrecht
- **AVG / GDPR** — Algemene Verordening Gegevensbescherming
- **Mededingingswet (Mw)** — mededingingsrecht
- **Wetboek van Burgerlijke Rechtsvordering (Rv)** — burgerlijk procesrecht
- Jurisprudentie van **Hoge Raad**, **Gerechtshoven** en **Rechtbanken**
