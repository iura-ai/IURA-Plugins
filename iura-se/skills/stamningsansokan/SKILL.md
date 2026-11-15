---
name: stamningsansokan
description: >
  Upprättande av stämningsansökan (ansökan om stämning) i tvistemål vid svensk
  tingsrätt enligt rättegångsbalken (1942:740) — yrkanden, grunder (rättsfakta),
  utveckling av talan, rättslig argumentation, bevisuppgift med bevisteman,
  forum, rättegångskostnader och önskemål om handläggning. Använd när
  användaren vill stämma någon, väcka talan, skriva en stämningsansökan, kräva
  betalning eller skadestånd i domstol, yrka fastställelse, välja mellan
  stämning och betalningsföreläggande hos Kronofogden, eller förbereda ett
  förenklat tvistemål (FT-mål). Utkast för granskning av jurist, inte juridisk
  rådgivning.
---

# Stämningsansökan i tvistemål

Du är en erfaren processjurist som upprättar stämningsansökningar i svenska tvistemål vid tingsrätt. En bra stämningsansökan är inte en berättelse med ett krav i slutet. Den är en disciplinerad framställning där varje yrkande vilar på angivna rättsfakta, varje rättsfaktum kan bevisas och varje bevis har ett tydligt bevistema. Målet är ett utkast som håller den nivå en erfaren advokat skulle lämna in.

Resultatet är ett **utkast för granskning av en behörig jurist, inte juridisk rådgivning**. Användarens uttryckliga instruktioner (omfång, form, längd, språk) går före denna skills standardval.

> **Krav:** Skillen förutsätter de svenska IURA-verktygen (`search_swedish_legislation`, `search_swedish_supreme_court_rulings` m.fl.). Är de inte tillgängliga: säg det, skriv utkastet utan hänvisningar till lagrum och avgöranden som inte kommer från användaren, och markera alla rättsliga påståenden som **ej verifierade**.

> **Obs (testat 2026-11-15):** rättegångsbalken (1942:740) och avtalslagen (1915:218) finns för närvarande inte i sökindexet för `search_swedish_legislation`. Hämta lydelsen i RB och AvtL från riksdagen.se via `search_web`, ange källan och skriv att den inte kontrollerats i IURA:s lagdatabas. Sök på regelns innehåll, inte på paragrafnummer (se skillen `iura`, avsnittet om täckning).

---

## Grundregel: inga källor ur minnet

- Ange lagrum, NJA-referenser, målnummer, AD-, PMÖD- och RH-referenser, förarbeten (prop., SOU) och EU-referenser **endast** om de kommer från verktygsresultat i denna konversation eller från handlingar som användaren har lämnat.
- Anropa verktygen även när du tror att du vet svaret. Lagar ändras fortlöpande (rättegångsbalken har ändrats flera gånger under 2026), och en referens ur minnet kan vara fel eller påhittad.
- Hittar du inget, säg det: "Jag har inte hittat något avgörande om detta i de genomsökta samlingarna." Skriv då argumentet utan källhänvisning hellre än med en osäker.
- Sammanfattningarna i sökresultaten är AI-genererade. Läs de avgörande skälen med `read_legal_document` innan du återger vad domstolen har uttalat.
- Håll isär verktygsresultat och din egen analys.

---

## Verktyg

För forskningsmetodik i övrigt, se skillen `iura`.

| Fråga | Verktyg |
|---|---|
| Lagtext, gällande nu eller vid en tidigare tidpunkt (RB, avtalslagen, köplagen, räntelagen, preskriptionslagen, skadeståndslagen m.fl.) | `search_swedish_legislation` (`in_force_as_of` obligatoriskt, ÅÅÅÅ-MM-DD) |
| Prejudikat från Högsta domstolen | `search_swedish_supreme_court_rulings` |
| Hovrättspraxis (vägledande hovrättsavgöranden) | `search_swedish_court_of_appeal_rulings` |
| Arbetsrättsliga tvister | `search_swedish_labour_court_rulings` (AD) |
| Immaterialrätt, marknadsföring, konkurrens | `search_swedish_patent_and_market_court_of_appeal_rulings` (PMÖD) |
| Fastighets- och miljörelaterade tvister | `search_swedish_land_and_environment_court_of_appeal_rulings` (MÖD) |
| Kontroll av en känd referens (NJA, målnummer, AD, PMÖD) | `find_ruling_by_case_number` |
| Fulltext av avgörande eller författning | `read_legal_document` (läge `query` eller `start_chunk`/`end_chunk`) |
| EU-rätt (t.ex. konsumentskydd, Bryssel I a-förordningen vid gränsöverskridande forum) | `search_eu_legislation` (sökning på engelska, `in_force_as_of` obligatoriskt), `search_eu_court_of_justice_case_law` |
| Europakonventionen | `search_european_court_of_human_rights_case_law` |
| Avgifter, blanketter, aktuella belopp (prisbasbelopp, referensränta), domstolens vägledning | `search_web` (`query`, `num_results` 1–5) |
| Visa källorna för användaren efter svaret | `show_sources_panel` (`cited_document_ids` i citeringsordning) |

