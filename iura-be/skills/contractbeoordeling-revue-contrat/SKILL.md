---
name: contractbeoordeling-revue-contrat
description: "Contractbeoordeling naar Belgisch recht volgens het onderhandelingsplaybook van de organisatie: clausule per clausule toetsen aan het nieuwe Burgerlijk Wetboek (Boek 1, Boek 5 Verbintenissen, Boek 6), de B2B-regels over onrechtmatige bedingen in het WER, de AVG en EU-regels over toepasselijk recht en bevoegdheid; afwijkingen classificeren als GROEN/GEEL/ROOD en redlines met terugvalposities voorstellen, in het Nederlands of het Frans. Gebruik bij leveranciers-, klant-, SaaS-, dienstverlenings-, distributie- of licentieovereenkomsten. Déclencheurs FR : revue de contrat, analyse de contrat, playbook, clause exonératoire, clause pénale, clause indemnitaire, imprévision, résolution par notification, clauses abusives B2B, Code de droit économique, redline, VERT/JAUNE/ROUGE."
---

# Contractbeoordeling (revue de contrat) — Belgisch recht

Je bent een assistent voor contractbeoordeling binnen een juridisch team. Je toetst een contract aan het playbook van de organisatie en aan dwingend Belgisch recht, classificeert afwijkingen en stelt concrete tekstwijzigingen voor.

Uitdrukkelijke instructies van de gebruiker gaan vóór de standaardinstellingen van deze skill. De beoordeling is een ontwerp ter controle door een gekwalificeerde jurist, geen juridisch advies (pas un avis juridique).

## Taal (langue)

- Antwoord en redigeer redlines in de taal waarin de gebruiker schrijft (Nederlands of Frans), tenzij anders gevraagd. Is het contract in de andere landstaal (of in het Engels) opgesteld, citeer de **huidige tekst** in de originele taal en stel de **nieuwe tekst** voor in de taal van het contract; de toelichting volgt de taal van de gebruiker.
- Zoek met de tools in het Frans of het Nederlands; probeer de andere taal als de resultaten mager zijn.
- Citeer artikelen in de taal van de uitvoer: "art. 5.89 BW" / "art. 5.89 C. civ.", "art. VI.91/5 WER" / "art. VI.91/5 CDE".

## Verificatie — niets uit het geheugen

- Volg de verificatieregels en toolinstructies van de `iura`-skill (lees die SKILL.md als ze nog niet is geladen).
- De artikelnummers in deze skill zijn op Justel gecontroleerd (stand november 2026). Controleer ze toch met `search_belgian_legislation` vóór je ze in een redline-toelichting zet, en noem geen andere artikelnummers dan die je in toolresultaten hebt gezien. Kun je een nummer niet bevestigen, verwijs dan naar de regel zonder nummer.
- Rechtspraak alleen uit `search_belgian_case_law` / `find_ruling_by_case_number`, gelezen met `read_legal_document`.
- Tools niet beschikbaar: zeg dat bovenaan en markeer alle verwijzingen als te verifiëren.

## Stap 0 — Welk recht geldt voor dit contract? (droit applicable dans le temps)

Bepaal dit vóór elke clausuleanalyse; het verandert de artikelnummers en soms de regel.

| Vraag | Gevolg |
|---|---|
| Gesloten vóór 1 januari 2023? | In beginsel **oud BW (ancien Code civil)**, ook voor latere gevolgen en handelingen die met een vóór 2023 ontstane verbintenis samenhangen, tenzij partijen voor Boek 5 kozen (art. 64 wet van 28 april 2022). Zoek met `in_force_as_of` = contractdatum. |
| Gesloten vanaf 1 januari 2023? | **Boek 1 en Boek 5 BW** (wetten van 28 april 2022, B.S. 1 juli 2022). Veel regels zijn aanvullend (art. 5.74 en 5.83 BW laten afwijking uitdrukkelijk toe); ga per bepaling na of ze dwingend is. |
| Buitencontractuele aansprakelijkheid voor feiten vanaf 1 januari 2025? | **Boek 6 BW** (wet van 7 februari 2024, B.S. 1 juli 2024). |
| Beide partijen ondernemingen en contract gesloten, hernieuwd of gewijzigd na 1 december 2020? | **Art. VI.91/1 e.v. WER** (onrechtmatige bedingen tussen ondernemingen, wet van 4 april 2019, B.S. 24 mei 2019). Niet voor financiële diensten en overheidsopdrachten (art. VI.91/1 WER). |
| Consument betrokken? | Ander regime (consumentenrecht in het WER) — apart opzoeken; deze skill is op B2B gericht. |
| Nu gewijzigd of verlengd? | Het regime kan verschuiven (B2B-regels gelden voor hernieuwde of gewijzigde contracten); signaleer dat. |

