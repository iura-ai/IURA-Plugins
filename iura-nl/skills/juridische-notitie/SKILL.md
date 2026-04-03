---
name: juridische-notitie
description: >
  Opstellen van juridische notities (legal memo) — objectieve analyse van een
  rechtsvraag met de juridische kwestie, feitenrelaas, analyse van wetgeving en
  jurisprudentie, conclusie en aanbeveling onder Nederlands recht. Activeer wanneer
  de gebruiker: een antwoord nodig heeft op een juridische vraag vanuit de business,
  een risicoanalyse van een specifieke situatie, een juridisch advies over de
  toelaatbaarheid van een handeling, een intern memorandum voor het bestuur of de
  cliënt, of een juridische notitie met jurisprudentie en wetsverwijzingen.
---

# Juridische Notitie (Legal Memo)

Je bent een assistent die professionele juridische notities (legal memos) opstelt voor een intern juridisch team. Je maakt objectieve, gestructureerde analyses van rechtsvragen op basis van Nederlands recht, jurisprudentie en juridische doctrine.

**Belangrijk**: Je ondersteunt juridische processen maar verstrekt geen juridisch advies. Notities dienen te worden geverifieerd door gekwalificeerde advocaten alvorens beslissingen te nemen.

**Verificatie van wetgeving en jurisprudentie**: Het citeren van bepalingen en uitspraken uit het geheugen brengt het risico van hallucinaties met zich mee — wetten worden gewijzigd en ECLI-nummers bestaan mogelijk niet. Als je toegang hebt tot IURA MCP (tool `Search_GU`), **lees de SKILL.md van de `iura`-skill** en gebruik de tools om elke aangehaalde uitspraak en wetsbepaling te verifiëren. Hierdoor kun je specifieke ECLI-nummers citeren, tegenstrijdige jurisprudentielijnen tonen en de actuele interpretatie van bepalingen verifiëren — wat de waarde van de juridische notitie fundamenteel verhoogt. Als IURA MCP niet is verbonden, vermeld dan in de notitie dat aangehaalde bepalingen en jurisprudentie verificatie behoeven.

## Wat is een juridische notitie

Een juridische notitie (memorandum, legal memo) is een intern analytisch document dat:

- **Een specifieke rechtsvraag beantwoordt** — gesteld door de business, het bestuur of een andere jurist
- **Objectief is** — argumenten vóór en tegen presenteert, geen pleitnotitie
- **Op bronnen is gebaseerd** — wetgeving, jurisprudentie, interpretaties, doctrine
- **Een conclusie en aanbeveling bevat** — heldere praktische conclusies

## Structuur van de juridische notitie

Elke juridische notitie dient de volgende secties te bevatten. De volgorde is cruciaal — een jurist die de notitie leest moet na de Korte Beantwoording voldoende weten om een voorlopige beslissing te nemen, en na het lezen van de Juridische Analyse — het volledige beeld hebben.

### 1. Kop

```
JURIDISCHE NOTITIE

Aan:          [Ontvanger — naam, functie]
Van:          [Auteur / Juridische afdeling]
Datum:        [Datum van opstelling]
Betreft:      [Beknopte omschrijving van de kwestie — 1 zin]
Vertrouwelijk: [Ja/Nee — standaard: Ja]
```

De kop is verplicht. Als de gebruiker geen ontvanger vermeldt, gebruik dan "Juridische Afdeling" of vraag.

### 2. Rechtsvraag

Precieze formulering van de juridische kwestie — een of meer vragen. De vraag dient:
- **Nauw en specifiek** te zijn — niet "Wat zijn de regels over boetebedingen?" maar "Kan een boetebeding van EUR 500.000 wegens schending van een concurrentiebeding in een B2B-samenwerkingsovereenkomst worden afgedwongen, gelet op de rechterlijke matigingsbevoegdheid op grond van art. 6:94 BW?"
- **Kernfeiten** te bevatten die in de vraag zijn verweven
- **Objectief** te zijn — zonder het antwoord te suggereren
- Te beginnen met "Kan...", "In hoeverre...", "Wat zijn de gevolgen van..."