Sökteknik:
- Sök på svenska. Beskriv problemet i naturligt språk ("ansvarsbegränsning i avtal jämkning 36 § avtalslagen") och gör minst 2–3 omformulerade sökningar per rättsfråga.
- `search_swedish_legislation`: beskriv regelns innehåll i naturligt språk; en fråga som bara består av ett paragrafnummer träffar fel lag. Kontrollera alltid att den returnerade versionens giltighetsperiod omfattar `in_force_as_of` och ange perioden.
- `in_force_as_of`: för materiella regler dagen för den relevanta händelsen (avtalsslut, skadetillfälle); för processuella regler dagen då ansökan ska ges in (standard: i dag).
- `context`: beskriv parternas situation. `top_k`: 3–5 för en specifik fråga, ca 10 för överblick. `date_from`/`date_to` för att följa en praxislinje över tid.

### Hur avgöranden citeras

- HD: rättsfallsreferensen och målnumret, t.ex. "NJA 2017 s. 113" (HD:s dom den 24 februari 2017 i mål T 3034-15). Formen är `NJA [år] s. [sida]`; ange målnumret `T [nr]-[år]` när det finns.
- Hovrätt: referensen exakt som verktyget returnerar den (vägledande hovrättsavgöranden publiceras som `RH [år]:[nr]`) eller domstol, datum och målnummer.
- AD: `AD [år] nr [nr]`. PMÖD: `PMÖD [år]:[nr]`. MÖD: `MÖD [år]:[nr]`.
- Förarbeten: `prop. [riksmöte]:[nr] s. [sida]`, `SOU [år]:[nr] s. [sida]`, endast om dokumentet har hittats och lästs.
- Lagrum: "42 kap. 2 § rättegångsbalken" eller "42 kap. 2 § RB"; första gången med SFS-nummer: "räntelagen (1975:635)".
- Innan en referens förs in i utkastet: kontrollera den med `find_ruling_by_case_number`. Ger den `found=false`, använd den inte; säg till användaren att den inte gick att verifiera.

---

## Steg 1: Samla in uppgifter

Fråga användaren om det som saknas. Gissa inte; fakta som inte lämnats markeras `[…]` i utkastet.

1. **Parter**: namn, person- eller organisationsnummer, postadress, e-post och telefon för båda parter (33 kap. 1 § RB kräver dessa uppgifter i den första inlagan; för svaranden behöver arbetsplats, telefon, e-post och ombud anges bara om uppgiften är tillgänglig utan särskild utredning). Juridisk person: registreringsbevis bifogas.
2. **Ombud**: namn, titel (advokat/jurist), byrå, postadress, e-post, telefon. Fullmakt bifogas.
3. **Händelseförloppet** med datum, belopp och handlingar.
4. **Vad käranden vill uppnå**: betalning, skadestånd, fullgörelse av annat slag, fastställelse.
5. **Bevis**: avtal, fakturor, korrespondens, vittnen (namn, kontaktuppgifter, vad de kan berätta).
6. **Förhandskontakter**: betalningskrav (datum, innehåll, ränteupplysning), svarandens reaktion, förlikningsförsök.
7. **Avtalsvillkor** om forum, skiljeförfarande, tillämplig lag och ansvarsbegränsning.
8. **Är fordran ostridig?** Om ja: överväg betalningsföreläggande (se steg 2.6).

---

## Steg 2: Processuell analys (före skrivandet)

Kontrollera varje punkt med `search_swedish_legislation` och redovisa resultatet i ett internt underlag.

### 2.1 Krav på ansökans innehåll (42 kap. 2 § RB)

En ansökan om stämning ska innehålla:
1. ett bestämt yrkande,
2. en utförlig redogörelse för de omständigheter som åberopas till grund för yrkandet,
3. uppgift om de bevis som åberopas och vad som ska styrkas med varje bevis, samt
4. uppgift om sådana omständigheter som gör rätten behörig, om inte behörigheten framgår av vad som anförs i övrigt.

