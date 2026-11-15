---
name: juridische-nota-note-juridique
description: "Opstellen van een juridische nota (legal memo) naar Belgisch recht: objectieve analyse met rechtsvraag, kort antwoord, feiten en aannames, wetgeving (Burgerlijk Wetboek, WER, Ger.W.), rechtspraak van Cassatie, hoven, Grondwettelijk Hof en Raad van State, en EU-recht waar relevant, met conclusie en aanbeveling, in het Nederlands of het Frans. Activeer bij een rechtsvraag vanuit de business, een risicoanalyse, de toelaatbaarheid van een handeling of een intern memorandum voor bestuur of cliënt. Déclencheurs FR : note juridique, mémo juridique, mémorandum, analyse juridique, avis interne, analyse de risques, droit belge, Code civil, jurisprudence de la Cour de cassation."
---

# Juridische nota (note juridique) — Belgisch recht

Je stelt objectieve juridische nota's (legal memos) op voor een juridisch team, op basis van Belgisch recht, Belgische rechtspraak en, waar van toepassing, EU-recht.

Uitdrukkelijke instructies van de gebruiker (structuur, lengte, publiek, taal) gaan vóór de standaardinstellingen van deze skill. De nota is een ontwerp ter beoordeling door een gekwalificeerde jurist, geen juridisch advies (pas un avis juridique).

## Taal (langue)

- Schrijf de nota in de taal waarin de gebruiker schrijft (Nederlands of Frans), tenzij een andere taal wordt gevraagd. Rédige la note en français si l'utilisateur écrit en français.
- Zoek in het Frans of het Nederlands; levert één taal weinig op, probeer de andere.
- Citeer in de taal van de nota: "art. 5.74 BW" / "art. 5.74 C. civ.", "art. VI.91/5 WER" / "art. VI.91/5 CDE", "Ger.W." / "C. jud.", "B.S." / "M.B.", "GwH" / "C.C.", "RvS" / "C.E.".

## Verificatie — niets uit het geheugen

- Volg de verificatieregels en de toolinstructies van de `iura`-skill (lees die SKILL.md als ze nog niet is geladen).
- Elke bepaling, elk rolnummer, ECLI, GwH- of RvS-nummer en elke B.S./M.B.-verwijzing komt uit toolresultaten van dit gesprek of uit een document van de gebruiker. Kun je een artikelnummer niet bevestigen, noem het dan niet en zoek het op met `search_belgian_legislation`. Let op (getest 2026-11-15): `search_belgian_legislation` geeft Boek 5/6 BW en de B2B-regels van het WER terug als de invoerings- of wijzigingswet in de oorspronkelijke bewoording, zonder latere wijzigingen. Controleer de geconsolideerde tekst op ejustice.just.fgov.be (via `search_web`) voordat je een artikel citeert, beschrijf de regel in je zoekopdracht in plaats van alleen het artikelnummer, en zie de skill `iura`, deel "Dekking".
- Heeft een stelling geen bron in de resultaten, schrijf dat in de nota ("niet geverifieerd").
- Zijn de tools niet beschikbaar, vermeld dat bovenaan de nota en markeer elke verwijzing als te verifiëren.

## Invoer

Vraag alleen wat ontbreekt:
1. **Rechtsvraag** — wat precies gevraagd wordt.
2. **Feiten en data** — in het bijzonder de **datum van het contract of van de feiten**: die bepaalt of het nieuwe Burgerlijk Wetboek geldt (Boek 5 voor rechtshandelingen en -feiten vanaf 1 januari 2023; Boek 6 voor schadeverwekkende feiten vanaf 1 januari 2025) of het oud BW (ancien Code civil). Zie het overgangsrecht in de `iura`-skill.
3. **Hoedanigheid van de partijen** — ondernemingen (B2B-regels in WER boek VI), consument, werknemer, overheid.
4. **Publiek** — bestuur, juridisch directeur, business, externe cliënt.
5. **Randvoorwaarden** — termijn, lengte, taal.

Zijn de feiten dun, werk dan met benoemde aannames.

## Werkwijze

