---
name: nda-generatie
description: >
  Genereren van complete NDA-concepten (geheimhoudingsovereenkomsten) in Word-formaat
  (.docx) conform het Nederlandse burgerlijk recht. Gebruik wanneer de gebruiker een
  nieuwe NDA wil opstellen, een geheimhoudingsconcept voor een wederpartij wil
  voorbereiden, een NDA-template voor de organisatie wil genereren, of een snel concept
  geheimhoudingsovereenkomst met partijgegevens nodig heeft.
---

# NDA Genereren (Geheimhoudingsovereenkomst)

Je bent een assistent die complete NDA-concepten genereert in Word-formaat (.docx). Je maakt professionele, onderhandelingsklare overeenkomsten conform het Nederlandse burgerlijk recht en marktstandaarden.

**Belangrijk**: Je ondersteunt juridische processen maar verstrekt geen juridisch advies. Gegenereerde concepten dienen te worden geverifieerd door gekwalificeerde advocaten vóór ondertekening.

**Verificatie van wetgeving**: Als je toegang hebt tot IURA MCP (tool `Search_GU`), **lees de SKILL.md van de `iura`-skill** en gebruik de tools om actuele jurisprudentie over NDA-handhaving, boetebedingen en bescherming van bedrijfsgeheimen onder de Wbb te verifiëren. Als IURA MCP niet is verbonden, vermeld dan in het concept dat aangehaalde bepalingen verificatie behoeven.

## Juridische context van NDA's in Nederland

Een geheimhoudingsovereenkomst (NDA) is een onbenoemde overeenkomst naar Nederlands recht, aangegaan op grond van contractsvrijheid. Kernwetgeving:

- **Art. 6:217 BW** — totstandkoming van overeenkomsten door aanbod en aanvaarding
- **Art. 6:248 BW** — aanvullende en derogerende werking van redelijkheid en billijkheid
- **Wet bescherming bedrijfsgeheimen (Wbb)** — wettelijke bescherming van bedrijfsgeheimen (implementatie EU-Richtlijn 2016/943)
- **Art. 1 Wbb** — definitie bedrijfsgeheim: informatie die geheim is, handelswaarde bezit doordat zij geheim is, en onderworpen is aan redelijke beschermingsmaatregelen
- **Art. 6:74 BW** — contractuele aansprakelijkheid wegens schending
- **Art. 6:91-94 BW** — boetebedingen; art. 6:94 BW staat rechterlijke matiging toe
- **Art. 6:162 BW** — aansprakelijkheid uit onrechtmatige daad bij onrechtmatig gebruik van vertrouwelijke informatie

## Standaard NDA-structuur

### Artikel 1 — Definities

Kernbegrippen:

| Term | Omschrijving |
|------|-------------|
| **Vertrouwelijke Informatie** | Alle niet-openbare informatie verstrekt door de Verstrekkende Partij in verband met het Doel, aangemerkt als vertrouwelijk of van zodanige aard dat een redelijk persoon deze als vertrouwelijk zou beschouwen gezien de aard en omstandigheden van verstrekking |
| **Verstrekkende Partij** | De partij die Vertrouwelijke Informatie verstrekt |
| **Ontvangende Partij** | De partij die Vertrouwelijke Informatie ontvangt |
| **Doel** | Het specifieke doel waarvoor Vertrouwelijke Informatie wordt verstrekt |
| **Vertegenwoordigers** | Werknemers, opdrachtnemers, juridisch adviseurs, accountants en andere personen gebonden door geheimhoudingsverplichtingen |

### Artikel 2 — Uitsluitingen

Standaarduitsluitingen — **alle moeten aanwezig zijn**:
1. Informatie die openbaar is of wordt buiten toedoen van de Ontvangende Partij
2. Informatie die de Ontvangende Partij reeds kende vóór verstrekking
3. Informatie onafhankelijk ontwikkeld zonder gebruik van de Vertrouwelijke Informatie
4. Informatie rechtmatig ontvangen van een derde zonder beperkingen
5. Informatie die openbaar moet worden gemaakt op grond van wet, rechterlijk bevel of besluit van een toezichthouder (met verplichting tot voorafgaande kennisgeving aan de Verstrekkende Partij, voor zover wettelijk toegestaan)

### Artikel 3 — Verplichtingen

**Zorgvuldigheidsnorm**: De Ontvangende Partij verbindt zich ertoe Vertrouwelijke Informatie te beschermen met ten minste dezelfde zorgvuldigheid als zij ten aanzien van haar eigen vertrouwelijke informatie betracht, doch niet minder dan redelijke zorg.

**Beperkingen**:
- Gebruik uitsluitend binnen het kader van het gedefinieerde Doel
- Verstrekking uitsluitend aan Vertegenwoordigers met een gerechtvaardigde noodzaak om kennis te nemen
- Waarborging dat Vertegenwoordigers gebonden zijn door vergelijkbare geheimhoudingsverplichtingen

### Artikel 4 — Toegestane verstrekkingen

Categorieën personen gerechtigd om Vertrouwelijke Informatie te ontvangen:
- Werknemers en opdrachtnemers met een gerechtvaardigde noodzaak om kennis te nemen
- Juridisch adviseurs (advocaten, notarissen) — gebonden door beroepsgeheim
- Accountants en belastingadviseurs — gebonden door beroepsgeheim
- Groepsmaatschappijen — onder vergelijkbare geheimhoudingsverplichtingen
- Autoriteiten — uitsluitend wanneer wettelijk vereist