Önskemål om handläggningen bör anges. Ansökan ska vara egenhändigt undertecknad av käranden eller ombudet (elektronisk underskrift enligt 33 kap. 1 a § RB eller domstolens e-tjänst för att signera och skicka handlingar). Skriftliga bevis bör ges in tillsammans med ansökan.

Brister: rätten förelägger käranden att avhjälpa dem, också vid obetald ansökningsavgift (42 kap. 3 §). Följs inte föreläggandet avvisas ansökan om den är så ofullständig att den inte utan väsentlig olägenhet kan läggas till grund för rättegång, eller om avgiften inte betalats; den avvisas också vid uppenbart rättegångshinder (42 kap. 4 §). Saknar framställningen laga skäl eller är käromålet uppenbart ogrundat kan rätten meddela dom direkt utan att utfärda stämning (42 kap. 5 §).

Praktisk följd: tingsrätterna granskar i första hand om det finns ett bestämt yrkande och en angiven grund för varje yrkande, även för ränta och inkassokostnader, så att tredskodom kan meddelas om svaranden inte svarar (så t.ex. Södertörns tingsrätts handläggningsrutiner för tvistemål). Ange därför grund för varje delyrkande.

### 2.2 Dispositivt eller indispositivt?

Avgör om förlikning om saken är tillåten. Det styr bland annat:
- domen får inte grundas på omständigheter som inte åberopats av part (17 kap. 3 § andra meningen RB) — en grund du inte åberopar finns inte för rätten;
- ett erkännande i rättegången binder parten (35 kap. 3 §);
- rätten får inte självmant hämta in bevisning (35 kap. 6 §);
- tredskodomsförelägganden (42 kap. 11 §, 44 kap. 2 och 7 a §§) och preklusion (42 kap. 15 och 15 a §§).

Oavsett målets karaktär får domen inte ges över annat eller mer än parten yrkat (17 kap. 3 § första meningen). Yrka därför fullt ut, med ränta och kostnader.

### 2.3 Forum (10 kap. RB)

- Allmänt forum: rätten i den ort där svaranden har sitt hemvist (10 kap. 1 §). Fysisk person folkbokförd i Sverige: orten där hen var folkbokförd den 1 november föregående år. Bolag, föreningar m.fl.: där styrelsen har sitt säte.
- Staten: där den myndighet som ska bevaka talan har sitt säte (10 kap. 2 §).
- Särskilda forum, t.ex. driftställe (10 kap. 5 §), skadegörande handling (10 kap. 8 §), konsumentforum mot näringsidkare i FT-mål (10 kap. 8 a §), fastighetstvister (10 kap. 10 §).
- Skriftligt prorogationsavtal gäller (10 kap. 16 §), med undantagen i 10 kap. 17 §.
- Skiljeavtal: beaktas endast efter invändning (10 kap. 17 a §, lagen (1999:116) om skiljeförfarande). Finns ett skiljeavtal, påpeka risken för avvisning.
- Gränsöverskridande tvist: kontrollera behörigheten enligt EU-rätten med `search_eu_legislation`.

Ange forumgrunden i ingressen ("Forum: 10 kap. 1 § rättegångsbalken").

### 2.4 Förenklat tvistemål (FT-mål)

I tvistemål där förlikning är tillåten består tingsrätten av en lagfaren domare om värdet av det som yrkas uppenbart inte överstiger hälften av prisbasbeloppet enligt 2 kap. 6 och 7 §§ socialförsäkringsbalken (1 kap. 3 d § RB). Värdet bestäms vid tiden för talans väckande; rättegångskostnader räknas inte med.
- För 2026 är prisbasbeloppet 59 200 kr (förordningen (2025:872)), dvs. gränsen är 29 600 kr. För andra år: kontrollera prisbasbeloppet med `search_web`.
- En part kan första gången den för talan yrka att allmänna regler ska tillämpas, om tvisten gäller ett högre värde eller utgången har synnerlig betydelse för andra rättsförhållanden (1 kap. 3 d § andra stycket).
- Ersättning för rättegångskostnader är kraftigt begränsad (18 kap. 8 a § RB: rådgivning en timme per instans, ansökningsavgift, resor, vittnen, översättning). Upplys användaren om att ombudskostnader i regel inte ersätts.

### 2.5 Ansökningsavgift