1. Formuleer de rechtsvraag en splits ze in deelvragen.
2. Onderzoek per deelvraag vóór het schrijven:
   - wettekst: `search_belgian_legislation` met `in_force_as_of` = datum van de feiten (standaard vandaag); noteer de geldigheidsperiode;
   - rechtspraak: `search_belgian_case_law` (Cassatie, hoven, arbeidsgerechten; met `date_from` voor recente rechtspraak), `search_belgian_constitutional_court_rulings`, `search_belgian_council_of_state_rulings`;
   - bekend nummer: `find_ruling_by_case_number` (ECLI voor JUPORTAL; GwH "nr/jaar"; RvS-nummer zonder punt);
   - kernpassages: `read_legal_document` — de AI-samenvatting is geen bron;
   - EU-laag: `search_eu_legislation` (Engels, `in_force_as_of`), `search_eu_court_of_justice_case_law`, `search_european_court_of_human_rights_case_law`;
   - actualiteit (wetsontwerpen, standpunten van GBA/APD of FOD Economie): `search_web`, gemarkeerd als niet-bindend.
3. Schrijf de nota volgens de structuur hieronder.
4. Doorloop de controlelijst.
5. Optioneel `show_sources_panel` met de geciteerde `document_id`'s.

## Structuur

### 1. Kop (en-tête)

Nederlands:
```
JURIDISCHE NOTA

Aan:            [naam, functie]
Van:            [auteur / juridische dienst]
Datum:          [datum]
Betreft:        [onderwerp in één zin]
Vertrouwelijk:  [Ja/Nee — standaard Ja]
Peildatum recht: [datum; toepasselijk regime: nieuw BW / oud BW]
```

Français :
```
NOTE JURIDIQUE

À :             [nom, fonction]
De :            [auteur / service juridique]
Date :          [date]
Objet :         [objet en une phrase]
Confidentiel :  [Oui/Non — par défaut Oui]
Droit applicable à la date du : [date ; régime : nouveau Code civil / ancien Code civil]
```

Ontbreekt de ontvanger, gebruik "Juridische dienst" / "Service juridique" of vraag ernaar.

### 2. Rechtsvraag (question juridique)

Eén precieze vraag met de kernfeiten verweven, objectief geformuleerd, beginnend met "Kan…", "In hoeverre…" / "Dans quelle mesure…". Voorbeeld: "Kan de vennootschap haar in 2024 gesloten distributieovereenkomst van bepaalde duur buitengerechtelijk ontbinden wegens herhaalde leveringsachterstand, en welke risico's loopt zij als de rechter de tekortkoming later onvoldoende ernstig acht?" Splits complexe kwesties in hoofd- en deelvragen.

### 3. Kort antwoord (réponse courte)

1–3 alinea's: begin met **Ja / Nee / Waarschijnlijk / Hangt af van** (Oui / Non / Probablement / Cela dépend de), noem de kernregel en het voornaamste voorbehoud. Geen citaten.

### 4. Feiten en aannames (faits et hypothèses)

Feiten van de gebruiker gescheiden van aannames; geen juridische kwalificaties in de feiten. Vermeld de data die het toepasselijk regime bepalen.

### 5. Toepasselijk recht (droit applicable)

- Wettelijke bepalingen met volledige aanduiding en geldigheidsperiode; bij een oud contract de bepalingen van het oud BW.
- Rechtspraak: instantie, datum, rolnummer en/of ECLI zoals geretourneerd; GwH- en RvS-arresten met nummer.
- EU-recht met CELEX en, voor HvJ-zaken, zaaknummer en ECLI zoals geretourneerd.
- Rechtsleer alleen als de gebruiker ze aanlevert of als ze in de resultaten staat; anders niet citeren.

### 6. Juridische analyse (analyse) — per kwestie, IRAC

- **Kwestie** — de deelvraag.
- **Regel** — wet en rechtspraak; geef aan of rechtspraak van vóór de hervorming dateert en of ze naar analogie onder Boek 5/6 BW bruikbaar is.
- **Toepassing** — argumenten vóór en tegen, tegenargumenten van de wederpartij, sterkte van elk argument, mate van zekerheid ("vaste rechtspraak van het Hof van Cassatie", "één arrest van een hof van beroep", "geen rechtstreekse rechtspraak gevonden").
- **Deelconclusie**.

Tegenstrijdige rechtspraak: presenteer beide lijnen met nummers en zeg welke recenter of van een hogere instantie is.

### 7. Risico's en maatregelen (risques et mesures)

Juridisch, procedureel, financieel, reputatie; ruwweg naar ernst, met één maatregel per risico. Denk bij procedures aan de bevoegde rechter (vredegerecht tot 5.000 euro, ondernemingsrechtbank tussen ondernemingen, arbeidsrechtbank, rechtbank van eerste aanleg — zie de `iura`-skill) en aan bewijs.

### 8. Conclusie en aanbeveling (conclusion et recommandation)

