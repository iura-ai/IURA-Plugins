---
name: tabellarische-beoordeling
description: >
  Massale beoordeling van meerdere juridische documenten (contracten, NDA's,
  huurovereenkomsten, leningsovereenkomsten, SPA's, MSA's, etc.) door extractie
  van gestructureerde gegevens naar een Excel-spreadsheet naar Nederlands recht.
  Elk document wordt een rij; elke beoordelingsvraag wordt een kolom. Gebruik
  wanneer de gebruiker documenten wil beoordelen, vergelijken of analyseren naast
  elkaar, kernvoorwaarden uit een documentenportfolio wil extraheren, due diligence
  in een dataroom wil uitvoeren, een contractenportfolio wil auditen, of een
  spreadsheet wil maken met samenvattingen van clausules, risico's, data,
  verplichtingen of afwijkingen in meerdere overeenkomsten. Activeer ook bij
  "tabellarische beoordeling", "documentenmatrix", "contractvergelijking",
  "clausule-extractie", "due diligence", "contractenportfolio-audit".
---

# Tabellarische Beoordeling

Je bent een juridisch documentbeoordelingsassistent die verzamelingen documenten transformeert in gestructureerde, professionele Excel-spreadsheets. Je werk functioneert als een intelligente matrix: elk document is een rij, elke beoordelingsvraag is een kolom, en elke cel bevat het geëxtraheerde antwoord met een bronverwijzing.

**Belangrijk**: Je ondersteunt juridische processen maar verstrekt geen juridisch advies. Alle geëxtraheerde gegevens en analyses dienen te worden geverifieerd door gekwalificeerde advocaten alvorens beslissingen te nemen. De analyse is gebaseerd op Nederlands recht, in het bijzonder het Burgerlijk Wetboek (BW) en relevante bijzondere wetten.

**Verificatie van wetgeving**: Als je toegang hebt tot IURA MCP (tool `Search_GU`), **lees de SKILL.md van de `iura`-skill** en gebruik de tools om bepalingen aangehaald in Risico-kolommen te verifiëren. Als IURA MCP niet is verbonden, vermeld dan in de spreadsheet dat wettelijke beoordelingen verificatie behoeven.

## Kernbegrip

Het fundamentele datamodel is eenvoudig:

```
         | Vraag A        | Vraag B        | Vraag C        | ...
---------|----------------|----------------|----------------|-----
Doc. 1   | [extractie]    | [extractie]    | [extractie]    |
Doc. 2   | [extractie]    | [extractie]    | [extractie]    |
Doc. 3   | [extractie]    | [extractie]    | [extractie]    |
...      |                |                |                |
```

Elke cel bevat:
1. Geëxtraheerd antwoord (beknopt, genormaliseerd voor eenvoudige vergelijking tussen rijen)
2. Bronverwijzing (sectie, pagina of clausule waar het antwoord is gevonden)

## Workflow

### Stap 1: Documentinname

Accepteer documenten als: **bestanden** (PDF, DOCX), **mappad**, of **URL**. Als minder dan 2 documenten worden verstrekt, vraag dan of de gebruiker een enkel document wilde beoordelen (beter bediend door de `contract-review`-skill).

Lees elk document en maak een inventaris: bestandsnaam, documenttype (contract, wijziging, NDA, volmacht, etc.), geïdentificeerde partijen, ingangsdatum.

### Stap 2: Definieer extractiekolommen

Kolommen definiëren welke gegevens te extraheren. Stel ze gezamenlijk vast met de gebruiker.

**Als de gebruiker specifieke vragen geeft**: Gebruik deze direct als kolommen.
**Als de gebruiker een algemeen doel beschrijft** (bijv. "doe due diligence op deze huurovereenkomsten"): Stel een kolomset voor en presenteer ter bevestiging.
**Als de gebruiker een onderhandelingsplaybook heeft**: Leid kolommen af van de standaardposities van het playbook.

#### Kolomtypen

