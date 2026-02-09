# Connectors

## Hoe tool-referenties werken

Pluginbestanden gebruiken `~~categorie` als placeholder voor welk hulpmiddel de gebruiker ook aansluit in die categorie. Bijvoorbeeld `~~cloudopslag` kan betekenen Box, Egnyte of een andere opslagprovider met een MCP-server.

Plugins zijn **tool-agnostisch** — ze beschrijven workflows in termen van categorieën (cloudopslag, chat, kantoorpakket, etc.) in plaats van specifieke producten. Het `.mcp.json` configureert specifieke MCP-servers vooraf, maar elke MCP-server in die categorie werkt.

## Connectors voor deze plugin

| Categorie | Placeholder | Inclusief servers | Andere opties |
|-----------|-------------|------------------|---------------|
| Chat | `~~chat` | Slack | Microsoft Teams |
| Cloudopslag | `~~cloudopslag` | Box, Egnyte | Dropbox, SharePoint, Google Drive |
| CLM | `~~CLM` | — | Ironclad, Agiloft |
| CRM | `~~CRM` | — | Salesforce, HubSpot |
| E-handtekening | `~~e-handtekening` | — | DocuSign, Adobe Sign |
| Kantoorpakket | `~~kantoorpakket` | Microsoft 365 | Google Workspace |
| Projecttracker | `~~projecttracker` | Atlassian (Jira/Confluence) | Linear, Asana |

## Optionele Integraties

Voor Nederlandse juridische praktijk kunnen de volgende integraties nuttig zijn:

- **Juridische databases**: Overweeg integratie met Nederlandse juridische databases voor toegang tot jurisprudentie en wetgeving
- **Autoriteit Persoonsgegevens (AP)**: Voor AVG-compliance monitoring
- **KvK (Kamer van Koophandel)**: Voor bedrijfsinformatie en verificatie