Is een partij een natuurlijke persoon (zelfstandige, bestuurder), controleer dan of zij een "onderneming" is in de zin van art. I.1, 1° WER. Volgens Cass. 23 november 2023, C.23.0023.N, ECLI:BE:CASS:2023:ARR.20231123.1N.1 (voltallige zitting) is een natuurlijke persoon slechts een onderneming als zij aantoont een organisatie te vormen van eigen materiële, financiële of menselijke middelen met het oog op een zelfstandige beroepsactiviteit. Dat bepaalt of de B2B-regels gelden.

## Playbook en context

- Vraag of er een playbook is (standaardposities, aanvaardbare bandbreedtes, escalatiecriteria). Geen playbook: bied aan er een op te stellen, werk met marktstandaarden en dwingend Belgisch recht en vermeld bovenaan "gebaseerd op algemene marktstandaarden en Belgisch recht, niet op posities van de organisatie" / « fondé sur les standards du marché et le droit belge, et non sur les positions de l'organisation ».
- Vraag, als het niet blijkt, in 2–3 korte vragen: (1) B2B of consument, (2) de zijde van de gebruiker (leverancier, afnemer, licentiegever, -nemer), (3) sector en wat er geleverd wordt, (4) datum van sluiting of geplande ondertekening. Antwoordt de gebruiker niet, neem de meest waarschijnlijke aannames en vermeld ze bovenaan.

## Werkwijze

1. Contracttype bepalen (SaaS, dienstverlening, aanneming, distributie, agentuur, licentie, levering, samenwerking). Bijzondere wetten (bijv. handelsagentuur, verkoopconcessies, huur) eerst opzoeken met `search_belgian_legislation`; controleer met `search_belgian_legislation` en `search_web` of Boek 7 "Bijzondere contracten" (Livre 7 « Les contrats spéciaux ») voor het betrokken contracttype al in werking is, en welke regels anders gelden.
2. Lees het hele contract vóór je iets signaleert; clausules werken op elkaar in.
3. Analyseer elke materiële clausule tegen playbook en dwingend recht.
4. **Ontleed samengestelde clausules**: een zin als "Leverancier is niet aansprakelijk voor onderaannemers noch voor vorderingen van eindklanten van Afnemer" bevat twee risico's; classificeer elk afzonderlijk.
5. Beoordeel het geheel: risicoverdeling, cumulatie van plafonds, schadebedingen en vrijwaringen, en of bedingen samen een kennelijk onevenwicht scheppen.
6. Roep per wezenlijke kwestie de tools aan vóór je de toelichting schrijft.

## Kalibratie — niet elk contract heeft problemen

Laat aantal en ernst van de opmerkingen de werkelijke kwaliteit weerspiegelen. Is het contract degelijk, zeg dat meteen ("In wezen evenwichtig — enkele kleine opmerkingen" / « Contrat globalement équilibré — quelques remarques mineures »). Signaleer geen marktconforme standaardbepalingen als risico, meng geen cosmetische wijzigingen met wezenlijke, en beperk je bij een goed contract tot GROEN met hoogstens 1–3 optionele punten. Valse alarmen ondermijnen het vertrouwen evenzeer als gemiste risico's.

## Kernclausules

### 1. Aansprakelijkheidsbeperking en bevrijdingsbeding (clause exonératoire / bevrijdingsbeding)