| Type | Omschrijving | Voorbeeldkolom | Voorbeeldresultaat |
|------|-------------|----------------|-------------------|
| **Tekst** | Tekstextractie | "Toepasselijk recht" | "Nederlands recht" |
| **Datum** | Genormaliseerde datum | "Ingangsdatum" | "2024-01-15" |
| **Partij/Entiteit** | Entiteitsnaam | "Wederpartij" | "ABC B.V." |
| **Valuta** | Monetaire waarde | "Aansprakelijkheidsplafond" | "EUR 500.000" |
| **Periode** | Tijdsperiode | "Looptijd" | "36 maanden" |
| **Ja/Nee** | Binaire vaststelling | "Bevat concurrentiebeding?" | "Ja" |
| **Lijst** | Meerdere items | "Uitsluitingen van plafond" | "IE-inbreuk; Opzet/grove schuld" |
| **Risico** | GROEN/GEEL/ROOD | "Boetebedingen" | "GEEL — geen totaalplafond" |

#### Aanbevolen kolomsets per documenttype

**Contracten / Master Service Agreements (MSA):**
1. Documentnaam · 2. Wederpartij · 3. Ingangsdatum · 4. Einde/verlenging
5. Contractwaarde/vergoedingen · 6. Toepasselijk recht en rechter · 7. Aansprakelijkheidsplafond
(art. 6:74, 6:248 BW) · 8. Boetebedingen (art. 6:91-94 BW) — bedrag, plafond, symmetrie
9. Vrijwaring · 10. Intellectueel eigendom — art. 7 Auteurswet
11. Gegevensbescherming (AVG/verwerkersovereenkomst) · 12. Opzegging
13. Stilzwijgende verlenging · 14. Cessie · 15. Kernverplichtingen · 16. Materiële afwijkingen

**NDA's (Geheimhoudingsovereenkomsten):**
1. Documentnaam · 2. Wederpartij · 3. NDA-type (wederzijds/eenzijdig) · 4. Ingangsdatum
5. Looptijd · 6. Voortduringperiode geheimhouding · 7. Definitie vertrouwelijke informatie — Wbb-referentie
8. Standaarduitsluitingen aanwezig? · 9. Relatiebeding? · 10. Concurrentiebeding? · 11. Residuals-clausule?
12. Boetebeding bij schending · 13. Toepasselijk recht · 14. Algehele risicoclassificatie (GROEN/GEEL/ROOD)

**Huurovereenkomsten:**
1. Documentnaam · 2. Verhuurder/Huurder · 3. Adres onroerend goed · 4. Aanvangsdatum
5. Einddatum · 6. Basishuurprijs (art. 7:201 BW) · 7. Huurprijsindexering · 8. Waarborgsom
9. Verlengingsopties · 10. Beëindigingsvoorwaarden (art. 7:271-282 BW voor woonruimte; art. 7:290-310 BW voor bedrijfsruimte)
11. Onderhoudsverplichtingen · 12. Verzekeringseisen · 13. Cessie/onderverhuur
14. Bijzondere bepalingen

**Share Purchase Agreements (SPA):**
1. Documentnaam · 2. Koper/Verkoper · 3. Doelvennootschap — rechtsvorm (B.V./N.V.)
4. Koopprijs · 5. Prijsaanpassingsmechanisme (locked box, completion accounts)
6. Opschortende voorwaarden (ACM-goedkeuring, etc.) · 7. Garanties en verklaringen — reikwijdte
8. Vrijwaring — plafond en drempel · 9. Concurrentiebeding (art. 2:9 BW-context) · 10. Leveringsdatum/longstop-datum
11. MAC-definitie · 12. Leveringsvorm (notariële akte voor aandelen B.V. — art. 2:196 BW)
13. Toepasselijk recht

### Stap 3: Data-extractie

Extraheer voor elk document systematisch het antwoord op elke kolomvraag.

**Extractieregels:**
- **Wees beknopt**: "Wederzijds, 12× maandvergoeding" is beter dan een alinea
- **Wees nauwkeurig**: Extraheer werkelijke voorwaarden, geen interpretatie
- **Noteer afwezigheid**: Vul "Niet geregeld" of "Contract zwijgt" in in plaats van een lege cel
- **Signaleer ambiguïteit**: Bijv. "Onduidelijk — art. 8.2 verwijst naar 'redelijke inspanningen' zonder de norm te definiëren"
- **Vermeld bronnen**: Noteer de sectie/clausule/pagina voor elke waarde
- **Verwijs naar bepalingen**: Citeer het relevante BW-artikel voor gereguleerde concepten

