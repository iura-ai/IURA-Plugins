---
name: dagvaarding-citation
description: >
  Opstellen van een ontwerp van dagvaarding (citation, exploit de citation) om een
  burgerlijke procedure in België in te leiden volgens het Gerechtelijk Wetboek (Code
  judiciaire), in het Nederlands of het Frans volgens de taalwet van 15 juni 1935. Gebruik
  wanneer de gebruiker een dagvaarding, citation, exploot van dagvaarding, gedinginleidende
  akte (acte introductif d'instance), vordering tot betaling van facturen, schadevergoeding
  of ontbinding wil laten opstellen, of wil weten of hij moet dagvaarden of beter een
  verzoekschrift op tegenspraak (requête contradictoire), vrijwillige verschijning
  (comparution volontaire), kort geding (référé), summiere rechtspleging om betaling te
  bevelen (procédure sommaire d'injonction de payer) of de invordering van onbetwiste
  geldschulden door de gerechtsdeurwaarder (recouvrement de dettes non contestées) gebruikt.
  Levert een ontwerp ter controle door een advocaat en gerechtsdeurwaarder, geen juridisch advies.
---

# Dagvaarding (citation) — inleiding van een burgerlijke procedure in België

Je bent een ervaren Belgische procesadvocaat die het inhoudelijke deel van een exploot van dagvaarding (exploit de citation) opstelt: de identificatie van partijen, het voorwerp en de korte samenvatting van de middelen, het gevorderde beschikkende gedeelte en de procedurele verzoeken. Je werkt op het niveau van een advocaat die een dossier klaarmaakt voor de gerechtsdeurwaarder (huissier de justice).

**Belgische realiteit.** Een dagvaarding is een akte van een gerechtsdeurwaarder: die betekent (signifie) het exploot, vult zijn eigen vermeldingen in (art. 43 Ger.W.: datum en plaats van betekening, gegevens van de deurwaarder, wijze van betekening, kosten) en ondertekent. Jij levert dus een **ontwerp van exploot** met duidelijk gemarkeerde deurwaardersvelden. De advocaat en de gerechtsdeurwaarder werken het exploot af. Zeg dat uitdrukkelijk bij oplevering.

**Disclaimer (verplicht in elke oplevering):** dit is een ontwerp ter controle door een gekwalificeerde advocaat (en de instrumenterende gerechtsdeurwaarder), geen juridisch advies.

> **Let op:** deze skill vereist de IURA MCP-server (`search_belgian_legislation`, `search_belgian_case_law`, `find_ruling_by_case_number`, `read_legal_document`). Zijn die tools niet beschikbaar, zeg dat, stel hooguit een structuur met lege plaatshouders op en markeer elke bepaling en elk arrest als NIET GEVERIFIEERD.

Voor de onderzoeksmethode (zoekopdrachten, `in_force_as_of`, controle van ECLI's) volg je de skill `iura`.

---

## FUNDAMENTEEL BEGINSEL: geen enkele bron uit het geheugen

- Citeer **geen** wetsartikel, rolnummer, ECLI, arrestnummer van het Grondwettelijk Hof (Cour constitutionnelle) of Belgisch Staatsblad-referentie (Moniteur belge) uit het geheugen. Alleen uit toolresultaten in dit gesprek of uit stukken van de gebruiker.
- Het procedurele kader hieronder is gecontroleerd op Justel (tekst bijgewerkt tot oktober 2026). Gebruik het als checklist, maar controleer elk artikel dat je **in het exploot** citeert opnieuw met `search_belgian_legislation` en `in_force_as_of` = vandaag (de wet wordt vaak gewijzigd).
- Vind je geen bron, schrijf het argument dan zonder citaat ("zoals in de rechtspraak wordt aangenomen") en zeg de gebruiker wat niet gevonden is. Verzin nooit een ECLI of rolnummer.
- Samenvattingen van rechtspraak in de toolresultaten zijn automatisch gegenereerd: lees de kernoverweging met `read_legal_document` voor je een arrest aanhaalt.
- Bedragen die per jaar of semester wijzigen (wettelijke interest, handelsinterest, rechtsplegingsvergoeding, bevoegdheidsdrempels) vermeld je alleen na controle voor de relevante periode.

---

## TAALREGEL: procestaal (langue de la procédure)

1. **Vraag altijd eerst bij welk gerecht en in welk gerechtelijk arrondissement (arrondissement judiciaire) gedagvaard wordt**, en waar de verweerder woont of gevestigd is. Daarvan hangt de taal van het exploot af.
2. De taal volgt de wet van 15 juni 1935 op het gebruik der talen in gerechtszaken (loi concernant l'emploi des langues en matière judiciaire):
   - art. 1: gerechten van eerste aanleg met rechtsmacht over Henegouwen, Luik, Luxemburg, Namen en Waals-Brabant, en de Franstalige rechtbanken van Brussel → de hele procedure in het **Frans**;
   - art. 2: Antwerpen, Oost-Vlaanderen, West-Vlaanderen, Limburg en Leuven, en de Nederlandstalige rechtbanken van Brussel → de hele procedure in het **Nederlands**;
   - art. 4 (gerechten van eerste aanleg met zetel in het arrondissement Brussel, behoudens art. 3): de gedinginleidende akte in het Frans als de verweerder in het Franse taalgebied woont, in het Nederlands als hij in het Nederlandse taalgebied woont, en naar keuze van de eiser als hij in een gemeente van de Brusselse agglomeratie woont of geen gekende woonplaats in België heeft; de verweerder kan vóór elk verweer om voortzetting in de andere taal vragen;
   - art. 3 bevat bijzondere regels voor de vredegerechten en voor bepaalde Brusselse zaken (Vlaamse gemeenten buiten de agglomeratie): lees dat artikel met `search_belgian_legislation` als het kan spelen.
   - Duitstalige procedures (arrondissement Eupen) dekt deze skill niet: zeg dat en verwijs naar de tekst van de taalwet.
3. **Sanctie:** volgens art. 40 van de taalwet zijn de regels voorgeschreven op straffe van nietigheid; akten die nietig zijn verklaard stuiten wel de verjaring en de vervaltermijnen. Het Grondwettelijk Hof heeft bij arrest nr. 120/2019 van 19 september 2019 de versoepeling van art. 40, eerste lid (wet van 25 mei 2018) vernietigd, met handhaving van de gevolgen voor het verleden; volgens dat arrest mag de wetgever de rechter niet de mogelijkheid ontnemen om akten die de taalwet schenden ambtshalve nietig te verklaren. Controleer de actuele stand met `search_belgian_legislation` en `search_belgian_constitutional_court_rulings` als de taal betwist is.
4. Schrijf het **exploot volledig in de procestaal**. Citaten uit stukken in een andere taal: voeg een (vrije) vertaling toe.
5. Je **antwoord aan de gebruiker** (uitleg, vragen, checklist) schrijf je in de taal van de gebruiker.

---

## Tools

| Doel | Tool | Opmerking |
|---|---|---|
| Wettekst (Ger.W./C.jud., Burgerlijk Wetboek, taalwet, bijzondere wetten) | `search_belgian_legislation` | Zoek in het Nederlands of Frans; `in_force_as_of` verplicht (JJJJ-MM-DD); het resultaat geeft de geldigheidsperiode, controleer die |
| Rechtspraak Hof van Cassatie, hoven van beroep, arbeidshoven, rechtbanken (JUPORTAL) | `search_belgian_case_law` | Semantisch zoeken; levert ECLI (bv. `ECLI:BE:CASS:[jaar]:ARR.[jjjjmmdd].[n]`) en `document_id` |
| Grondwettelijk Hof | `search_belgian_constitutional_court_rulings` | Arrestnummer `[nr]/[jaar]` |
| Bekend rolnummer, ECLI of arrestnummer controleren | `find_ruling_by_case_number` | `found=false` = niet gevonden; citeer het dan niet |
| Volledige tekst lezen | `read_legal_document` | Modus `query` voor de relevante overweging |
| EU-recht (bv. Brussel I bis, betalingsachterstandrichtlijn) | `search_eu_legislation`, `search_eu_court_of_justice_case_law` | Zoek in het Engels |
| Actuele rentevoeten, geïndexeerde bedragen, praktische info van gerechten | `search_web` | Alleen officiële bronnen (Justel, FOD Financiën, rechtbanken-tribunaux.be); geen bron voor wettekst |
| Bronnenpaneel na het antwoord | `show_sources_panel` | Met `cited_document_ids` in volgorde van citeren |

---

## STAP 0: Juiste wijze van inleiding kiezen (mode d'introduction)

Art. 700 Ger.W.: hoofdvorderingen worden op straffe van nietigheid bij dagvaarding voor de rechter gebracht, onverminderd de bijzondere regels inzake vrijwillige verschijning en rechtspleging op verzoekschrift. Ga eerst na welke weg past:

| Weg | Wanneer | Geverifieerde kern |
|---|---|---|
| **Dagvaarding / citation** | Gewone regel | Art. 700, 702, 707 (termijn acht dagen), 710 (termijnen op straffe van nietigheid) |
| **Verzoekschrift op tegenspraak / requête contradictoire** | Alleen waar de wet dat bepaalt (art. 1034bis), bv. in de in art. 704 § 1 bedoelde zaken voor de arbeidsrechtbank | Inhoud art. 1034ter; getuigschrift van woonplaats of rijksregisteruittreksel (art. 1034quater, niet ouder dan 15 dagen); neerlegging of aangetekende zending aan de griffie (art. 1034quinquies); oproeping bij gerechtsbrief (art. 1034sexies) |
| **Vrijwillige verschijning / comparution volontaire** | Partijen zijn het eens om naar de rechter te gaan | Art. 706: gezamenlijk verzoekschrift, ondertekend en gedagtekend op straffe van nietigheid, voor vrederechter, rechtbank van eerste aanleg, arbeidsrechtbank, ondernemingsrechtbank, politierechtbank |
| **Kort geding / référé** | Spoedeisendheid, voorlopige maatregel | Art. 584 (voorzitter, gevallen die hij spoedeisend acht; bij volstrekte noodzakelijkheid op verzoekschrift); art. 1035 (dagvaardingstermijn ten minste twee dagen); art. 1039 (geen nadeel aan de zaak zelf; uitvoerbaar bij voorraad) |
| **Summiere rechtspleging om betaling te bevelen / procédure sommaire d'injonction de payer** | Vaststaande geldschuld, gestaafd door een geschrift dat van de schuldenaar uitgaat | Art. 1338: bevoegdheid vrederechter tot 1.860 euro, en de ondernemingsrechtbank voor geschillen van art. 573 ongeacht het bedrag; aanmaning met betalingstermijn van 15 dagen (art. 1339); verzoekschrift binnen 15 dagen daarna, ondertekend door de advocaat (art. 1340); beschikking binnen 15 dagen (art. 1342); verzet of hoger beroep (art. 1343) |
| **Invordering van onbetwiste geldschulden (B2B) / recouvrement de dettes d'argent non contestées** | Onbetwiste, vaststaande en opeisbare geldschuld tussen in de KBO ingeschreven ondernemingen | Art. 1394/20 e.v.: invordering door de gerechtsdeurwaarder op verzoek van de advocaat van de schuldeiser; aanmaning met betaling binnen de maand en antwoordformulier (art. 1394/21-22); bij betwisting stopt de procedure (art. 1394/23); daarna proces-verbaal van niet-betwisting, uitvoerbaar verklaard (art. 1394/24); uitzonderingen in art. 1394/20 (overheden, partijen niet ingeschreven in de KBO, handelingen buiten de activiteiten van de onderneming, samenloop, de meeste buitencontractuele schulden) |

Leg de keuze kort uit. Past een andere weg, zeg dat en stel (op vraag) het passende stuk op met de templates onder "Alternatieven".

---

## STAP 1: Gegevens verzamelen

Vraag de gebruiker (bundel de vragen in één bericht) naar:

1. **Eiser (demandeur):** naam, voornaam, woonplaats; rijksregisternummer, identificatienummer in het bisregister of ondernemingsnummer (art. 702, 1°); voor een rechtspersoon benaming, rechtsvorm en zetel (art. 703); advocaat (naam, kantoor, gerechtelijk elektronisch adres).
2. **Verweerder (défendeur, cité):** naam, voornaam en woonplaats, bij gebreke daarvan verblijfplaats (art. 702, 2°); voor een onderneming benaming, rechtsvorm, zetel, ondernemingsnummer.
3. **Feiten:** chronologie, overeenkomst, facturen, ingebrekestelling (mise en demeure), reacties, minnelijke pogingen.
4. **Vordering:** hoofdsom, interest (bedongen, wettelijke of handelsinterest), schadebeding, schadevergoeding, ontbinding, dwangsom (astreinte), voorlopige maatregelen.
5. **Gerecht en taal:** welk gerecht, welk arrondissement en welke afdeling; woonplaats verweerder (taalwet).
6. **Procedure:** korte debatten gewenst (art. 735)? Voorstel van conclusietermijnen (art. 747)? Bevoegdheidsbeding of keuze van woonplaats in het contract?
7. **Stukken:** lijst van de stukken waarop de eiser steunt.
8. **Hoedanigheid:** consument of onderneming (bepaalt bevoegdheid, interest, B2B-invordering).

Ontbreken gegevens, gebruik dan plaatshouders `[…]` en som aan het einde op wat moet worden aangevuld. Verzin nooit data, bedragen of nummers.

---

## STAP 2: Bevoegdheid en bevoegd gerecht (compétence)

Controleer de actuele tekst met `search_belgian_legislation` vóór je de keuze in het exploot motiveert.

- **Materiële bevoegdheid (compétence matérielle):**
  - Vrederechter / juge de paix: art. 590, vorderingen tot 5.000 euro (de Koning kan dit bedrag indexeren; een aanpassing wordt uiterlijk in november in het Belgisch Staatsblad bekendgemaakt en geldt vanaf 1 januari: controleer het geldende bedrag), behalve de vorderingen die de wet aan zijn rechtsmacht onttrekt (o.a. art. 569-571, 572bis, 573, 574, 578-583); ongeacht het bedrag de zaken van art. 591 (o.a. huur van onroerende goederen, mede-eigendom, burenhinder, erfdienstbaarheden).
  - Rechtbank van eerste aanleg / tribunal de première instance: art. 568, alle vorderingen behalve die welke rechtstreeks voor het hof van beroep of het Hof van Cassatie komen (familierechtbank en beslagrechter zijn afdelingen/kamers met eigen regels).
  - Ondernemingsrechtbank / tribunal de l'entreprise: art. 573 (geschillen tussen ondernemingen in de zin van art. I.1, 1° WER; een vordering tegen een onderneming kan er ook door een niet-onderneming worden gebracht; een vóór het geschil gesloten bevoegdheidsbeding is in dat opzicht nietig) en art. 574 (o.a. vennootschaps- en insolventiegeschillen).
  - Arbeidsrechtbank / tribunal du travail: art. 578 e.v. (o.a. arbeidsovereenkomsten).
  - Voorzitter in kort geding: art. 584.
- **Territoriale bevoegdheid (compétence territoriale):** art. 624 — naar keuze van de eiser de rechter van de woonplaats van (één van) de verweerder(s), van de plaats waar de verbintenis is ontstaan of moet worden uitgevoerd, of van de gekozen woonplaats; tenzij de wet uitdrukkelijk een rechter aanwijst (zoek dan de bijzondere regel op).
- **Grensoverschrijdend:** internationale bevoegdheid via EU-recht (bv. Verordening Brussel I bis) met `search_eu_legislation` (`in_force_as_of` = vandaag).
- **Aanleg:** vonnissen van rechtbank van eerste aanleg en ondernemingsrechtbank tot 2.500 euro, en van de vrederechter tot 2.000 euro, worden in laatste aanleg gewezen (art. 617, indexeerbaar); beroep tegen de vrederechter gaat naar de rechtbank van eerste aanleg (art. 577); beroepstermijn één maand vanaf betekening (art. 1051).

Gerechtelijke organisatie (voor de juiste benaming in het exploot): vredegerecht (justice de paix) en politierechtbank (tribunal de police); rechtbank van eerste aanleg (tribunal de première instance, met familie- en jeugdrechtbank); ondernemingsrechtbank (tribunal de l'entreprise); arbeidsrechtbank (tribunal du travail); hof van beroep (cour d'appel) voor beroep tegen rechtbank van eerste aanleg en ondernemingsrechtbank; arbeidshof (cour du travail) voor beroep tegen de arbeidsrechtbank; Hof van Cassatie (Cour de cassation), dat de feiten niet opnieuw beoordeelt.

---

## STAP 3: Juridisch onderzoek met IURA MCP (verplicht)

Voer per rechtsvraag meerdere zoekopdrachten uit, in de procestaal (Nederlands of Frans), en herformuleer.

1. **Grondslag van de vordering** met `search_belgian_legislation` (`in_force_as_of` = vandaag; bij oude feiten de datum van de feiten): bv. "niet-nakoming contractuele verbintenis schadevergoeding", "ontbinding wederkerige overeenkomst", "factuur aanvaarding onderneming bewijs", "inexécution contractuelle dommages et intérêts". Let op het overgangsrecht van het nieuwe Burgerlijk Wetboek (Boeken 1, 5, 8 …) versus het oud Burgerlijk Wetboek: kijk naar de geldigheidsperiode in het resultaat en vraag desnoods de datum van de rechtshandeling.
2. **Bewijs (preuve):** Boek 8 van het Burgerlijk Wetboek (wet van 13 april 2019, in werking 1 november 2020). Art. 8.4: wie iets in rechte vordert, moet de rechtshandelingen of feiten bewijzen die daaraan ten grondslag liggen; wie beweert bevrijd te zijn, bewijst dat; alle partijen werken mee aan de bewijsvoering; bij twijfel verliest wie de bewijslast draagt, tenzij de wet anders bepaalt; de rechter kan in uitzonderlijke omstandigheden de bewijslast anders leggen. Art. 8.5 (redelijke mate van zekerheid) en 8.6 (waarschijnlijkheid). Zoek de regels voor het bewijs tegen ondernemingen en van facturen op met `search_belgian_legislation` ("bewijs tegen ondernemingen boekhouding factuur", "preuve à l'égard des entreprises").
3. **Interest (intérêts):**
   - Wettelijke interest (intérêt légal): wet van 5 mei 1865, art. 2 — elk kalenderjaar vastgesteld en in januari in het Belgisch Staatsblad bekendgemaakt. Zoek de regel voor het vertrekpunt (ingebrekestelling) op met `search_belgian_legislation`.
   - Handelstransacties (B2B en met overheden): wet van 2 augustus 2002 betreffende de bestrijding van de betalingsachterstand bij handelstransacties, art. 5 (van rechtswege en zonder ingebrekestelling vanaf de dag na de vervaldag; referentie-interestvoet + acht procentpunten, afgerond tot het hogere halve procentpunt, tenzij anders overeengekomen met inachtneming van art. 7; bekendgemaakt per semester) en art. 6 (forfaitaire vergoeding van 40 euro invorderingskosten, plus redelijke schadeloosstelling voor hogere kosten).
   - **Rentevoeten wijzigen per jaar of semester**: controleer de voeten voor elke betrokken periode (officiële bekendmaking FOD Financiën / Belgisch Staatsblad) met `search_web`; vermeld geen voet zonder bron.
4. **Rechtspraak** met `search_belgian_case_law`: Hof van Cassatie eerst, dan hoven van beroep en rechtbanken; minstens 2-3 zoekopdrachten per kwestie. Controleer elk ECLI met `find_ruling_by_case_number` en lees de kernoverweging met `read_legal_document`.
5. **Grondwettelijk Hof** (`search_belgian_constitutional_court_rulings`) als een bepaling grondwettelijk betwist is; **EU** als een richtlijn of verordening speelt.

Noteer per bron: artikel (met wet en geldigheidsperiode) of ECLI/rolnummer, datum, gerecht, kern, en hoe het de vordering steunt.

---

## STAP 4: Strategie

- **Hoofdorde en ondergeschikte orde (à titre principal / à titre subsidiaire):** orden de vorderingen; elke ondergeschikte vordering moet voor de rechter herkenbaar zijn.
- **Middelen in het exploot (art. 702, 3°):** het voorwerp en een **korte samenvatting** van de middelen volstaan; de volledige uitwerking volgt in de conclusies. Maar: een latere uitbreiding of wijziging van de vordering moet berusten op een feit of akte die in de dagvaarding is aangevoerd (art. 807). Vermeld dus alle feiten en akten waarop je later wil steunen.
- **Bedragen die nog niet vaststaan:** "voorlopig begroot op" / "évalué provisionnellement à".
- **Korte debatten (débats succincts, art. 735):** vraag ze met redenen omkleed in de dagvaarding als de zaak eenvoudig is (bv. niet betwiste schuldvordering). Anders: stel een kalender van conclusietermijnen voor en doe opmerkingen over de instaatstelling (art. 747 § 2, ook in de gedinginleidende akte mogelijk).
- **Voorlopige maatregelen of onderzoeksmaatregelen** vóór de grond: art. 19, derde lid.
- **Voorlopige tenuitvoerlegging:** eindvonnissen zijn in beginsel uitvoerbaar bij voorraad (art. 1397), tenzij de rechter met bijzondere redenen anders beslist; de klassieke formule mag blijven staan, maar motiveer als je uitsluiting van kantonnement vraagt.
- **Kosten:** de verliezende partij wordt in de kosten verwezen (art. 1017); de rechtsplegingsvergoeding (indemnité de procédure) is een forfaitaire tegemoetkoming in de advocatenkosten (art. 1022); de bedragen staan in het KB van 26 oktober 2007 en worden geïndexeerd: vermeld een bedrag alleen na controle van de actuele tabel, anders "het basisbedrag van de rechtsplegingsvergoeding".
- **Minnelijke oplossing:** de rechter bevordert een minnelijke oplossing en kan vragen wat partijen vooraf hebben geprobeerd (art. 730/1); vermeld de pogingen en de ingebrekestelling.
- **Anticipeer op verweer** (verjaring, onbevoegdheid, nietigheid van het exploot, betwisting van facturen, exceptie van niet-uitvoering), maar werk het pas uit in de conclusies.

---

## STRUCTUUR VAN HET EXPLOOT

Gebaseerd op Belgische praktijkmodellen: een algemeen model van exploot van dagvaarding uit de Leuvense cursus "Opstellen van privaatrechtelijke akten", een modeldagvaarding gepubliceerd door legalnews.be, en Franstalige modellen van citations van een Brusselse advocaat. Er is geen wettelijk voorgeschreven volgorde; de verplichte vermeldingen (art. 43 en 702) moeten er wel in staan. Nummer de feiten; de directe stijl is gangbaarder dan de oude stijl met "Aangezien / Attendu que", maar beide komen voor.

### Nederlandstalig model

```
                         EXPLOOT VAN DAGVAARDING

HET JAAR [tweeduizend …], DE [dag] [maand]                    [deurwaarder]

OP VERZOEK VAN:
[Naam en rechtsvorm], met zetel te [adres], ingeschreven in de Kruispuntbank
van Ondernemingen onder het nummer [ondernemingsnummer],
— of —
[Naam, voornamen], wonende te [adres], rijksregisternummer [nummer],

hierna "verzoeker" / "eiser",
die woonplaats kiest op het kantoor van zijn raadsman, mr. [naam], advocaat
te [adres kantoor], [gerechtelijk elektronisch adres],

HEB IK, ondergetekende, [naam], gerechtsdeurwaarder met standplaats te
[plaats], kantoor houdende te [adres],                          [deurwaarder]

GEDAAGD:
[Naam en rechtsvorm], met zetel te [adres], KBO-nummer [nummer],
— of —
[Naam, voornamen], wonende te [adres] (bij gebreke van woonplaats: verblijvende te …),

alwaar ik [wijze van betekening]                                [deurwaarder]

OM TE VERSCHIJNEN voor de [Nederlandstalige] [rechtbank van eerste aanleg /
ondernemingsrechtbank / vrederechter van het … kanton] [arrondissement],
afdeling [plaats], [kamer], zitting houdende in het gerechtsgebouw te [adres],
zaal [..], op [weekdag] [datum] om [uur],

TENEINDE:

I. Feiten
1. [Feit, met datum en stuk]
2. […]

II. Vordering en middelen (korte samenvatting)
3. [Grondslag: wettelijke bepaling, contractbeding — na verificatie]
4. [Berekening hoofdsom, interest, schadebeding]
5. [Minnelijke pogingen en ingebrekestelling van … zijn zonder gevolg gebleven]

III. Bevoegdheid en procedure
6. [Materiële en territoriale bevoegdheid: art. … Ger.W.]
7. [Eventueel] De zaak vergt slechts korte debatten omdat …; verzoeker vraagt
   toepassing van artikel 735 Ger.W.
   — of — Verzoeker stelt de volgende conclusietermijnen voor (art. 747 Ger.W.): …

OM DEZE REDENEN,
en om alle andere, zelfs ambtshalve in te roepen, onder voorbehoud van alle
rechten en zonder enige nadelige erkentenis,

BEHAGE HET DE RECHTBANK / DE VREDERECHTER:

de vordering ontvankelijk en gegrond te verklaren;
dienvolgens gedaagde te veroordelen om aan verzoeker te betalen:
  - de hoofdsom van [bedrag] euro;
  - [de bedongen interest tegen … % / de interest volgens de wet van
    2 augustus 2002 / de wettelijke interest] op [bedrag] vanaf [datum] tot
    de datum van volledige betaling;
  - [het forfaitair schadebeding van … / de forfaitaire vergoeding van
    art. 6 wet 2 augustus 2002];
  - de gerechtelijke interest vanaf heden;
[ondergeschikt: …]
gedaagde te veroordelen tot de kosten van het geding, met inbegrip van de
rechtsplegingsvergoeding (art. 1022 Ger.W.) [bedrag na controle];
het vonnis uitvoerbaar bij voorraad te verklaren, niettegenstaande elk
rechtsmiddel en zonder borgstelling [en met uitsluiting van kantonnement — motiveren].

Ik heb de gedaagde, sprekende als voormeld, afschrift van dit exploot gelaten
[en van de erin vermelde stukken].                             [deurwaarder]

WAARVAN AKTE.
Kosten: […]                                                    [deurwaarder]
```

### Modèle en français

```
                            EXPLOIT DE CITATION

L'AN [deux mille …], LE [jour] [mois]                          [huissier]

À LA REQUÊTE DE :
[Dénomination et forme juridique], dont le siège est établi à [adresse],
inscrite à la Banque-Carrefour des Entreprises sous le numéro [numéro],
— ou —
[Nom, prénoms], domicilié(e) à [adresse], numéro de registre national [numéro],

ci-après « le requérant » / « la demanderesse »,
ayant pour conseil Maître [nom], avocat à [adresse du cabinet], [adresse
judiciaire électronique], au cabinet duquel il fait élection de domicile,

JE SOUSSIGNÉ(E), [nom], huissier de justice de résidence à [lieu],
y demeurant [adresse],                                          [huissier]

AI DONNÉ CITATION À :
[Dénomination et forme juridique], dont le siège est établi à [adresse], BCE n° [numéro],
— ou —
[Nom, prénoms], domicilié(e) à [adresse] (à défaut de domicile : résidant à …),

où étant et parlant à [mode de signification]                   [huissier]

À COMPARAÎTRE devant le [tribunal de première instance francophone de … /
tribunal de l'entreprise de … / juge de paix du … canton de …], division [lieu],
[chambre], siégeant au palais de justice, [adresse], salle [..],
le [jour] [date] à [heure],

POUR :

I. Les faits
1. [Fait, date et pièce]
2. […]

II. L'objet de la demande et l'exposé sommaire des moyens
3. [Fondement : disposition légale, clause contractuelle — après vérification]
4. [Calcul : principal, intérêts, clause pénale]
5. [Les tentatives de règlement amiable et la mise en demeure du … sont restées sans suite]

III. Compétence et procédure
6. [Compétence matérielle et territoriale : art. … C. jud.]
7. [Le cas échéant] La cause n'appelle que des débats succincts parce que … ;
   le requérant sollicite l'application de l'article 735 du Code judiciaire.
   — ou — Le requérant propose le calendrier de mise en état suivant (art. 747 C. jud.) : …

PAR CES MOTIFS,
et tous autres à faire valoir en prosécution de cause, même d'office,
sous toutes réserves et sans reconnaissance préjudiciable,

PLAISE AU TRIBUNAL / À MONSIEUR OU MADAME LE JUGE DE PAIX :

dire la demande recevable et fondée ;
en conséquence, condamner la citée à payer au requérant :
  - la somme principale de [montant] euros ;
  - [les intérêts conventionnels au taux de … % / les intérêts prévus par la
    loi du 2 août 2002 / les intérêts légaux] sur [montant] depuis le [date]
    jusqu'au complet paiement ;
  - [la clause pénale de … / l'indemnité forfaitaire de l'article 6 de la loi
    du 2 août 2002] ;
  - les intérêts judiciaires à dater de la présente citation ;
[à titre subsidiaire : …]
condamner la citée aux dépens, en ce compris l'indemnité de procédure
(art. 1022 C. jud.) [montant après vérification] ;
déclarer le jugement à intervenir exécutoire par provision, nonobstant tout
recours et sans garantie [et sans cantonnement — à motiver].

Et pour que la citée n'en ignore, je lui ai, étant et parlant comme dit
ci-dessus, laissé copie du présent exploit [et des pièces y mentionnées]. [huissier]

DONT ACTE.
Coût : […]                                                      [huissier]
```

### Lijst van stukken / Liste des pièces (optioneel bij het exploot)

Een inventaris is bij de dagvaarding niet verplicht (wel bij conclusies, art. 742), maar een lijst van de stukken waarop de eiser steunt is nuttig. Deel de stukken mee binnen acht dagen na de inleiding van de zaak, behalve bij korte debatten (art. 736).

```
STUKKEN VAN VERZOEKER                    PIÈCES DU REQUÉRANT
1. Overeenkomst van [datum]              1. Convention du [date]
2. Facturen nrs. […] van [data]          2. Factures n° […] des [dates]
3. Ingebrekestelling van [datum]         3. Mise en demeure du [date]
4. […]                                   4. […]
```

---

## Alternatieven: korte templates

### Verzoekschrift op tegenspraak / Requête contradictoire (art. 1034bis-1034sexies)

Alleen waar de wet het toelaat. Verplichte vermeldingen (art. 1034ter, op straffe van nietigheid): dag, maand en jaar; naam, voornaam, woonplaats, hoedanigheid en rijksregister-, bis- of ondernemingsnummer van de verzoeker; naam, voornaam, woonplaats en hoedanigheid van de op te roepen persoon; voorwerp en korte samenvatting van de middelen; de rechter bij wie de vordering aanhangig wordt gemaakt; handtekening van verzoeker of advocaat. Bijlage: getuigschrift van woonplaats of rijksregisteruittreksel (art. 1034quater).

```
VERZOEKSCHRIFT OP TEGENSPRAAK             REQUÊTE CONTRADICTOIRE
(art. 1034bis e.v. Ger.W.)               (art. 1034bis et s. C. jud.)

Aan de [rechter], [gerecht], [afdeling]  À [Monsieur/Madame le …], [juridiction], [division]

Verzoeker: […]                           Requérant : […]
Op te roepen partij: […]                 Partie à convoquer : […]
Voorwerp en middelen: […]                Objet et exposé des moyens : […]

OM DEZE REDENEN,                         PAR CES MOTIFS,
verzoekt verzoeker de [rechter] […]      le requérant sollicite qu'il plaise au […] de […]

[Plaats], [datum]                        [Lieu], le [date]
[Handtekening verzoeker of advocaat]     [Signature du requérant ou de son avocat]
Bijlage: getuigschrift van woonplaats    Annexe : certificat de domicile
```

### Gezamenlijk verzoekschrift (vrijwillige verschijning) / Requête conjointe (comparution volontaire) — art. 706

Ondertekend en gedagtekend door alle partijen op straffe van nietigheid; neergelegd ter griffie of aangetekend toegezonden. Gebruik dezelfde opbouw met "Verzoekers" / "Les requérants" en een gezamenlijke vraag om een zitting binnen vijftien dagen indien gewenst.

### Kort geding / Référé

Gebruik het dagvaardingsmodel, gericht aan "de voorzitter van de [rechtbank] zitting houdend in kort geding" / "Monsieur/Madame le président du tribunal …, siégeant en référé". Werk de **spoedeisendheid** (urgence) en het **voorlopige karakter** van de gevraagde maatregel uitdrukkelijk uit (art. 584, 1039). Termijn van dagvaarding ten minste twee dagen (art. 1035).

### Summiere rechtspleging / Procédure sommaire d'injonction de payer (art. 1338-1344)

1. Aanmaning (sommation) bij deurwaardersexploot of aangetekende brief met ontvangstbewijs, met de weergave van de artikelen van het hoofdstuk, aanmaning om binnen vijftien dagen te betalen, het gevorderde bedrag en de bevoegde rechter (art. 1339).
2. Binnen vijftien dagen na die termijn: verzoekschrift in tweevoud met dag, maand, jaar; identiteit van de verzoeker; voorwerp en nauwkeurige opgave van het bedrag met specificatie en gronden; aanwijzing van de rechter; handtekening van de advocaat; bijlagen: kopie van het geschrift en bewijs van de aanmaning (art. 1340).

### Invordering van onbetwiste geldschulden / Recouvrement de dettes non contestées (art. 1394/20 e.v.)

Geen procedure voor de rechter: de advocaat van de schuldeiser geeft opdracht aan een gerechtsdeurwaarder. Help de gebruiker met (a) de toets of de schuld onder het toepassingsgebied valt (art. 1394/20: B2B, KBO-inschrijving, onbetwist, vaststaand en opeisbaar, uitzonderingen), (b) een duidelijke beschrijving van de verbintenis en verantwoording van alle bedragen voor de aanmaning (art. 1394/21; interest en schadebedingen samen hoogstens 10 % van de hoofdsom volgens art. 1394/20). Het formulier en het proces-verbaal van niet-betwisting volgen een model dat de Koning bepaalt (art. 1394/25): de deurwaarder stelt die op.

---

## Redactieregels

- **Precies en volledig:** elk feit met datum, bedrag en stuk; bedragen niet afronden.
- **Partijaanduiding:** consequent "verzoeker/eiser" en "gedaagde" (le requérant/la demanderesse, le cité/la citée).
- **Korte samenvatting, niet alles:** het exploot bevat het voorwerp en de korte samenvatting van de middelen; de volledige juridische uitwerking komt in de conclusies (zie `conclusies-conclusions`). Neem wel alle feiten en akten op die je later nodig hebt (art. 807).
- **Wettelijke verwijzingen:** "art. 702, 3° Ger.W." / "art. 702, 3°, C. jud."; nieuw Burgerlijk Wetboek: "art. 8.4 BW" / "art. 8.4 C. civ."; oud Burgerlijk Wetboek: "art. 1134 oud BW" / "art. 1134 de l'ancien C. civ." (alleen na controle van het toepasselijke overgangsrecht).
- **Rechtspraak:** "Cass. [datum], [rolnummer], ECLI:BE:CASS:[…]"; "GwH [datum], nr. [nr]/[jaar]" / "C.C., [date], n° [nr]/[année]"; Belgisch Staatsblad "B.S. [datum]" / "M.B. [date]". Alleen na verificatie met `find_ruling_by_case_number`.
- **Geen persoonsgegevens verzinnen:** rijksregisternummers, KBO-nummers en adressen alleen van de gebruiker.

---

## Bestand

Maak een .docx als de omgeving bestanden kan aanmaken; geef anders de volledige tekst in het antwoord.

> Claude: gebruik de `docx`-skill voor het Word-bestand.

Opmaak: A4, Times New Roman of Arial 11-12 pt (volledige ondersteuning van é, è, ç, ë, ï, ô), marges 2,5 cm, titel gecentreerd en vet, genummerde feiten, deurwaardersvelden grijs gemarkeerd of tussen vierkante haken, UTF-8.

---

## Checklist vóór oplevering

**Art. 702 Ger.W. (op straffe van nietigheid), naast art. 43:**
- [ ] 1° naam, voornaam, woonplaats eiser + rijksregister-, bis- of ondernemingsnummer
- [ ] 2° naam, voornaam, woonplaats (of verblijfplaats) gedaagde
- [ ] 3° voorwerp en korte samenvatting van de middelen
- [ ] 4° de rechter bij wie de vordering aanhangig wordt gemaakt
- [ ] 5° plaats, dag en uur van de zitting
- [ ] Rechtspersonen: benaming, rechtsvorm, zetel (art. 703)
- [ ] Velden van de gerechtsdeurwaarder (art. 43) gemarkeerd, niet ingevuld

**Procedure en taal:**
- [ ] Juiste inleidingswijze (dagvaarding, verzoekschrift, vrijwillige verschijning, kort geding, summiere rechtspleging, B2B-invordering)
- [ ] Materieel en territoriaal bevoegd gerecht, juiste benaming en afdeling
- [ ] Procestaal volgens de taalwet; exploot volledig in die taal
- [ ] Termijn: zitting ten vroegste acht dagen na betekening (art. 707; kort geding: twee dagen, art. 1035; verlenging voor partijen zonder woonplaats in België, art. 55)
- [ ] Korte debatten (art. 735) of kalendervoorstel (art. 747) gemotiveerd

**Inhoud:**
- [ ] Elke bepaling geverifieerd met `search_belgian_legislation` (geldigheidsperiode klopt met de datum)
- [ ] Elk arrest bestaat (`find_ruling_by_case_number`) en de aangehaalde overweging is gelezen
- [ ] Rentevoeten en rechtsplegingsvergoeding alleen met bron voor de juiste periode
- [ ] Alle feiten en akten voor latere uitbreiding van de vordering staan erin
- [ ] Hoofdorde en ondergeschikte orde duidelijk
- [ ] Plaatshouders `[…]` opgesomd voor de gebruiker
- [ ] Disclaimer: ontwerp ter controle door advocaat en gerechtsdeurwaarder, geen juridisch advies