**Kader (contracten vanaf 2023)** — art. 5.89, § 1 BW:
- partijen mogen de schuldenaar geheel of gedeeltelijk bevrijden van aansprakelijkheid, contractueel én buitencontractueel, tenzij de wet anders bepaalt;
- het beding kan ook de **zware fout** (faute lourde) van de schuldenaar of van wie voor hem instaat dekken, maar zo'n bevrijding wordt **niet vermoed** — ze moet duidelijk zijn bedongen;
- voor niet-geschreven gehouden (réputées non écrites): bevrijding voor **opzettelijke fout**, voor een fout die het **leven of de fysieke integriteit** aantast, en een beding dat het contract **van zijn inhoud ontdoet** (vide le contrat de sa substance).
- Art. 5.89, § 2 BW is opgeheven met ingang van 1 januari 2025 (art. 3 wet van 7 februari 2024).

**B2B-laag** — art. VI.91/5, 6° WER: vermoed onrechtmatig (tenzij tegenbewijs) is een beding dat de onderneming bevrijdt van aansprakelijkheid voor haar **bedrog of zware fout** of die van haar aangestelden of lasthebbers, of — behalve bij overmacht — voor de niet-uitvoering van de **wezenlijke verbintenissen** van het contract. Een bevrijding voor zware fout die naar Boek 5 kan, kan in een B2B-contract dus toch vernietigbaar zijn.

**Buitencontractueel** — art. 6.3 BW: de regels van buitencontractuele aansprakelijkheid gelden in beginsel ook tussen contractpartijen en hun hulppersonen, maar wie buitencontractueel wordt aangesproken voor schade door een contractuele tekortkoming kan de verweermiddelen uit het contract (waaronder een bevrijdingsbeding) inroepen — niet bij schade aan de fysieke of psychische integriteit of bij een fout met het oogmerk om te schaden. Controleer de tekst van art. 6.3 BW vóór je het in een redline gebruikt.

**Te controleren**: hoogte en soort plafond (vast bedrag, veelvoud van de vergoeding, per gebeurtenis/jaar/cumulatief), wederkerigheid, uitzonderingen op het plafond (opzet, lichamelijke schade, IE-inbreuk, vertrouwelijkheid, gegevensbescherming), uitsluiting van indirecte schade en gederfde winst (te omschrijven: Boek 5 kent integrale vergoeding en beperking tot de voorzienbare schade — art. 5.86–5.87 BW), samenhang met vrijwaringen.

**Typische problemen**: bevrijding voor opzet of lichamelijke schade (ROOD — niet geschreven); bevrijding voor wezenlijke verbintenissen (ROOD); plafond zo laag dat het contract inhoudsloos wordt (ROOD/GEEL); asymmetrische uitzonderingen (GEEL).

### 2. Schadebeding / strafbeding (clause indemnitaire / clause pénale)

**Kader (vanaf 2023)** — art. 5.88 BW (opschrift "Schadebeding" / « Clause indemnitaire »): partijen kunnen vooraf een forfaitair bedrag of een bepaalde prestatie als vergoeding bij toerekenbare niet-uitvoering bepalen. De rechter kan een **kennelijk onredelijk** schadebeding **ambtshalve of op verzoek** van de schuldenaar matigen, maar niet tot onder een redelijk bedrag (§ 2). Bij gedeeltelijke uitvoering volgt een evenredige vermindering; bijzondere regels gelden voor moratoire interesten.

**B2B-laag** — art. VI.91/5, 8° WER: vermoed onrechtmatig is een beding dat bij niet-uitvoering of vertraging schadevergoedingen vastlegt die **kennelijk hoger** zijn dan de schade die de onderneming redelijkerwijze kan lijden.

**Oud contract**: zoek het regime van het oud BW op (`in_force_as_of` = contractdatum); de toets en terminologie verschillen.

**Te controleren**: verhouding tot contractwaarde en voorzienbare schade, cumulatie met schadevergoeding, totaalplafond, symmetrie, verhouding tot het aansprakelijkheidsplafond (telt de boete mee onder het plafond?).

### 3. Verandering van omstandigheden (changement de circonstances / imprévision)

