---
name: nda-triage
description: "Snelle triage van inkomende NDA's (geheimhoudingsovereenkomsten) naar Belgisch recht: toetsing aan een checklist, aan de bescherming van bedrijfsgeheimen in het WER (boek XI) en aan het schadebeding in het nieuwe Burgerlijk Wetboek; classificatie als GROEN/GEEL/ROOD met behandelroute en redlinevoorstellen, in het Nederlands of het Frans. Gebruik wanneer sales of business development een NDA aanlevert, bij de vraag of een NDA zonder jurist kan worden getekend, of bij een vergelijking met de standaard-NDA van de organisatie. Déclencheurs FR : accord de confidentialité, NDA, clause de confidentialité, secrets d'affaires, Code de droit économique, clause pénale, clause indemnitaire, non-concurrence, non-sollicitation, triage, VERT/JAUNE/ROUGE."
---

# NDA-triage (triage d'accords de confidentialité) — Belgisch recht

Je beoordeelt snel inkomende geheimhoudingsovereenkomsten (accords de confidentialité), classificeert hun risiconiveau en geeft de behandelroute aan. De analyse gebeurt naar Belgisch recht.

Uitdrukkelijke instructies van de gebruiker gaan vóór de standaardinstellingen van deze skill. De triage is een ontwerp ter beoordeling door een gekwalificeerde jurist, geen juridisch advies (pas un avis juridique).

## Taal (langue)

- Antwoord in de taal waarin de gebruiker schrijft (Nederlands of Frans), tenzij anders gevraagd. Citeer de NDA in haar originele taal; stel redlines voor in de taal van de NDA.
- Zoek in het Frans of het Nederlands ("secrets d'affaires" / "bedrijfsgeheimen"); probeer de andere taal bij magere resultaten.
- Citeer in de taal van de uitvoer: "art. XI.332/4 WER" / "art. XI.332/4 CDE", "art. 5.88 BW" / "art. 5.88 C. civ.", "art. 871bis Ger.W." / "art. 871bis C. jud.".

## Verificatie — niets uit het geheugen

- Volg de verificatieregels en toolinstructies van de `iura`-skill.
- De artikelnummers hieronder zijn op Justel gecontroleerd (stand november 2026); controleer ze met `search_belgian_legislation` vóór je ze in een toelichting zet. Noem geen andere nummers dan die je in toolresultaten zag. Let op (getest 2026-11-15): `search_belgian_legislation` geeft Boek 5/6 BW en de B2B-regels van het WER terug als de invoerings- of wijzigingswet in de oorspronkelijke bewoording, zonder latere wijzigingen. Controleer de geconsolideerde tekst op ejustice.just.fgov.be (via `search_web`) voordat je een artikel citeert, beschrijf de regel in je zoekopdracht in plaats van alleen het artikelnummer, en zie de skill `iura`, deel "Dekking".
- Rechtspraak over NDA's of bedrijfsgeheimen alleen uit `search_belgian_case_law`, gelezen met `read_legal_document`. Gebruik `date_from` (bijv. 2015-01-01) om recente rechtspraak te krijgen; zonder filter domineren oude arresten met onbetrouwbare samenvattingen (zie de skill `iura`).

## Juridisch kader

**Contract.** Een NDA is een onbenoemd contract; het nieuwe Burgerlijk Wetboek, Boek 5 "Verbintenissen", geldt voor contracten gesloten vanaf 1 januari 2023 — voor oudere NDA's in beginsel het oud BW (overgangsrecht: zie de `iura`-skill). Een eenzijdige geheimhoudingsverplichting is geldig; er is geen "consideration" nodig.

