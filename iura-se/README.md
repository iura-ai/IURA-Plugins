# IURA Plugin (SE)

AI-plugin för svenska juristteam, utformad för [Cowork](https://claude.com/product/cowork) — fungerar även i Claude Code.

Integrerad med **IURA MCP** — juridisk kunskapsbas för svensk rätt: lagar och förordningar ur Svensk författningssamling (SFS) i alla historiska lydelser samt avgöranden från Högsta domstolen, Högsta förvaltningsdomstolen, hovrätterna, kammarrätterna, Arbetsdomstolen, Migrationsöverdomstolen, Mark- och miljööverdomstolen och Patent- och marknadsöverdomstolen.

> **Ansvarsfriskrivning:** Pluginen stöder juridiskt arbete men utgör inte juridisk rådgivning. Allt som skillsen producerar är utkast som ska granskas av en behörig jurist innan det används.

## Installation

```
claude plugin install iura-se@iura-plugins
```

## Skills

| Skill | Beskrivning |
|-------|-------------|
| **iura** | Juridisk research i svensk rätt — lagtext (SFS), prejudikat, underrättspraxis, förarbeten |
| **juridisk-pm** | Juridisk PM: fråga, kort svar, bakgrund, rättslig analys, slutsats och rekommendation |
| **avtalsgranskning** | Avtalsgranskning mot organisationens förhandlingsplaybook enligt svensk rätt (AvtL m.m.) |
| **nda-granskning** | Snabb granskning av inkommande sekretessavtal — GRÖN/GUL/RÖD-klassificering |
| **tabellgranskning** | Tabellgranskning av många dokument (due diligence, avtalsportföljer) till Excel |
| **stamningsansokan** | Stämningsansökan i tvistemål enligt 42 kap. rättegångsbalken |
| **svaromal** | Svaromål i tvistemål enligt rättegångsbalken |

## Struktur

```
iura-se/
├── .claude-plugin/plugin.json
├── .mcp.json
├── CONNECTORS.md
├── README.md
├── LICENSE
└── skills/
    ├── iura/SKILL.md
    ├── juridisk-pm/SKILL.md
    ├── avtalsgranskning/SKILL.md
    ├── nda-granskning/SKILL.md
    ├── tabellgranskning/SKILL.md
    ├── stamningsansokan/SKILL.md
    └── svaromal/SKILL.md
```

## Rättsligt sammanhang

Pluginen är utformad för svensk rätt med hänvisning till bl.a.:
- **Rättegångsbalken (1942:740)** — civilprocess
- **Avtalslagen (1915:218)**, **köplagen (1990:931)**, **skadeståndslagen (1972:207)**
- **Lagen (2018:558) om företagshemligheter**
- **Dataskyddsförordningen (GDPR)** och **dataskyddslagen (2018:218)**
- Prejudikat från **Högsta domstolen (NJA)**, **Högsta förvaltningsdomstolen (HFD)** och **Arbetsdomstolen (AD)**
- Förarbeten (**propositioner, SOU, Ds**) som rättskälla