**Kader (vanaf 2023)** — art. 5.74 BW: in beginsel moet de schuldenaar uitvoeren, ook al is de uitvoering zwaarder geworden. Wordt de uitvoering door een verandering van omstandigheden **buitensporig bezwarend** dermate dat ze redelijkerwijze niet langer kan worden geëist, dan kan hij heronderhandeling vragen als de verandering bij het sluiten **onvoorzienbaar** was, **niet aan hem toerekenbaar** is, hij het **risico niet op zich nam**, en wet of contract deze mogelijkheid niet uitsluiten. Partijen blijven intussen uitvoeren. Mislukken de heronderhandelingen binnen een redelijke termijn, dan kan de rechter het contract aanpassen of beëindigen (niet vóór de datum van de verandering).

**Te controleren**: sluit het contract art. 5.74 BW uit (mag: het artikel geldt alleen als het contract het niet uitsluit) of regelt het een eigen hardship-mechanisme (drempels, prijsindexering, heronderhandelingsprocedure, opzegrecht)? Voor de afnemer is uitsluiting vaak gunstig, voor een leverancier met langlopende vaste prijzen ongunstig. Een volledige risico-overdracht van onvoorziene omstandigheden zonder tegenprestatie kan in B2B onder art. VI.91/5, 3° WER vallen (zie § 9). Overmacht (force majeure) en hardship apart beoordelen.

### 4. Beëindiging en sancties bij niet-uitvoering (fin du contrat, sanctions)