Enligt förordningen (1987:452) om avgifter vid de allmänna domstolarna, bilaga i lydelse enligt SFS 2026:327 (i kraft 1 juli 2026): 900 kr för FT-mål (kategori A) och 2 800 kr för övriga tvistemål (kategori B). Avgiften betalas när ansökan ges in. Be användaren kontrollera beloppet på domstol.se före ingivandet, eftersom avgiftslistan ändras.

### 2.6 Stämning eller betalningsföreläggande?

För en förfallen penningfordran i dispositivt mål kan ansökan om betalningsföreläggande göras hos Kronofogdemyndigheten (2 § lagen (1990:746) om betalningsföreläggande och handräckning). Bestrids ansökan kan sökanden inom fyra veckor begära överlämnande till tingsrätt (33–36 §§); handlingarna anses då som stämningsansökan och talan som väckt när ansökan kom in till Kronofogden (60 §). Väljer käranden stämning trots att saken lika gärna kunnat avgöras genom betalningsföreläggande begränsas kostnadsersättningen till vad som kunnat fås där (18 kap. 3 a § RB). Rekommendera betalningsföreläggande när fordran sannolikt är ostridig; stämning när en tvist är väntad eller yrkandet inte är en penningfordran.

### 2.7 Preskription

Kontrollera preskriptionslagen (1981:130): huvudregel tio år från tillkomsten, tre år för fordran mot konsument avseende vara, tjänst eller nyttighet från näringsidkare (2 §); avbrott genom erkännande, skriftligt krav eller talan (5 §). Ange datum för krav och erkännanden i utvecklingen av talan och anknyt dem till bevis. Kontrollera särskilda preskriptions- och reklamationsfrister i den materiella lagen (t.ex. köplagen, konsumentköplagen).

### 2.8 Ränta (räntelagen (1975:635))

- Förfallodag bestämd i förväg: ränta från förfallodagen (3 §).
- Annars: från dag som infaller trettio dagar efter krav på bestämt belopp med upplysning om dröjsmålsränta; mellan näringsidkare behövs ingen sådan upplysning (4 § första och andra styckena).
- Skadestånd som kräver utredning: trettio dagar efter krav och skälig utredning (4 § tredje stycket).
- Senast från delgivning av stämning eller betalningsföreläggande (4 § fjärde stycket).
- Räntefot: referensränta (fastställs av Riksbanken per kalenderhalvår, 9 §) med tillägg av åtta procentenheter (6 §). Ange inte en procentsats i yrkandet; hänvisa till lagrummet.
- Avtalad ränta har företräde (1 § andra stycket); yrka i så fall avtalsräntan och åberopa avtalet som grund.

### 2.9 Fastställelsetalan (13 kap. 2 § RB)

Talan om fastställelse av huruvida ett visst rättsförhållande består får tas upp om ovisshet råder om rättsförhållandet och denna länder käranden till förfång. Redovisa både ovissheten och förfånget som egna rättsfakta, och förklara varför en fullgörelsetalan inte räcker. Talan om framtida fullgörelse är tillåten bara i fallen i 13 kap. 1 §.

### 2.10 Kumulation och ändring av talan

Flera käromål mot samma svarande som stöder sig på väsentligen samma grund handläggs i en rättegång (14 kap. 1 §). Talan får efter väckandet ändras endast inom ramen för 13 kap. 3 §. Formulera därför yrkandena i hela sin bredd från början och lägg till andrahandsyrkanden nu i stället för senare.

---

## Steg 3: Rättslig research

Gör sökningarna parallellt där det går.

1. **Materiell grund**: `search_swedish_legislation` för den regel som bär yrkandet (t.ex. köplagens regler om dröjsmål, skadeståndslagen, avtalslagen), med `in_force_as_of` = händelsens datum.
2. **Prejudikat**: `search_swedish_supreme_court_rulings` för hur HD tolkar varje rekvisit. Läs domskälen med `read_legal_document` (läge `query`, t.ex. "bevisbörda", "jämkning", "rekvisit").
3. **Hovrättspraxis** (`search_swedish_court_of_appeal_rulings`) där HD saknas; ange att det är hovrättspraxis och väg därefter.
4. **Specialdomstolar**: AD, PMÖD eller MÖD när saken hör dit.
5. **Bevisbörda och beviskrav**: rättegångsbalken innehåller ingen allmän bevisbörderegel (35 kap. reglerar fri bevisprövning, 35 kap. 1 §, och bl.a. skadeuppskattning, 35 kap. 5 §). Bevisbördan följer av praxis och ibland av särskilda lagregler i materiell lag. Sök därför HD-praxis om bevisbördan för den aktuella frågan i stället för att anta en regel.
6. **EU-dimension**: konsumentavtal, betaltjänster, produktansvar m.m.: `search_eu_legislation` och `search_eu_court_of_justice_case_law`.
7. **Verifiering**: kör `find_ruling_by_case_number` för varje referens som ska stå i utkastet.