**Bedrijfsgeheimen (secrets d'affaires)** — wet van 30 juli 2018 betreffende de bescherming van bedrijfsgeheimen (B.S. 14 augustus 2018), die richtlijn (EU) 2016/943 omzet:
- **Definitie** (art. I.17/1, 1° WER): informatie die (a) geheim is (niet algemeen bekend of gemakkelijk toegankelijk), (b) handelswaarde heeft omdat ze geheim is, en (c) door de rechtmatige houder aan redelijke maatregelen is onderworpen om ze geheim te houden. Een NDA is zo'n "redelijke maatregel" — en de wettelijke bescherming bestaat ook zonder NDA.
- **Titel 8/1 boek XI WER "Bedrijfsgeheimen"**: uitzonderingen en waarborgen, o.a. de mobiliteit van werknemers en het gebruik van hun ervaring en vaardigheden (art. XI.332/2); rechtmatige verkrijging, o.a. door onafhankelijke ontdekking of creatie en door observatie, onderzoek of demontage van een product dat openbaar beschikbaar is of rechtmatig in bezit is (art. XI.332/3); onrechtmatige verkrijging, gebruik of openbaarmaking, o.a. door schending van een **geheimhoudingsovereenkomst** of contractuele beperking (art. XI.332/4); afwijzing van vorderingen bij o.a. vrijheid van meningsuiting en onthulling van wangedrag in het algemeen belang (art. XI.332/5).
- **Titel 9/1 "Burgerrechtelijke aspecten"**: maatregelen (staking, verbod, terugroeping, vernietiging) en schadevergoeding (art. XI.336/1–XI.336/5).
- **Bevoegdheid en verjaring**: bijzondere bevoegdheidsregel (art. XI.342/1 WER — lees de actuele tekst, ook over bedingen die ervan afwijken); verjaring 5 jaar vanaf kennis van de gedraging en de identiteit van de inbreukmaker, uiterlijk 20 jaar (art. XI.342/2 WER).
- **Procedure**: vertrouwelijkheid van bedrijfsgeheimen tijdens een geding (art. 871bis Ger.W.).
- **Werknemers**: de werknemer moet zich tijdens en na de arbeidsovereenkomst onthouden van onrechtmatige verkrijging, gebruik of openbaarmaking van een bedrijfsgeheim (art. 17, 3° Arbeidsovereenkomstenwet van 3 juli 1978, zoals gewijzigd in 2018).

**Schadebeding / strafbeding (clause indemnitaire / clause pénale).** Art. 5.88 BW: forfaitaire schadevergoeding mag; de rechter kan een **kennelijk onredelijk** beding ambtshalve of op verzoek matigen, niet tot onder een redelijk bedrag. Tussen ondernemingen (contract gesloten, hernieuwd of gewijzigd na 1 december 2020) is een schadevergoeding die kennelijk hoger is dan de schade die redelijkerwijze kan worden geleden **vermoed onrechtmatig** (art. VI.91/5, 8° WER). Voor NDA's van vóór 2023: regime van het oud BW opzoeken.

**Concurrentie- en wervingsverboden (non-concurrence / non-sollicitation).** Horen niet in een NDA. Tussen ondernemingen worden ze getoetst aan het mededingingsrecht en aan de B2B-regels over onrechtmatige bedingen (algemene norm "kennelijk onevenwicht", art. VI.91/3 WER); voor werknemers geldt een eigen wettelijk regime in de Arbeidsovereenkomstenwet — zoek de actuele voorwaarden op met `search_belgian_legislation` en noem geen artikelnummers of drempels uit het geheugen. Een NDA die de mobiliteit van werknemers beperkt, botst bovendien met art. XI.332/2 WER.

**Toepasselijk recht en forum.** Rechtskeuze: Rome I (Verordening (EG) nr. 593/2008) art. 3; forumkeuze: Brussel Ibis (Verordening (EU) nr. 1215/2012) art. 25. Tussen Belgische ondernemingen is de ondernemingsrechtbank (tribunal de l'entreprise) bevoegd (art. 573 Ger.W.).

## Checklist

### 1. Structuur
- [ ] Type: wederzijds, eenzijdig (wij geven) of eenzijdig (wij ontvangen) — past het bij de relatie?
- [ ] Zelfstandige NDA, geen geheimhoudingsclausule in een groter commercieel contract (dan: `contractbeoordeling-revue-contrat`)
- [ ] Partijen juist: volledige naam, rechtsvorm, ondernemingsnummer (KBO/BCE), zetel, bevoegde ondertekenaars
- [ ] Datum van sluiting (oud of nieuw BW; WER B2B-regels)

### 2. Definitie van vertrouwelijke informatie
- [ ] Redelijk afgebakend (niet "alle informatie van welke aard ook, gemarkeerd of niet")
- [ ] Dekt wat als bedrijfsgeheim kwalificeert (art. I.17/1, 1° WER) zonder publieke informatie te omvatten
- [ ] Markering uitvoerbaar (bijv. schriftelijke bevestiging van mondelinge informatie binnen een redelijke termijn)

### 3. Verplichtingen van de ontvanger
- [ ] Zorgvuldigheidsnorm: redelijke zorg, minstens dezelfde als voor eigen informatie
- [ ] Doelbinding: alleen voor het omschreven doel
- [ ] Need-to-know, met vergelijkbare verplichtingen voor ontvangers
- [ ] Geen onuitvoerbare verplichtingen

### 4. Standaarduitzonderingen (exceptions usuelles)
- [ ] Publiek bekend buiten toedoen van de ontvanger
- [ ] Reeds in bezit vóór de openbaarmaking
- [ ] Onafhankelijk ontwikkeld (sluit aan bij art. XI.332/3 WER)
- [ ] Rechtmatig van een derde ontvangen zonder beperking
- [ ] Wettelijke of gerechtelijke verplichting tot openbaarmaking, met voorafgaande kennisgeving waar toegestaan
- [ ] Geen afbreuk aan klokkenluiden, vrijheid van meningsuiting en werknemersvertegenwoordiging (art. XI.332/5 WER)

### 5. Toegestane openbaarmakingen
- [ ] Werknemers en bestuurders met need-to-know
- [ ] Adviseurs met beroepsgeheim (advocaten, bedrijfsrevisoren, accountants)
- [ ] Verbonden vennootschappen onder vergelijkbare verplichtingen
- [ ] Toezichthouders en overheden waar wettelijk vereist

### 6. Duur
- [ ] Looptijd van de overeenkomst passend (1–3 jaar is gangbaar)
- [ ] Nawerking van de geheimhouding (2–5 jaar gangbaar; voor echte bedrijfsgeheimen zolang ze geheim blijven, verdedigbaar)
- [ ] Geen onbeperkte duur zonder rechtvaardiging; bij onbepaalde duur: opzegmogelijkheid met redelijke termijn (art. 5.75 BW)

### 7. Teruggave en vernietiging
- [ ] Bij einde of op verzoek
- [ ] Uitzondering voor wettelijke bewaarplicht en automatische back-ups (die vertrouwelijk blijven)
- [ ] Schriftelijke bevestiging redelijk; beëdigde verklaring buitensporig

### 8. Remedies
- [ ] Erkenning dat een vordering tot staking of maatregelen in kort geding (référé) gepast kan zijn — standaard
- [ ] Schadebeding: redelijk bedrag, met plafond; geen automatische cumulatie per dag zonder grens (art. 5.88 BW; art. VI.91/5, 8° WER)
- [ ] Wederkerig bij een wederzijdse NDA
- [ ] Wettelijke vorderingen op grond van boek XI WER niet uitgesloten

### 9. Problematische bepalingen
- [ ] Geen concurrentiebeding (clause de non-concurrence)
- [ ] Geen wervingsverbod (clause de non-sollicitation) — hoogstens beperkt tot personen met wie men in het project contact had, kort en wederkerig
- [ ] Geen exclusiviteit of standstill (tenzij M&A-context, dan apart beoordelen)
- [ ] Residuals-clausule: afwezig of eng (algemene kennis in het geheugen, met uitsluiting van bedrijfsgeheimen)
- [ ] Geen overdracht of licentie van IE
- [ ] Geen auditrecht, of beperkt met kennisgeving
- [ ] Verbod op reverse engineering: let op dat art. XI.332/3 WER observatie of demontage van een rechtmatig verkregen product als rechtmatige verkrijging behandelt — lees de precieze tekst en beoordeel of de contractuele beperking past bij de relatie

### 10. Toepasselijk recht en geschillen
- [ ] Belgisch recht bij Belgische partijen; anders een aanvaardbaar EU-recht
- [ ] Rechtskeuze en forum consistent; bevoegde rechter of arbitrage duidelijk
- [ ] Bevoegdheidsbeding verenigbaar met art. XI.342/1 WER (tekst nalezen)

## Classificatie (classification)

### GROEN / VERT — Standaardgoedkeuring / Approbation standard
**Alle** voorwaarden: juiste richting of wederzijds; alle standaarduitzonderingen; duur binnen bereik; geen concurrentie-, wervings- of exclusiviteitsbeding; geen of enge residuals-clausule; Belgisch of aanvaardbaar recht; geen of redelijk schadebeding; toegestane openbaarmakingen aanwezig; bewaaruitzondering bij teruggave; redelijke definitie; partijen juist.
**Route**: goedkeuren volgens de delegatieregeling; geen jurist nodig.

### GEEL / JAUNE — Beoordeling door jurist / Revue par un juriste
Eén of meer van: definitie ruimer dan gewenst maar niet onredelijk; duur langer dan standaard maar marktconform; één ontbrekende standaarduitzondering die makkelijk toe te voegen is; enge residuals-clausule; aanvaardbaar maar niet geprefereerd recht; lichte asymmetrie; redelijk schadebeding; uitvoerbare markering; geen uitdrukkelijke bewaaruitzondering.
**Route**: naar de aangewezen jurist met de gemarkeerde punten; doorgaans één redline-ronde.

### ROOD / ROUGE — Aanzienlijke problemen / Problèmes importants
Eén of meer van: eenzijdig in de verkeerde richting; ontbrekende kernuitzonderingen (onafhankelijke ontwikkeling, wettelijke verplichting); concurrentie- of wervingsverbod; exclusiviteit of standstill zonder context; onredelijke duur (10+ jaar of onbeperkt zonder rechtvaardiging); definitie die publieke informatie omvat; brede residuals-clausule (feitelijke licentie); verborgen IE-overdracht of licentie; buitensporig schadebeding zonder plafond; zeer ongunstig forum met verplichte arbitrage; bepalingen die wettelijke waarborgen (art. XI.332/2 of XI.332/5 WER) uitsluiten; document dat feitelijk geen NDA is (commerciële voorwaarden, exclusiviteit).
**Route**: volledige juridische beoordeling; niet tekenen; tegenvoorstel of standaard-NDA van de organisatie.

## Behandelroute (routage)

| Classificatie | Actie (NL) | Action (FR) | Doorlooptijd |
|---|---|---|---|
| GROEN / VERT | Goedkeuren en ter ondertekening volgens volmacht | Approuver et faire signer selon les délégations | Zelfde dag |
| GEEL / JAUNE | Naar aangewezen jurist met gemarkeerde punten | Transmettre au juriste désigné avec les points signalés | 1–2 werkdagen |
| ROOD / ROUGE | Volledige beoordeling; tegenvoorstel of eigen standaard-NDA | Revue complète ; contre-proposition ou NDA standard | 3–5 werkdagen |

## Uitvoerformaat

Nederlands:
```
NDA-TRIAGE
Document:        [naam/versie]   Wederpartij: [naam]
Type:            [wederzijds / eenzijdig — richting]
Datum / regime:  [datum; nieuw BW / oud BW; WER B2B ja/nee]
Classificatie:   [GROEN / GEEL / ROOD]
Route:           [actie + doorlooptijd]

Bevindingen (per checklistonderdeel): [OK / punt + korte toelichting]
Redlines (GEEL/ROOD): Clausule — Huidige tekst — Voorgestelde tekst — Toelichting — Prioriteit
Niet geverifieerd / aannames: [...]
```

Français :
```
TRIAGE NDA
Document :          [nom/version]   Cocontractant : [nom]
Type :              [mutuel / unilatéral — sens]
Date / régime :     [date ; nouveau / ancien Code civil ; CDE B2B oui/non]
Classification :    [VERT / JAUNE / ROUGE]
Routage :           [action + délai]

Constats (par point de la checklist) : [OK / point + brève explication]
Redlines (JAUNE/ROUGE) : Clause — Texte actuel — Texte proposé — Justification — Priorité
Non vérifié / hypothèses : [...]
```

Maak een .docx aan als de omgeving bestanden kan aanmaken; geef anders de volledige tekst in het antwoord.
> Claude: gebruik de `docx`-skill als de gebruiker een bestand wil.

Lettertypen: gebruik lettertypen die é, è, ê, ë, ç, à, ï, ô, û ondersteunen.

## Kalibratie

Een degelijke NDA is GROEN met een korte bevestiging; verzin geen bezwaren. Classificeer naar het zwaarste punt, maar meng geen cosmetische opmerkingen met wezenlijke.

## Controlelijst vóór oplevering

- [ ] Taal = taal van de gebruiker; redlines in de taal van de NDA; citaten in de juiste taal.
- [ ] Datum en regime bepaald (oud/nieuw BW; WER B2B).
- [ ] Artikelnummers gecontroleerd met `search_belgian_legislation` of als niet geverifieerd gemarkeerd.
- [ ] Alle tien checklistonderdelen behandeld; classificatie volgt uit de bevindingen.
- [ ] Vermelding: ontwerp ter beoordeling door een jurist, geen juridisch advies.

## Samenhang

- Geheimhouding binnen een groter contract: `contractbeoordeling-revue-contrat`.
- Diepere vraag (bijv. afdwingbaarheid van een wervingsverbod of matiging van een schadebeding): `juridische-nota-note-juridique`, onderzoek met `iura`.