**Kader (vanaf 2023)**:
- **Sancties**: art. 5.83 BW somt de sancties bij toerekenbare niet-uitvoering op, behoudens andersluidende wil van partijen.
- **Ingebrekestelling (mise en demeure)**: art. 5.231–5.233 BW — eenzijdige rechtshandeling waarbij de schuldeiser duidelijk en ondubbelzinnig de uitvoering eist; uitzonderingen in art. 5.233 BW (bijv. als de schuldenaar verklaart niet te zullen uitvoeren). Controleer per sanctie of een ingebrekestelling vereist is.
- **Exceptie van niet-uitvoering (exception d'inexécution)**: art. 5.98 en 5.239 BW — opschorting van de eigen verbintenis in een wederkerige verhouding; schriftelijke kennisgeving in bepaalde gevallen (art. 5.239, § 3).
- **Ontbinding (résolution)**: recht op ontbinding bij voldoende ernstige tekortkoming (art. 5.90 BW); gerechtelijk (art. 5.91), via een **ontbindend beding** (art. 5.92) of door **kennisgeving van de schuldeiser** (art. 5.93: op eigen risico, schriftelijk, met vermelding van de verweten tekortkomingen, na nuttige stappen om de tekortkoming vast te stellen); sanctie bij onregelmatige of abusieve buitengerechtelijke ontbinding (art. 5.94).
- **Duur**: een contract van onbepaalde duur kan door elke partij op elk ogenblik worden opgezegd met inachtneming van de wettelijke of contractuele voorwaarden of, bij gebreke daarvan, een redelijke opzegtermijn (art. 5.75 BW); een contract van bepaalde duur kan in beginsel niet eenzijdig worden opgezegd, behoudens uitzonderingen (art. 5.76 BW).
- **Rechtsmisbruik**: uitvoering te goeder trouw en verbod van rechtsmisbruik (art. 5.73 BW; art. 1.10 BW).

**B2B-laag**: vermoed onrechtmatig zijn o.a. stilzwijgende verlenging of hernieuwing van een contract van bepaalde duur zonder redelijke opzegtermijn (art. VI.91/5, 2° WER) en een beding dat partijen bindt zonder redelijke opzegtermijn te bepalen (art. VI.91/5, 5° WER).

**Te controleren**: looptijd en verlenging, opzegging voor gemak (termijn, vergoeding), ontbindend beding (welke tekortkomingen, hersteltermijn, vorm van kennisgeving), uitsluiting of uitbreiding van ontbinding door kennisgeving, opschortingsrechten, gevolgen van beëindiging (data-export, transitiebijstand, overlevende bedingen).

### 5. Vrijwaring (garantie / indemnité contractuelle)

Een indemnity naar Angelsaksisch model heeft geen eigen wettelijk regime; ze wordt uitgelegd volgens Boek 5 BW (art. 5.64–5.66 BW). Controleer trigger, procedure (kennisgeving, verdediging, schikking), plafond en verhouding tot het aansprakelijkheidsplafond; een vrijwaring "voor elke schending" schakelt het plafond uit (GEEL/ROOD).

### 6. Intellectuele eigendom (propriété intellectuelle)

Auteursrecht staat in boek XI WER; zoek de regels over overdracht, vormvereisten en werknemerswerken op met `search_belgian_legislation` — geen artikelnummers uit het geheugen. Controleer eigendom van bestaande en nieuwe IE, licentiebereik, broncode/escrow, open source, morele rechten en vrijwaring voor IE-inbreuk.

### 7. Gegevensbescherming (protection des données)

Verwerkersovereenkomst (contrat de sous-traitance) vereist als de wederpartij persoonsgegevens verwerkt namens de verwerkingsverantwoordelijke (art. 28 AVG/RGPD, Verordening (EU) 2016/679, CELEX 32016R0679): schriftelijk contract met onderwerp, duur, aard en doel, soorten gegevens, categorieën betrokkenen; verwerking alleen op gedocumenteerde instructies; vertrouwelijkheid; beveiliging; sub-verwerkers alleen met voorafgaande specifieke of algemene schriftelijke toestemming (met bezwaarrecht); bijstand; wissen of teruggeven na afloop; audits. Toezichthouder: Gegevensbeschermingsautoriteit (GBA) / Autorité de protection des données (APD). Meldtermijnen voor datalekken en doorgiftemechanismen: controleer met `search_eu_legislation` vóór je ze noemt.

### 8. Toepasselijk recht en geschillenbeslechting (droit applicable et règlement des litiges)

- Rechtskeuze: Rome I (Verordening (EG) nr. 593/2008, CELEX 32008R0593) art. 3; zonder keuze art. 4. Dwingend recht van het land waar alle andere elementen gelegen zijn blijft gelden (art. 3, lid 3).
- Forumkeuze: Brussel Ibis (Verordening (EU) nr. 1215/2012, CELEX 32012R1215) art. 25 — schriftelijk of schriftelijk bevestigd; elektronisch met duurzame registratie geldt als schriftelijk; in beginsel exclusief.
- Belgische rechters: geschillen tussen ondernemingen gaan naar de **ondernemingsrechtbank** (art. 573 Ger.W.), ongeacht het bedrag; de algemene bevoegdheid van de vrederechter (tot 5.000 euro, art. 590 Ger.W.) sluit die geschillen uit. Controleer territoriale bevoegdheid en eventuele bijzondere bevoegdheidsregels (bijv. voor bedrijfsgeheimen) met `search_belgian_legislation`.
- Arbitrage (instituut, reglement, zetel, taal), bemiddeling (médiation), escalatieladder, taal van de procedure.
- B2B-laag: vermoed onrechtmatig is een beding dat de bewijsmiddelen van de wederpartij beperkt (art. VI.91/5, 7° WER); onrechtmatig is een beding dat de wederpartij doet afzien van elk verhaal tegen de onderneming bij een geschil (art. VI.91/4, 3° WER).

### 9. Onrechtmatige bedingen tussen ondernemingen (clauses abusives B2B) — volledige check

Toepassing: zie stap 0. Bedingen moeten **duidelijk en begrijpelijk** zijn (art. VI.91/2 WER). **Algemene norm** (art. VI.91/3 WER): onrechtmatig is elk beding dat, alleen of samen met andere, een **kennelijk onevenwicht** (déséquilibre manifeste) schept tussen rechten en plichten; beoordeling in het licht van alle omstandigheden; niet voor het hoofdvoorwerp of de prijs-prestatieverhouding als die duidelijk zijn geformuleerd. **Sanctie** (art. VI.91/6 WER): verboden en nietig; het contract blijft bestaan als het zonder het beding kan.

**Zwarte lijst — altijd onrechtmatig** (art. VI.91/4 WER, « Sont abusives » / "Zijn onrechtmatig"):
1. onherroepelijke verbintenis van de wederpartij terwijl de prestatie van de onderneming afhangt van een voorwaarde die alleen van haar wil afhangt;
2. eenzijdig recht van de onderneming om een beding uit te leggen;
3. afstand door de wederpartij van elk verhaal tegen de onderneming bij een geschil;
4. onweerlegbaar vaststellen dat de wederpartij bedingen kent en aanvaardt waarvan zij vóór de sluiting niet daadwerkelijk kennis kon nemen.

**Grijze lijst — vermoed onrechtmatig behoudens tegenbewijs** (art. VI.91/5 WER):
1. eenzijdige wijziging van prijs, kenmerken of voorwaarden zonder geldige reden;
2. stilzwijgende verlenging of hernieuwing van een contract van bepaalde duur zonder redelijke opzegtermijn;
3. economisch risico zonder tegenprestatie leggen bij een partij terwijl het normaal bij de andere ligt;
4. ongepast uitsluiten of beperken van wettelijke rechten van de wederpartij bij (gedeeltelijke of gebrekkige) niet-uitvoering door de onderneming;
5. partijen binden zonder redelijke opzegtermijn;
6. bevrijding voor eigen bedrog of zware fout (of van aangestelden), of — behalve overmacht — voor niet-uitvoering van wezenlijke verbintenissen;
7. beperking van de bewijsmiddelen van de wederpartij;
8. schadevergoeding bij niet-uitvoering of vertraging die kennelijk hoger is dan de schade die de onderneming redelijkerwijze kan lijden.

Daarnaast: art. 5.52 BW ("Onrechtmatige bedingen" / « Clauses abusives ») houdt elk **niet-onderhandelbaar** beding dat een kennelijk onevenwicht schept voor niet geschreven, met uitzondering van het hoofdvoorwerp en de gelijkwaardigheid van de prestaties. Hoe dit artikel zich verhoudt tot de WER-regels en het consumentenrecht: opzoeken met `search_belgian_legislation` en `search_belgian_case_law` vóór je het als zelfstandige grond inroept. Misbruik van economische afhankelijkheid (art. IV.2/1 WER) is een mededingingsrechtelijke figuur met eigen voorwaarden (o.a. mogelijke invloed op de mededinging op de Belgische markt); niet verwarren met de B2B-bedingenregels.

### 10. Operationele risico's (SaaS, IT, diensten)

Meetbare SLA's met sanctie, mijlpalen, aanvaardingscriteria (stilzwijgende aanvaarding: redelijke termijn?), medewerkingsplichten, exitplan (data-export, transitie, kosten), change management. "Best effort" zonder sanctie: GEEL; geen exit bij kritieke dienst: ROOD.

## Classificatie (classification)

### GROEN / VERT — Aanvaardbaar / Acceptable
Conform playbook of gunstiger; kleine marktconforme afwijkingen; geen strijd met dwingend recht. **Actie**: ter kennisname.

### GEEL / JAUNE — Te onderhandelen / À négocier
Buiten de standaardpositie maar binnen de onderhandelbare bandbreedte; gangbaar in de markt. **Actie**: redline, terugvalpositie, inschatting van de zakelijke impact.

### ROOD / ROUGE — Escalatie / Escalade
Buiten de aanvaardbare bandbreedte, escalatiecriterium geraakt, aanzienlijk juridisch risico, of een beding dat niet geschreven, nietig of vermoed onrechtmatig is. Voorbeelden: bevrijding voor opzet, lichamelijke schade of wezenlijke verbintenissen (art. 5.89 BW; art. VI.91/5, 6° WER); zwarte-lijstbeding (art. VI.91/4 WER); geen aansprakelijkheidsplafond; geen verwerkersovereenkomst bij verwerking van persoonsgegevens; IE-overdracht van kernactiva; buitensporig schadebeding zonder plafond. **Actie**: juridisch risico met grondslag, alternatieve tekst, inschatting van de blootstelling, escalatiepad.

## Redline-formaat

Nederlands:
```
**Clausule**: [nummer en titel]
**Classificatie**: [GROEN / GEEL / ROOD]
**Huidige tekst**: "[letterlijk citaat]"
**Voorgestelde tekst**: "[concrete tekst, klaar om in te voegen]"
**Toelichting**: [1–2 zinnen, met wettelijke grondslag uit toolresultaten]
**Prioriteit**: [Must-have / Nice-to-have / Optioneel]
**Terugvalpositie**: [alternatief bij weigering]
```

Français :
```
**Clause** : [numéro et intitulé]
**Classification** : [VERT / JAUNE / ROUGE]
**Texte actuel** : « [citation exacte] »
**Texte proposé** : « [texte concret, prêt à insérer] »
**Justification** : [1–2 phrases, avec base légale issue des outils]
**Priorité** : [Indispensable / Souhaitable / Optionnel]
**Position de repli** : [alternative en cas de refus]
```

## Redlineregels

- **Kwaliteit boven kwantiteit**: elke aangehaalde bepaling moet de stelling werkelijk dragen. Bij aanvullend recht: zeg dat partijen mogen afwijken; noem een beding niet "onwettig" als het alleen ongunstig is. Geen zekere grondslag: baseer de aanbeveling op zakelijk risico.
- Invoegklare, evenwichtige tekst, niet verder dan de markt; toelichting deelbaar met de wederpartij; prioriteer en houd rekening met de relatie.

## Onderhandelingsprioriteiten (priorités de négociation)

- **Rang 1 — Must-haves / Indispensables**: geen of grof ontoereikend plafond; bedingen die niet geschreven of nietig zijn (art. 5.89 BW, art. VI.91/4–VI.91/6 WER); ontbrekende AVG-waarborgen; IE-bepalingen die kernactiva bedreigen; strijd met regelgeving.
- **Rang 2 — Nice-to-haves / Souhaitables**: plafond binnen de bandbreedte, vrijwaringen, kalibratie van schadebedingen, beëindigingsflexibiliteit, hardship-regeling, audit.
- **Rang 3 — Optioneel / Optionnels** (concessies): rechtskeuze als het alternatief aanvaardbaar is, opzegtermijnen, definities, verzekeringen.

Begin met rang 1, ruil rang 3 in voor rang 2, geef rang 1 nooit op zonder escalatie.

## Uitvoer

1. Samenvatting: contracttype, zijde van de gebruiker, toepasselijk regime (oud/nieuw BW, WER B2B ja/nee), aannames, algemene beoordeling met aantal GROEN/GEEL/ROOD.
2. Tabel: clausule — onderwerp — classificatie — kernpunt.
3. Redlines per clausule (formaat hierboven), gesorteerd op prioriteit.
4. Onderhandelingsstrategie per rang.
5. Bronnen en beperkingen (wat niet geverifieerd is).

Maak een .docx aan als de omgeving bestanden kan aanmaken; geef anders de volledige tekst in het antwoord.
> Claude: gebruik de `docx`-skill; redlines eventueel als bijgehouden wijzigingen.

Lettertypen: gebruik lettertypen die é, è, ê, ë, ç, à, ï, ô, û ondersteunen.

## Controlelijst vóór oplevering

- [ ] Taal = taal van de gebruiker; redlines in de taal van het contract; citaten in de juiste taal (BW/C. civ., WER/CDE).
- [ ] Contractdatum bepaald; oud of nieuw BW en WER B2B correct toegepast.
- [ ] Elke artikelverwijzing gecontroleerd met `search_belgian_legislation` (of als niet geverifieerd gemarkeerd).
- [ ] Rechtspraak gelezen met `read_legal_document`; geen nummers uit het geheugen.
- [ ] Samengestelde clausules ontleed; holistische beoordeling gedaan.
- [ ] Kalibratie: geen valse alarmen, geen cosmetische opmerkingen tussen wezenlijke.
- [ ] Vermelding: ontwerp ter beoordeling door een jurist, geen juridisch advies.

## Samenhang

- Een omstreden clausule uitdiepen: `juridische-nota-note-juridique`.
- Losse NDA: `nda-triage`. Onderzoek naar één rechtsvraag: `iura`.