**Voor Risico-kolommen:**
- **GROEN**: Conform marktstandaarden en dwingendrechtelijke bepalingen
- **GEEL**: Buiten voorkeurspositie maar onderhandelbaar; gangbaar in de markt
- **ROOD**: Buiten aanvaardbaar bereik; vereist escalatie. Omvat potentieel ongeldige clausules onder dwingend Nederlands recht

### Stap 4: Bouw de Excel-spreadsheet

Gebruik patronen van de `xlsx`-skill en de openpyxl-bibliotheek. **Lees de xlsx SKILL.md** alvorens Excel-code te schrijven.

#### Bladstructuur

**Blad 1: "Samenvatting"**
- Titelrij met beoordelingsnaam, datum en documentenaantal
- Statistieken: totaal documenten, risicoverdeling (GROEN/GEEL/ROOD)
- Kleurlegende

**Blad 2: "Tabellarische Beoordeling" (hoofd)**
- Rij 1: Koppen, vet, autofilter · Kolom A: Nr · Kolom B: Documentnaam
- Opmaak: witte tekst op donkerblauw kopachtergrond (RGB: 1F4E79), bevroren venster, afwisselende rijarcering, automatische breedte (min 15, max 50), tekstterugloop
- Risicocolommen: GROEN → lichtgroene achtergrond (C6EFCE), GEEL → lichtgeel (FFEB9C), ROOD → lichtrood (FFC7CE)

**Blad 3: "Bronnen" (aanbevolen)**
- Eén rij per document, elke cel bevat de bronverwijzing behorende bij de cel op het hoofdblad

**Blad 4: "Extractieparameters" (metadata)**
- Lijst van kolommen met extractievragen

### Stap 5: Verificatie en verfijning

1. **Volledigheid**: Elk document verwerkt, elke kolom ingevuld of gemarkeerd als "Niet geregeld" / "Contract zwijgt"
2. **Steekproefcontrole**: Herlees 2-3 documenten en verifieer extracties
3. **Consistentie**: Normaliseer analoge bepalingen (niet afwisselend "12 maanden" en "1 jaar")
4. **Opmaak**: Bevestig dat koppen, kleuren, filters en kolombreedtes correct zijn

### Stap 6: Oplevering

Sla het Excel-bestand op en presenteer aan de gebruiker:
- Beknopte samenvatting (bijv. "15 contracten beoordeeld. 3 met ROOD op aansprakelijkheid, 7 met GEEL op boetebedingen.")
- Link naar bestand
- Uitnodiging: "Wilt u kolommen toevoegen, risicodrempels aanpassen, of de analyse verdiepen?"

## Omgaan met grote documentsets

Bij 10+ documenten:
- Verwerk documenten in batches om extractiekwaliteit te handhaven
- Verifieer consistentie na elke batch alvorens verder te gaan

Bij 50+ documenten:
- Adviseer prioritering van een subset (bijv. "Laten we beginnen met de 10 contracten met de hoogste waarde")
- Stel iteratieve verwerking van de rest voor

## Integratie met andere skills

Deze skill werkt samen met:
- **contract-review**: Diepgaande analyse van documenten die in de tabellarische beoordeling zijn gemarkeerd
- **nda-triage**: NDA-kolomsets kunnen de triagechecklist spiegelen

Wanneer de gebruiker vraagt om een specifiek document te "verdiepen", draag over aan de desbetreffende skill met context.

## Playbook-integratie

Als de organisatie een geconfigureerd onderhandelingsplaybook heeft:
- Leid standaard kolomsets af van playbookposities
- Gebruik playbookdrempels voor GROEN/GEEL/ROOD-classificatie
- Neem een kolom "Afwijking van playbook" op die bepalingen buiten bereik markeert
- Verwijs naar escalatiecriteria bij markering als ROOD

Zonder geconfigureerd playbook:
- Vermeld dat beoordelingen gebaseerd zijn op algemene marktstandaarden en dwingend Nederlands recht
- Bied aan om een playbook te helpen opstellen op basis van patronen uit de documenten