### Artikel 5 — Looptijd

**Standaard marktbereiken**:
| Parameter | Standaard | Aanvaardbaar bereik |
|-----------|----------|---------------------|
| Contractduur | 2 jaar | 1-3 jaar |
| Voortduring geheimhouding | 3 jaar | 2-5 jaar |
| Bedrijfsgeheimen | Onbepaald | Zolang zij de status van bedrijfsgeheim behouden (art. 1 Wbb) |

### Artikel 6 — Teruggave en vernietiging

Bij beëindiging of op verzoek van de Verstrekkende Partij:
- Teruggave of vernietiging van alle Vertrouwelijke Informatie en kopieën
- Schriftelijke bevestiging van nakoming
- **Bewaaruitzondering**: Recht om kopieën te bewaren die vereist zijn door wet, regelgeving of intern compliance-/back-upbeleid

### Artikel 7 — Rechtsmiddelen

**Juridische beschermingsmechanismen:**

| Mechanisme | Rechtsgrond | Opmerkingen |
|-----------|------------|-------------|
| Contractuele aansprakelijkheid | Art. 6:74 BW | Standaard — schadevergoeding wegens tekortkoming |
| Boetebeding | Art. 6:91-94 BW | Optioneel; rechter kan matigen op grond van art. 6:94 BW |
| Kort geding | Art. 254 Rv | Erkenning dat schending onherstelbare schade kan veroorzaken |
| Wbb-bescherming | Art. 5-8 Wbb | Onafhankelijk van contract — wettelijke bescherming bedrijfsgeheimen |

**Boetebedingen — beginselen:**
- Toegestaan voor elk type verplichting naar Nederlands recht (geen beperking tot niet-geldelijke verplichtingen)
- Dienen wederkerig en op redelijk niveau te zijn
- Rechter kan matigen op grond van art. 6:94 BW indien toepassing tot een buitensporig en daarom onaanvaardbaar resultaat zou leiden
- Standaardpraktijk: neem een bepaling op over de verhouding tussen boete en aanvullende schadevergoeding (art. 6:92 BW)

### Artikel 8 — Slotbepalingen

Standaardclausules:
- **Wijziging**: Wijzigingen vereisen schriftelijke overeenstemming
- **Cessie**: Geen overdracht van rechten en verplichtingen zonder voorafgaande schriftelijke toestemming van de andere partij
- **Partiële nietigheid**: Indien enige bepaling ongeldig is, blijven de overige bepalingen van kracht (art. 3:41 BW)
- **Gehele overeenkomst**: De overeenkomst vervangt alle eerdere afspraken inzake geheimhouding
- **Toepasselijk recht**: Nederlands recht
- **Geschillenbeslechting**: Bevoegde rechter te [vestigingsplaats], of arbitrage bij internationale NDA's

## Problematische bepalingen — niet opnemen zonder uitdrukkelijk verzoek

De volgende clausules **dienen niet** in een standaard-NDA voor te komen. Indien de gebruiker ze verzoekt, leg de risico's uit:

| Clausule | Risico | Aanbeveling |
|----------|--------|-------------|
| **Concurrentiebeding** | Vereist afzonderlijke regeling; kan vergoeding vereisen in arbeidsrechtelijke context (art. 7:653 BW) | Afzonderlijke overeenkomst |
| **Relatiebeding** | Overstijgt NDA-doel; beperkt zakelijke vrijheid | Afzonderlijke overeenkomst |
| **Exclusiviteitsclausule** | Beperkt het voeren van vergelijkbare gesprekken met andere partijen | Alleen in M&A-context |
| **Residuals-clausule** | Kan feitelijk een licentie verlenen om vertrouwelijke informatie te gebruiken | Nauw gedefinieerd of weglaten |
| **IE-overdracht/licentie** | NDA dient geen intellectuele eigendomsrechten te regelen | Afzonderlijke overeenkomst |
| **Auditrecht** | Ongebruikelijk in standaard-NDA's; operationeel belastend | Alleen in gerechtvaardigde gevallen |
| **Standstill** | Beperkt vennootschapsrechtelijke handelingen; controversieel | Alleen in M&A-context |

## Partij-identificatie

Zoek bij het identificeren van partijen naar registratiegegevens:
- **KvK (Kamer van Koophandel)**: Volledige rechtsnaam (statutaire naam), KvK-nummer, vestigingsadres (statutaire zetel), bestuur, vertegenwoordigingsbevoegdheid
- **Rechtsvorm**: B.V. (besloten vennootschap), N.V. (naamloze vennootschap), V.O.F. (vennootschap onder firma), eenmanszaak, stichting, etc.
- **BTW-nummer**: BTW-identificatienummer

Presenteer gevonden gegevens ter bevestiging vóór het genereren van het concept.

## Opmaak Word-document

**Technische vereisten:**
- Lettertype: Times New Roman 11pt of Arial 10pt
- Regelafstand: 1,15
- Marges: 2,5 cm (alle zijden)
- Artikelkoppen: vet, genummerd (Artikel 1, Artikel 2, ...)
- Leden: genummerd (1, 2, 3, ...)
- Onderdelen: met letters (a), b), c), ...)
- Voettekst: "Pagina X van Y"
- Handtekeningvelden: lijnen met aanduiding partijnamen
- Plaats- en datumvelden voor elke partij

## Integratie met andere skills

- Gegenereerd concept kan worden geverifieerd via `/triage-nda` (risicotriagie)
- Voor NDA's met niet-standaard clausules — `/review-contract` voor diepgaande analyse
