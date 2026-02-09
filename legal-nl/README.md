# Juridische Plugin (NL) — Nederlandse Rechtspraktijk

AI-plugin voor Nederlandse juridische teams, ontworpen voor [Cowork](https://claude.com/product/cowork) — werkt ook in Claude Code. Automatiseert contractbeoordeling, NDA-triaging, compliance workflows, juridische briefing en gestandaardiseerde antwoorden — alles configureerbaar naar het playbook en risicotolerantie van uw organisatie.

> **Disclaimer:** Deze plugin ondersteunt juridische workflows maar vormt geen juridisch advies. Controleer altijd conclusies met gekwalificeerde juristen. AI-gegenereerde analyses moeten worden beoordeeld door bevoegde advocaten voordat ze worden gebruikt voor juridische beslissingen.

## Doelgroep

- **Commercieel Jurist** — Contractonderhandelingen, leveranciersbeheer, transactieondersteuning
- **Product Jurist** — Productbeoordelingen, algemene voorwaarden, privacybeleid, IP-aangelegenheden
- **Privacy / Compliance** — AVG (GDPR), DPA-beoordelingen, verzoeken van betrokkenen, regelgevingsmonitoring
- **Litigatie Ondersteuning** — Bewaarbesluiten, documentbeoordeling, zaakbriefings
- **Due Diligence** — Bulk documentbeoordeling, extractie van belangrijke bepalingen

## Installatie

```
claude plugins add iura-ai/iura-plugins/legal-nl
```

## Commando's

### `/review-contract` — Contractbeoordeling

Beoordeel een contract tegen uw organisatie-negotiatieplaybook. Markeert afwijkingen, genereert redlines en biedt bedrijfsimpactanalyse.

### `/triage-nda` — NDA Pre-screening

Snelle triage van binnenkomende NDA's: GROEN (standaard goedkeuring), GEEL (beoordeling nodig), ROOD (significante problemen).

### `/vendor-check` — Leveranciersovereenkomststatus

Controleer de status van bestaande overeenkomsten met een leverancier in uw aangesloten systemen.

### `/brief` — Juridische Team Briefing

```
/brief daily              # Ochtendoverzicht
/brief topic [vraag]      # Onderzoeksbrief over een specifieke juridische vraag
/brief incident [onderwerp]  # Snelle brief over een zich ontwikkelende situatie
```

### `/respond` — Genereer Gestandaardiseerd Antwoord

Genereer een antwoord vanuit uw geconfigureerde templates voor veelvoorkomende aanvraagtypen.

## Skills

| Skill | Beschrijving |
|-------|-------------|
| `contract-review` | Playbook-gebaseerde contractanalyse, afwijkingsclassificatie, redline-generatie |
| `nda-triage` | NDA-screeningcriteria, classificatieregels, routeringsaanbevelingen |
| `compliance` | Privacyregelgeving (AVG/GDPR), DPA-beoordeling, verzoeken van betrokkenen |
| `canned-responses` | Templatebeheer, antwoordcategorieën, escalatietriggers |
| `legal-risk-assessment` | Risicoseveriteitsframework, classificatieniveaus, escalatiecriteria |
| `meeting-briefing` | Meetingvoorbereidingsmethodologie, contextverzameling, actie-itemtracking |
| `tabular-review` | Bulk documentbeoordeling naar gestructureerde Excel-spreadsheets |

## Nederlandse Rechtscontext

Deze plugin is aangepast aan het Nederlandse recht:

- **Burgerlijk Wetboek (BW)** — Nederlandse civiele wetgeving voor contracten
- **Algemene Verordening Gegevensbescherming (AVG)** — GDPR-implementatie
- **Autoriteit Persoonsgegevens (AP)** — Nederlandse toezichthoudende autoriteit
- **ACM** — Autoriteit Consument & Markt (mededinging)
- **AFM** — Autoriteit Financiële Markten (financiële markten)

## Best Practices

### Playbook Configuratie

Uw playbook is het hart van het contractbeoordelingssysteem. Definieer uw posities in `legal.local.md`:

- **Standaardposities**: Uw voorkeursovereenkomstvoorwaarden
- **Acceptabele bereiken**: Wat u zonder escalatie kunt accepteren
- **Escalatietriggers**: Voorwaarden die senior review of externe advocaat vereisen

### Templatebeheer

Definieer templates voor veelvoorkomende aanvragen. Templates ondersteunen variabele substitutie en bevatten ingebouwde escalatietriggers voor situaties die geen gestandaardiseerd antwoord zouden moeten gebruiken.

## Bestandsstructuur

```
legal-nl/
├── .claude-plugin/plugin.json
├── .mcp.json
├── CONNECTORS.md
├── README.md
├── commands/
│   ├── review-contract.md
│   ├── triage-nda.md
│   ├── vendor-check.md
│   ├── brief.md
│   └── respond.md
└── skills/
    ├── contract-review/SKILL.md
    ├── nda-triage/SKILL.md
    ├── compliance/SKILL.md
    ├── canned-responses/SKILL.md
    ├── legal-risk-assessment/SKILL.md
    ├── meeting-briefing/SKILL.md
    └── tabular-review/SKILL.md
```