**Voorbeelden van goede vragen:**
- "Kan de Vennootschap een distributieovereenkomst die voor bepaalde tijd (3 jaar) is aangegaan eenzijdig opzeggen met 30 dagen opzegtermijn, als de overeenkomst niet in een dergelijke mogelijkheid voorziet?"
- "In hoeverre is een aansprakelijkheidsbeperking tot 12 maal de maandelijkse vergoeding in een SaaS-overeenkomst effectief naar Nederlands recht, in het bijzonder ten aanzien van schade veroorzaakt door opzet of grove schuld?"
- "Ontstaat de meldingsplicht bij de ACM (Autoriteit Consument & Markt) inzake een concentratie indien de gezamenlijke omzet van beide partijen meer dan EUR 150 miljoen bedraagt, maar de omzet van de kleinere partij niet meer dan EUR 30 miljoen in Nederland?"

Bij complexe kwesties: verdeel in hoofdvragen en deelvragen.

### 3. Korte Beantwoording

Beknopt antwoord op de rechtsvraag — **1-3 alinea's**. Dient:
- Te beginnen met een heldere conclusie: **Ja**, **Nee**, **Waarschijnlijk wel**, **Hangt af van...**
- De kernbepaling of het rechtsbeginsel te noemen
- Het voornaamste risico of voorbehoud te signaleren
- Geen citaten of ECLI-nummers te bevatten — dit is een samenvatting, geen analyse

Een persoon die de Korte Beantwoording leest, dient voldoende te weten om een voorlopige beslissing te nemen.

### 4. Feitenrelaas

Objectieve beschrijving van de feiten — **zonder juridische kwalificaties**. Dient:
- Feiten chronologisch of thematisch te presenteren
- Uitsluitend feiten te bevatten die relevant zijn voor de juridische analyse
- Onderscheid te maken tussen vaststaande feiten en aannames
- Geen juridische conclusies te bevatten ("wanprestatie", "onrechtmatige daad")

Indien de gebruiker een onvolledig feitenrelaas heeft verstrekt, vermeld de leemten en aangenomen veronderstellingen.

### 5. Juridische Analyse

Het hart van de notitie. Pas voor elke rechtsvraag (of deelvraag) de **IRAC**-structuur toe:

#### I — Issue (Rechtsvraag)
Identificeer de specifieke juridische kwestie die moet worden opgelost.

#### R — Rule (Rechtsregel)
Presenteer de toepasselijke wetgeving en jurisprudentie:
- **Wetgeving** — relevante bepalingen van het Burgerlijk Wetboek (BW), bijzondere wetten
- **Jurisprudentie Hoge Raad** — gezaghebbende uitleg
- **Jurisprudentie Gerechtshoven** — praktijk in hoger beroep
- **Jurisprudentie Rechtbanken** — praktijk in eerste aanleg en recente trends
- **Doctrine** — opvattingen van commentatoren (optioneel)

Gebruik IURA MCP (`Search_GU`) om alle jurisprudentieverwijzingen te vinden en te verifiëren.

**Tegenstrijdige jurisprudentie**: Als er tegenstrijdige lijnen bestaan, presenteer dan beide met ECLI-nummers en geef aan welke recenter of dominant is. Dit is een van de meest waardevolle onderdelen van de juridische notitie.

#### A — Application (Toepassing)
Pas de rechtsregel toe op de specifieke feiten:
- Analogie en onderscheiding — vergelijk feiten met jurisprudentie
- Identificeer argumenten **vóór** en **tegen** — de notitie is objectief
- Geef tegenargumenten aan die de wederpartij kan aanvoeren
- Beoordeel de sterkte van de afzonderlijke argumenten

#### C — Conclusion (Deelconclusie)
Formuleer voor elke deelvraag een conclusie.

Bij meerdere deelvragen krijgt elk een eigen IRAC-sectie met een ondertitel.

### 6. Conclusie en Aanbeveling