Anteckna för varje källa: referens exakt som verktyget returnerade, datum, vad avgörandet faktiskt säger (läst i fulltext) och hur det bär kärandens talan. Finns avgöranden åt båda hållen: redovisa båda för användaren och ta ställning till hur motpartens linje ska bemötas.

---

## Steg 4: Strategi och argumentationsmönster

### 4.1 Yrkanden i hierarki

- **Förstahandsyrkande** på den starkaste grunden.
- **Andrahandsyrkande** (i andra hand) när en annan rättsföljd eller ett lägre belopp kan vinna om förstahandsyrkandet faller (t.ex. kapitalbelopp enligt avtal i första hand, skadestånd i andra hand).
- **Alternativa grunder** för samma yrkande anges som separata grunder ("Käranden grundar sitt yrkande på var och en av följande omständigheter").
- **Rättegångskostnader** alltid.

### 4.2 Grunder: rättsfakta, inte bevisfakta eller juridik

Under Grunder anges endast de konkreta omständigheter som är av omedelbar betydelse för den rättsföljd som yrkas (rättsfakta). Bakgrund och indicier (bevisfakta) hör hemma i Utveckling av talan; lagtolkning och praxis i Rättslig argumentation. Kontrollera att grunderna, om de är sanna, räcker för att bifalla yrkandet utan att rätten behöver gå till texten i övrigt.

Mönster (subsumtion rekvisit för rekvisit):

```
REGEL: Enligt [lagrum] gäller att [rättsföljd] inträder om (1) [rekvisit 1],
(2) [rekvisit 2] och (3) [rekvisit 3].

GRUNDER (rättsfakta, ett per rekvisit):
a) [konkret omständighet som uppfyller rekvisit 1, med datum/belopp],
b) [konkret omständighet som uppfyller rekvisit 2],
c) [konkret omständighet som uppfyller rekvisit 3].

BEVIS: varje punkt a)–c) har minst ett bevis i bevisuppgiften med
bevistemat "till styrkande av att …".

SLUTSATS (i rättslig argumentation): Eftersom a)–c) är uppfyllda följer
[rättsföljd] av [lagrum], och yrkandet ska bifallas.
```

### 4.3 Kedja i varje argument

`TES → REGEL → SUBSUMTION → PRAXIS → SLUTSATS`

1. Tes: vad som ska visas ("Bolaget har rätt till ersättning för merkostnaden").
2. Regel: lagrummet med rekvisit, ordagrant eller nära parafras ur verktygsresultatet.
3. Subsumtion: varje rekvisit mot konkreta fakta, med hänvisning till bevis.
4. Praxis: HD:s tolkning av rekvisitet ("HD har i NJA [år] s. [sida] uttalat att …"), läst i fulltext.
5. Slutsats: rättsföljden i målet.

### 4.4 Föregripa svarandens invändningar

Ta upp de invändningar som svaranden kan väntas göra, utan att bli defensiv:
- preskription eller försenad reklamation: datum för krav och avbrott, med bevis;
- kvittning: varför motfordran inte finns eller inte är förfallen;
- jämkning (t.ex. 36 § avtalslagen eller skadeståndsrättslig jämkning): varför förutsättningarna saknas;
- bristande passivlegitimation: vem som är avtalspart eller skadevållare;
- ansvarsbegränsning i avtal: tolkning och eventuell oskälighet.

Mönster: "Svaranden kan tänkas invända att [invändning]. En sådan invändning saknar fog. För det första … För det andra … HD har i [referens] … Invändningen kan därför inte leda till att käromålet ogillas."

Avväg: i dispositiva mål ska du inte åberopa omständigheter som skadar käranden bara för att bemöta en invändning som kanske aldrig kommer. Diskutera med användaren vilka invändningar som ska föregripas i ansökan och vilka som ska sparas till yttrandet över svaromålet.

---

## Steg 5: Dokumentets struktur

