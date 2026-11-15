# IURA Plugin (BE)

AI-plugin voor Belgische juridische teams / plugin IA pour les équipes juridiques belges — ontworpen voor [Cowork](https://claude.com/product/cowork), werkt ook in Claude Code.

Geïntegreerd met **IURA MCP** — juridische kennisbank voor Belgisch recht / base de connaissances juridiques en droit belge: wetgeving uit Justel (alle historische versies), rechtspraak uit JUPORTAL (Hof van Cassatie / Cour de cassation, hoven en rechtbanken), arresten van het Grondwettelijk Hof / Cour constitutionnelle en van de Raad van State / Conseil d'État.

> **Disclaimer / Avertissement:** Deze plugin ondersteunt juridisch werk maar vormt geen juridisch advies; alle output is een ontwerp ter controle door een advocaat. Ce plugin soutient le travail juridique mais ne constitue pas un avis juridique ; tout résultat est un projet à faire vérifier par un avocat.

## Installatie / Installation

```
claude plugin install iura-be@iura-plugins
```

## Skills

Elke skill is tweetalig (NL/FR): de output volgt de taal van de gebruiker of de proceduretaal. / Chaque skill est bilingue (NL/FR) : la réponse suit la langue de l'utilisateur ou la langue de la procédure.

| Skill | Omschrijving / Description |
|-------|-------------|
| **iura** | Juridisch onderzoek / recherche juridique — Justel, JUPORTAL, Grondwettelijk Hof, Raad van State |
| **juridische-nota-note-juridique** | Juridische nota / note juridique — rechtsvraag, kort antwoord, analyse, conclusie |
| **contractbeoordeling-revue-contrat** | Contractbeoordeling / revue de contrats — nieuw Burgerlijk Wetboek (Boeken 1, 5, 6), WER Boek VI |
| **nda-triage** | NDA-triage — bedrijfsgeheimen (WER Boek XI), GROEN/GEEL/ROOD — VERT/JAUNE/ROUGE |
| **dagvaarding-citation** | Dagvaarding / citation — Gerechtelijk Wetboek / Code judiciaire |
| **conclusies-conclusions** | Conclusies en syntheseconclusies / conclusions et conclusions de synthèse |

## Structuur / Structure

```
iura-be/
├── .claude-plugin/plugin.json
├── .mcp.json
├── CONNECTORS.md
├── README.md
├── LICENSE
└── skills/
    ├── iura/SKILL.md
    ├── juridische-nota-note-juridique/SKILL.md
    ├── contractbeoordeling-revue-contrat/SKILL.md
    ├── nda-triage/SKILL.md
    ├── dagvaarding-citation/SKILL.md
    └── conclusies-conclusions/SKILL.md
```

## Juridische context / Contexte juridique

- **Burgerlijk Wetboek / Code civil** (nieuw: Boeken 1, 5, 6, 8 / nouveau : Livres 1, 5, 6, 8)
- **Wetboek van economisch recht / Code de droit économique** (Boek VI, Boek XI)
- **Gerechtelijk Wetboek / Code judiciaire**
- **Wet van 15 juni 1935 op het gebruik der talen in gerechtszaken / loi du 15 juin 1935 concernant l'emploi des langues en matière judiciaire**
- Rechtspraak / jurisprudence: **Hof van Cassatie / Cour de cassation**, **Grondwettelijk Hof / Cour constitutionnelle**, **Raad van State / Conseil d'État**