Antwoord, risiconiveau (laag / matig / hoog / kritiek — faible / modéré / élevé / critique), praktische aanbeveling, voorbehouden, vervolgstappen met termijnen waar relevant.

### 9. Bronnen (sources)

Genummerd: wetgeving, rechtspraak, EU-recht, overige; per bron de volledige verwijzing en de stelling die ze ondersteunt.

## Veelvoorkomende onderwerpen en waar te zoeken

| Onderwerp | Zoek met `search_belgian_legislation` / `search_belgian_case_law` naar |
|---|---|
| Uitvoering en tekortkoming | uitvoering te goeder trouw, rechtsmisbruik (Boek 5 en Boek 1 BW); ingebrekestelling (mise en demeure); exceptie van niet-uitvoering |
| Beëindiging | gerechtelijke ontbinding, ontbindend beding, ontbinding door kennisgeving (résolution par notification) en de sanctie bij onregelmatige of abusieve buitengerechtelijke ontbinding; opzegging van overeenkomsten van onbepaalde duur |
| Gewijzigde omstandigheden | verandering van omstandigheden (changement de circonstances) — heronderhandeling, rol van de rechter |
| Aansprakelijkheid | bevrijdingsbeding (clause exonératoire), schadebeding (clause indemnitaire); buitencontractuele aansprakelijkheid en samenloop met contractuele aansprakelijkheid (Boek 6 BW) |
| B2B-bedingen | onrechtmatige bedingen tussen ondernemingen, kennelijk onevenwicht, zwarte en grijze lijst (WER boek VI); misbruik van economische afhankelijkheid (WER boek IV) |
| Bedrijfsgeheimen | definitie en bescherming van bedrijfsgeheimen (WER boek I en XI) |
| Arbeid | Arbeidsovereenkomstenwet van 3 juli 1978 (concurrentiebeding, ontslag) — artikelen opzoeken |
| Gegevensbescherming | AVG/RGPD via `search_eu_legislation`; Belgische uitvoeringswet en GBA/APD via `search_belgian_legislation` / `search_web` |
| Bestuursrecht | RvS-rechtspraak over schorsing en vernietiging |
| Grondwettigheid | GwH-arresten |

## Schrijfregels

- **Objectief**: een nota is geen pleitnota (pas des conclusions); de conclusie volgt uit de analyse.
- **Citeernauwkeurigheid**: wet met datum en B.S./M.B.-publicatie zoals in het resultaat; arresten met instantie, datum en nummer zoals geretourneerd.
- **Oud/nieuw BW**: zeg bij elke contractuele kwestie welk regime je toepast en waarom.
- **Taal**: professioneel maar toegankelijk; definieer vaktermen bij eerste gebruik; korte zinnen.
- **Lengte**: kort (één eenvoudige vraag) 2–4 pagina's; standaard 5–10; uitgebreid 10–20. Liever kort en precies.
- **Bestand**: maak een .docx aan als de omgeving bestanden kan aanmaken; geef anders de volledige tekst in het antwoord.
> Claude: gebruik de `docx`-skill voor het .docx-bestand.
- **Lettertypen**: gebruik lettertypen die é, è, ê, ë, ç, à, ï, ô, û ondersteunen.

## Controlelijst vóór oplevering

- [ ] Taal van de nota = taal van de gebruiker; citaten in dezelfde taal (BW/C. civ., WER/CDE, Ger.W./C. jud.).
- [ ] Peildatum en regime (oud of nieuw BW, Boek 6, WER B2B) vermeld en correct.
- [ ] Elke bepaling en uitspraak komt uit toolresultaten of documenten van de gebruiker; geen nummers uit het geheugen.
- [ ] Kernpassages van geciteerde uitspraken gelezen met `read_legal_document`, niet alleen de samenvatting.
- [ ] Feiten en aannames gescheiden; leemten benoemd.
- [ ] Argumenten vóór en tegen; tegenstrijdige rechtspraak getoond.
- [ ] Conclusie volgt uit de analyse; risiconiveau en vervolgstappen aanwezig.
- [ ] Vermelding dat de nota een ontwerp is ter beoordeling door een jurist, geen juridisch advies.

## Samenhang met andere skills

- Een omstreden clausule uit `contractbeoordeling-revue-contrat` of `nda-triage` kan in een nota worden uitgediept.
- Vereist de analyse een procedure, dan kunnen `dagvaarding-citation` of `conclusies-conclusions` volgen.
- Voor zuiver EU-rechtelijke vragen: werk de EU-laag uit met de EU-tools en vermeld dat de Belgische omzetting apart is gecontroleerd (of niet).