Strukturen följer domstolarnas vägledning (Stockholms tingsrätt, Patent- och marknadsdomstolens riktlinjer för beredning av tvistemål; Domstolsverkets blankett Ansökan om stämning, DV 161) och publicerade stämningsansökningar från myndigheter och ombud. Rubrikerna "STÄMNINGSANSÖKAN" och "ANSÖKAN OM STÄMNING" används båda i praktiken. Numrera avsnitt (1, 2, 3 …) och stycken (1.1, 1.2 …) löpande; ange bilagor som "bilaga [nr]".

### Ingress

```
[Ort] den [datum]

[Namn] tingsrätt
[Postadress / e-postadress till domstolen]

STÄMNINGSANSÖKAN

Kärande:      [Namn], [personnummer / organisationsnummer]
              [Postadress]
              [E-post, telefon]

Ombud:        Advokaten [namn] / Juristen [namn]
              [Byrå, postadress]
              [E-post, telefon]

Svarande:     [Namn], [personnummer / organisationsnummer]
              [Postadress]
              [E-post, telefon, om kända]
              [Uppgivet ombud, om känt]

Saken:        [Fordran / Skadestånd / Fastställelse / …]

Forum:        [10 kap. 1 § rättegångsbalken / 10 kap. 16 § rättegångsbalken
              (forumavtal, bilaga [nr])]
```

Valfri inledningsmening när ombud anmäler sig: "Med stöd av bifogad fullmakt, bilaga [nr], anmäler sig [ombud] som ombud för [kärande] och får för [kärandens] räkning anföra följande."

### 1 YRKANDEN

Samtliga yrkanden samlas här, även yrkanden om edition och sekretess. Inga yrkanden längre ner i texten.

```
1.1  [Käranden] yrkar att tingsrätten ska förplikta [svaranden] att till
     [käranden] betala [belopp] kronor jämte ränta på beloppet enligt
     6 § räntelagen (1975:635) från den [datum] till dess betalning sker.

1.2  [I andra hand / För det fall tingsrätten inte bifaller yrkandet
     under 1.1] yrkar [käranden] att tingsrätten ska förplikta
     [svaranden] att till [käranden] betala [belopp] kronor jämte ränta
     enligt [4 § tredje stycket och 6 §] räntelagen från den [datum]
     till dess betalning sker.

1.3  [Fastställelse:] [Käranden] yrkar att tingsrätten ska fastställa
     att [beskrivning av rättsförhållandet, t.ex. avtalet mellan parterna
     daterat den … har upphört att gälla den …].

1.4  [Käranden] yrkar ersättning för sina rättegångskostnader [med ett
     belopp som kommer att anges senare / med [belopp] kronor, varav
     [belopp] kronor avser ombudsarvode], jämte ränta enligt 6 §
     räntelagen från dagen för tingsrättens dom till dess betalning sker.
```

Regler för yrkanden:
- Bestämda belopp i kronor, med räntans startdag och lagrum. Startdagen ska motsvaras av en grund (förfallodag, kravdatum + 30 dagar, delgivningsdag).
- Fullgörelse av annat än betalning: beskriv exakt vad svaranden ska göra, så att domen kan verkställas.
- Solidariskt ansvar: "solidariskt med varandra".
- Ränta på rättegångskostnader löper enligt 18 kap. 8 § RB med ränta enligt 6 § räntelagen från dagen då målet avgörs.

### 2 VAD MÅLET HANDLAR OM (rekommenderas)

Tre till åtta numrerade stycken som på en halv sida förklarar tvisten: parterna, avtalet eller händelsen, vad som gått fel, vad käranden kräver och vilken rättsfråga domstolen ska avgöra. Skriv det så att domaren förstår målet efter första sidan.

### 3 GRUNDER

```
3.1  [Käranden] grundar sitt yrkande under 1.1 på följande omständigheter.

3.2  Parterna ingick den [datum] ett avtal enligt vilket [käranden]
     skulle [prestation] och [svaranden] skulle betala [belopp] kronor
     (bilaga [nr]).

3.3  [Käranden] fullgjorde sin prestation den [datum].

3.4  Betalningen förföll den [datum]. [Svaranden] har inte betalat.

3.5  [Svaranden] är därför skyldig att betala [belopp] kronor jämte
     dröjsmålsränta från förfallodagen.

3.6  Till grund för yrkandet under 1.2 åberopas i andra hand att …
```

Endast rättsfakta. Varje yrkande, även ränteyrkandet, ska ha sin grund. Ange tydligt vilken grund som hör till vilket yrkande. Grunder för ett eventuellt sekretessyrkande anges också här.

### 4 UTVECKLING AV TALAN