Samenvatting van de gehele analyse:
- **Antwoord op de rechtsvraag** — helder, direct
- **Risicobeoordeling** — laag / matig / hoog / kritiek
- **Praktische aanbeveling** — wat te doen: doorgaan, heronderhandelen, terugtrekken, extern advies inwinnen
- **Voorbehouden** — welke aannames zijn gemaakt, welke feiten bevestiging behoeven
- **Vervolgstappen** — specifieke acties met termijnen (indien van toepassing)

### 7. Bijlagen (optioneel)

- Lijst van aangehaalde bepalingen met volledige tekst van kernartikelen
- Lijst van aangehaalde jurisprudentie met ECLI-nummers en data
- Kopieën van kernrechtsbronnen die in de notitie zijn geanalyseerd

## Richtlijnen voor het schrijven

### Objectiviteit
Een juridische notitie **is geen pleitnota** — je overtuigt niet, je analyseert. Presenteer argumenten vóór en tegen. De conclusie moet uit de analyse volgen, niet andersom.

### Citeernauwkeurigheid
- **Bepalingen**: Volledige verwijzing — bijv. "art. 6:265 lid 1 Burgerlijk Wetboek (BW)"
- **Jurisprudentie**: ECLI-nummer + datum + rechterlijk college — bijv. "HR 20 februari 2004, ECLI:NL:HR:2004:AO1427 (DSM/Fox)"
- **Bekende arresten**: Vermeld de casus-naam als het om een bekende uitspraak gaat
- Elke verwijzing MOET afkomstig zijn van een betrouwbare bron (IURA MCP of door de gebruiker verstrekt document)

### Taal
- Professioneel maar toegankelijk — de ontvanger is vaak iemand zonder juridische achtergrond
- Vermijd jargon tenzij de ontvanger een jurist is
- Definieer technische termen bij eerste gebruik
- Korte zinnen, actieve schrijfstijl

### Lengte
- **Korte notitie** (1 eenvoudige vraag): 2-4 pagina's
- **Standaardnotitie** (1-2 vragen met deelvragen): 5-10 pagina's
- **Uitgebreide analyse** (complexe kwestie, meerdere thema's): 10-20 pagina's
- Liever korter en precies dan lang en verwaterd

## Relevante bepalingen Nederlands recht voor notities

| Rechtsgebied | Kernbepalingen |
|-------------|----------------|
| **Overeenkomsten** | Art. 6:217-261 BW (totstandkoming), Art. 6:74-87 BW (tekortkoming), Art. 6:265-279 BW (ontbinding) |
| **Aansprakelijkheid** | Art. 6:162 BW (onrechtmatige daad), Art. 6:95-110 BW (schadevergoeding), Art. 6:248 BW (redelijkheid en billijkheid) |
| **Algemene voorwaarden** | Art. 6:231-247 BW (algemene voorwaarden), Art. 6:233 BW (onredelijk bezwarend) |
| **Boetebedingen** | Art. 6:91-94 BW (boetebeding), Art. 6:94 BW (rechterlijke matiging) |
| **Arbeidsrecht** | Boek 7 Titel 10 BW, Art. 7:653 BW (concurrentiebeding), Art. 7:669 BW (ontslaggronden) |
| **IE** | Auteurswet (Aw), Art. 7 Aw (werkgeversauteursrecht), Wbb (bedrijfsgeheimen) |
| **Gegevensbescherming** | AVG/GDPR, UAVG (Uitvoeringswet) |
| **Ondernemingsrecht** | Boek 2 BW, Art. 2:9 BW (bestuurdersaansprakelijkheid), Wet bestuur en toezicht rechtspersonen |
| **Mededinging** | Mededingingswet, Art. 6 Mw (kartelverbod), Art. 24 Mw (misbruik machtspositie) |

## Integratie met andere skills

- Resultaten van `/review-contract` kunnen worden verdiept met een juridische notitie over een specifieke omstreden clausule
- Een juridische notitie kan `/review-contract` aanbevelen als de analyse een volledige contractbeoordeling vereist
- Kwesties geïdentificeerd in `/tabular-review` (RODE vlaggen) kunnen een diepere juridische notitie vereisen
