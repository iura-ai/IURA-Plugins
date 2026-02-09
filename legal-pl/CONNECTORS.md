# Konektory

## Jak działają placeholdery narzędzi

Pliki pluginu używają `~~kategoria` jako placeholder dla narzędzia, które użytkownik podłączy w danej kategorii. Na przykład `~~przechowywanie w chmurze` może oznaczać Box, Egnyte lub dowolnego innego dostawcę z serwerem MCP.

Pluginy są **niezależne od konkretnych narzędzi** — opisują workflow w kategoriach (przechowywanie w chmurze, czat, pakiet biurowy itp.) zamiast konkretnych produktów. Plik `.mcp.json` konfiguruje konkretne serwery MCP, ale każdy serwer MCP w danej kategorii zadziała.

## Konektory dla tego pluginu

| Kategoria | Placeholder | Dołączone serwery | Inne opcje |
|-----------|-------------|-------------------|------------|
| Baza wiedzy prawnej | `~~baza prawna` | IURA MCP (orzecznictwo, legislacja, interpretacje) | — |
| Czat | `~~czat` | Slack | Microsoft Teams |
| Przechowywanie w chmurze | `~~przechowywanie w chmurze` | Box, Egnyte | Dropbox, SharePoint, Google Drive |
| CLM | `~~CLM` | — | Ironclad, Agiloft |
| CRM | `~~CRM` | — | Salesforce, HubSpot |
| E-podpis | `~~e-podpis` | — | DocuSign, Adobe Sign, Autenti |
| Pakiet biurowy | `~~pakiet biurowy` | Microsoft 365 | Google Workspace |
| Zarządzanie projektami | `~~zarządzanie projektami` | Atlassian (Jira/Confluence) | Linear, Asana |

## IURA MCP — Baza wiedzy prawnej

IURA MCP zapewnia dostęp do ponad 1,5 miliona dokumentów prawnych z Polski:

| Narzędzie | Baza danych | Zastosowanie |
|-----------|-------------|-------------|
| `Search_SP` | Orzeczenia sądów powszechnych | Wyroki sądów rejonowych, okręgowych i apelacyjnych |
| `Search_SN` | Orzeczenia Sądu Najwyższego | Uchwały, wyroki i postanowienia SN |
| `Search_CBOSA` | Orzeczenia sądów administracyjnych | Wyroki NSA i WSA |
| `Search_TK` | Orzeczenia Trybunału Konstytucyjnego | Wyroki i postanowienia TK |
| `Search_KIO` | Orzeczenia Krajowej Izby Odwoławczej | Zamówienia publiczne |
| `Search_DU` | Dziennik Ustaw | Ustawy i rozporządzenia (aktualny stan prawny) |
| `Search_IP` | Interpretacje podatkowe | Interpretacje MF, KIS, KAS |
| `Search_News` | Aktualności prawne | Bieżące informacje i zmiany w prawie |

Każdy skill w tym pluginie zawiera instrukcje dotyczące wykorzystania IURA MCP do wzbogacenia analizy prawnej o aktualne orzecznictwo i przepisy.