Bakgrunden och de ytterligare omständigheter (bevisfakta) som stöder grunderna, i kronologisk ordning och med underrubriker efter händelseförloppet. Texten ska som huvudregel inte vara argumenterande. Hänvisa löpande till bilagor: "(bilaga 4)". Ange alltid varifrån ett påstående kan beläggas.

Exempel på stycke:

```
4.3.2  Den 14 mars [år] skickade [käranden] en faktura om [belopp]
       kronor med förfallodag den 13 april [år] (bilaga 5). Fakturan
       angav att dröjsmålsränta skulle tas ut vid sen betalning.
       [Svaranden] bekräftade mottagandet per e-post samma dag utan att
       invända mot beloppet (bilaga 6).
```

### 5 RÄTTSLIG ARGUMENTATION

Här argumenterar du rättsligt, med lagtext, förarbeten, prejudikat och doktrin som har hittats med verktygen, och förklarar varför de åberopade omständigheterna leder till den yrkade rättsföljden. Disposition: ett underavsnitt per tvistig rättsfråga, i kedjan tes → regel → subsumtion → praxis → slutsats. Föregrip här de invändningar som valts ut i steg 4.4. Undvik upprepning av utvecklingen av talan; hänvisa till styckenumren.

Integrering av praxis:

```
5.4  Av fast praxis följer att [rättsregel]. HD har i NJA [år] s. [sida]
     uttalat att "[kort citat ur domskälen, läst med read_legal_document]"
     (p. [punkt]). Överfört till detta mål innebär det att [tillämpning
     på de åberopade omständigheterna under 3.3–3.4].
```

Otillåtet: listor med referenser utan förklaring, referenser vars innehåll inte har lästs, och att tillskriva ett avgörande ett uttalande som inte finns i den text verktyget returnerade.

### 6 BEVISNING

Bevisuppgift enligt 42 kap. 2 § första stycket 3 RB: varje bevis med bevistema. Bevistemat ska ta sikte på konkreta faktiska omständigheter. Otydliga teman som "att svaranden brutit mot avtalet" godtas inte; skriv "till styrkande av att [svaranden] inte levererade [vara] senast den [datum]".

Två godtagbara format, välj efter målets storlek:

**Format A — tema vid varje bevis (mindre mål):**

```
6.1  Skriftlig bevisning

     1. Avtal daterat den [datum], bilaga 1, till styrkande av att
        parterna avtalat om [prestation], pris och förfallodag.

     2. Faktura nr [nr] daterad den [datum], bilaga 2, till styrkande
        av att [käranden] krävt betalning av [belopp] kronor med
        förfallodag den [datum].

6.2  Muntlig bevisning

     1. Partsförhör med [kärandens företrädare], [befattning], till
        styrkande av att [omständighet]. [Namn] ska höras om
        [förhörstema: avtalsförhandlingarna, leveransen och kontakterna
        med svaranden efter förfallodagen].

     2. Vittnesförhör med [namn], [adress, telefon, e-post], till
        styrkande av att [omständighet]. [Namn] ska höras om
        [förhörstema].
```

**Format B — numrerade bevisteman (större mål):** formulera teman under bokstäver ("Till styrkande av att a) … b) …"), grupperade under rubriker per sakfråga, och ange vid varje bevis "Till styrkande av a), c) och f)".

Bevisuppgiften är ofta preliminär i detta skede, men ange den alltid. Har käranden ännu inte bestämt sin bevisning, skriv "[Käranden] åberopar för närvarande [ingen ytterligare] bevisning och återkommer med fullständig bevisuppgift." För vittnen gäller kraven på kontaktuppgifter i 33 kap. 1 § RB. Bifoga kopior av skriftliga bevis och markera relevanta avsnitt.

### 7 ÖVRIGT / MÅLETS HANDLÄGGNING

Önskemål om handläggningen bör anges (42 kap. 2 § andra stycket RB). Ta ställning till:
- **Tredskodom**: om käranden vill att tredskodom ska kunna meddelas om svaranden inte svarar (ange då kostnadsanspråket redan nu), eller om käranden motsätter sig det.
- **Muntlig förberedelse / skriftlig handläggning**: om målet kan avgöras på handlingarna eller kräver huvudförhandling.
- **Förlikning**: om käranden är öppen för förlikningsdiskussion eller särskild medling (42 kap. 17 §).
- **FT-mål**: om käranden yrkar att allmänna regler ska tillämpas (1 kap. 3 d § andra stycket), med skälen.
- **Ansökningsavgift**: "Ansökningsavgiften har betalats den [datum]." eller att den betalas i e-tjänsten.
- **Översättning** om svaranden behöver delges på annat språk.

### Underskrift och bilagor

```
[Ort] som ovan

[Kärandens namn]

______________________
[Namn], advokat / ombud för [käranden]

FÖRTECKNING ÖVER BILAGOR
1.  Fullmakt
2.  Registreringsbevis för [käranden] och [svaranden]
3.  [Avtal daterat …]
4.  [Faktura …]
5.  [Betalningskrav / påminnelse daterad …]
6.  [Korrespondens …]
```

Bilagor är bara handlingar som käranden ger in. Rättsfall och lagtext är inte bilagor; de citeras i texten.

---

## Steg 6: Språk och redigering

- Skriv modern, klar juridisk svenska. Korta meningar. Aktiv form där det går.
- Benämn parterna konsekvent: fullt namn första gången med en kort beteckning ("Bolaget", "Säljaren", "[efternamn]"); domstolar använder också "käranden" och "svaranden".
- Typfraser: "[Käranden] yrkar att tingsrätten ska förplikta …", "till dess betalning sker", "till grund för yrkandet åberopas", "till styrkande av att", "[Namn] ska höras om", "Som ovan".
- Datum skrivs "den 3 januari 2026" i löptext; belopp "100 000 kronor" (mellanslag som tusentalsavgränsare).
- Lagrum: "42 kap. 2 § rättegångsbalken"; paragraftecken med fast mellanslag.
- Ingen längdgräns: ansökan ska vara så fullständig som saken kräver, men utan upprepningar. Grunderna ska vara korta; utvecklingen får vara lång.
- Hitta aldrig på datum, belopp, namn eller referenser; använd `[…]`.

---

## Steg 7: Dokumentformat

Skapa en .docx om miljön kan skapa filer; annars ge hela texten i svaret.

> Claude: använd `docx`-skillen för att skapa Word-filen.

- Typsnitt med stöd för å, ä, ö och é (t.ex. Times New Roman, Garamond, Arial), 12 pt; radavstånd 1,15–1,5; marginaler ca 2,5 cm; A4.
- Ingressen som tabell utan synliga ramar.
- Rubriker numrerade och i versaler (1 YRKANDEN, 2 VAD MÅLET HANDLAR OM …); stycken numrerade 1.1, 1.2 …
- Sidnumrering "[sida] ([antal])" uppe till höger, som i domstolarnas och myndigheternas inlagor.
- Bilagor som separata, numrerade pdf-filer; bilagenumret även på första sidan av varje bilaga.

---

## Kontrollista före leverans

**Formkrav (42 kap. 2 § och 33 kap. 1 § RB)**
- [ ] Domstol, parter med person-/organisationsnummer, adresser, e-post, telefon; ombud
- [ ] Bestämt yrkande för varje anspråk, inklusive ränta (lagrum + startdag) och rättegångskostnader
- [ ] Utförlig redogörelse för omständigheterna; grund angiven för varje yrkande
- [ ] Bevisuppgift med konkret bevistema för varje bevis; förhörstema för muntlig bevisning
- [ ] Forumgrund
- [ ] Önskemål om handläggning (tredskodom, muntlig förberedelse, förlikning)
- [ ] Underskrift; fullmakt; registreringsbevis; bilageförteckning
- [ ] Ansökningsavgift (belopp kontrollerat på domstol.se)

**Materiellt**
- [ ] Varje rekvisit i den åberopade regeln har en grund och ett bevis
- [ ] Preskription och reklamation kontrollerade
- [ ] Ränteberäkningen följer räntelagen och grunden för startdagen är angiven
- [ ] Rätt val mellan stämning och betalningsföreläggande; FT-gränsen kontrollerad
- [ ] Skiljeavtal eller forumavtal kontrollerat

**Källor**
- [ ] Varje lagrum kommer från `search_swedish_legislation` med giltighetsperiod som omfattar rätt datum
- [ ] Varje avgörande kommer från verktygsresultat, har kontrollerats med `find_ruling_by_case_number` och de citerade skälen har lästs med `read_legal_document`
- [ ] Motstridig praxis har redovisats för användaren
- [ ] Inga platshållare kvar utan att användaren upplysts om vad som ska fyllas i

Avsluta svaret med en kort lista till användaren: uppgifter som saknas, antaganden, ej verifierade punkter och strategiska val som bör stämmas av (t.ex. andrahandsyrkanden, vilka invändningar som föregrips, tredskodom). Påminn om att utkastet ska granskas av en behörig jurist innan det ges in.
