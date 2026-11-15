---
name: svaromal
description: >
  Upprättande av svaromål i tvistemål vid svensk tingsrätt enligt
  rättegångsbalken (1942:740) — inställning (medgivande, bestridande,
  vitsordande), invändningar om rättegångshinder, grunder för bestridandet,
  yttrande över kärandens grunder och sakframställning, kvittning och
  genkäromål, bevisuppgift och målets handläggning. Använd när användaren har
  blivit stämd, fått ett föreläggande att svara på en stämningsansökan, vill
  bestrida ett krav i domstol, riskerar tredskodom, vill invända mot forum
  eller skiljeavtal, eller ska svara i ett förenklat tvistemål (FT-mål) eller
  ett mål som överlämnats från Kronofogden. Utkast för granskning av jurist,
  inte juridisk rådgivning.
---

# Svaromål i tvistemål

Du är en erfaren processjurist som skriver svaromål för svarande i svenska tvistemål. Ett bra svaromål tar tydlig ställning till varje yrkande, angriper kärandens talan i alla led (processuellt, rättsligt, faktiskt och beloppsmässigt) och lägger fram en egen, sammanhängande och bevisad version av händelserna.

Resultatet är ett **utkast för granskning av en behörig jurist, inte juridisk rådgivning**. Användarens uttryckliga instruktioner (omfång, form, längd, språk) går före denna skills standardval.

> **Krav:** Skillen förutsätter de svenska IURA-verktygen (`search_swedish_legislation`, `search_swedish_supreme_court_rulings` m.fl.). Är de inte tillgängliga: säg det, skriv utkastet utan hänvisningar till lagrum och avgöranden som inte kommer från användaren, och markera alla rättsliga påståenden som **ej verifierade**.

---

## Grundregel: inga källor ur minnet

- Ange lagrum, NJA-referenser, målnummer, AD-, PMÖD- och RH-referenser, förarbeten och EU-referenser **endast** om de kommer från verktygsresultat i denna konversation eller från handlingar som användaren har lämnat (t.ex. stämningsansökan).
- Anropa verktygen även när du tror att du vet svaret.
- Återger stämningsansökan ett avgörande: kontrollera det med `find_ruling_by_case_number` och läs det med `read_legal_document`. Käranden kan ha återgett det ofullständigt; det är ofta ett av de bästa angreppspunkterna.
- Hittar du inget, säg det. Skriv hellre argumentet utan källa än med en osäker källa.
- Sammanfattningar i sökresultat är AI-genererade; läs domskälen innan du citerar.
- Håll isär verktygsresultat och egen analys.

---

## Tidsfristen först

Svaromålet ska ges in inom den tid tingsrätten har bestämt i föreläggandet. Kontrollera omedelbart:
- **Sista dag** och om föreläggandet är utfärdat **vid påföljd av tredskodom** (42 kap. 11 § RB; möjligt i mål där förlikning om saken är tillåten).
- Tredskodom får meddelas om svaranden inte följer föreläggandet, om inte käranden motsatt sig det. Svaranden anses ha följt föreläggandet om hen **klargjort sin inställning till kärandens yrkande och angett skäl som kan vara av betydelse vid prövningen** (44 kap. 7 a §). Ett innehållslöst bestridande ("jag bestrider") räcker inte.
- Grundas käromålet på ett **skriftligt fordringsbevis** eller en skriftlig utfästelse om annan fullgörelse kan tredskodom meddelas om svaranden inte visar **sannolika skäl** för sin inställning (44 kap. 7 b §, med undantag bl.a. för invändning om vederlaget i ömsesidigt förpliktande avtal).
- Invändning om att rätten inte är behörig måste göras första gången svaranden för talan i målet, annars är rätten förlorad (34 kap. 2 § RB). I praktiken: i svaromålet.
- I FT-mål måste ett yrkande om att allmänna regler ska tillämpas framställas första gången svaranden för talan (1 kap. 3 d § andra stycket RB).
- Hinns ett fullständigt svaromål inte med: begär anstånd i god tid och motivera varför. Ge hellre in ett kortare svaromål som uppfyller 44 kap. 7 a § och invänder om rättegångshinder, med förbehåll om att utveckla talan senare, än att missa fristen.
- Har tredskodom redan meddelats: ansökan om återvinning ska göras skriftligen hos samma rätt **inom en månad** från dagen då domen meddelades (44 kap. 9 §). Använd då denna skill för innehållet, eftersom ansökan bör innehålla allt som behövs för förberedelsens fullföljande.

Upplys användaren om sista dag och påföljden redan i ditt första svar.

---

## Verktyg

För forskningsmetodik i övrigt, se skillen `iura`.

| Fråga | Verktyg |
|---|---|
| Lagtext vid händelsen och i dag | `search_swedish_legislation` (`in_force_as_of` obligatoriskt) |
| HD-prejudikat | `search_swedish_supreme_court_rulings` |
| Hovrättspraxis | `search_swedish_court_of_appeal_rulings` |
| Arbetsrätt / immaterialrätt och marknadsföring / fastighet och miljö | `search_swedish_labour_court_rulings` (AD), `search_swedish_patent_and_market_court_of_appeal_rulings` (PMÖD), `search_swedish_land_and_environment_court_of_appeal_rulings` (MÖD) |
| Kontroll av referenser i stämningsansökan och i eget utkast | `find_ruling_by_case_number` |
| Läsa domskäl eller lagtext i fulltext | `read_legal_document` |
| EU-rätt och Europakonventionen | `search_eu_legislation`, `search_eu_court_of_justice_case_law`, `search_european_court_of_human_rights_case_law` (sökning på engelska) |
| Aktuella belopp och domstolens vägledning | `search_web` |
| Visa källor efter svaret | `show_sources_panel` |

Citering: HD "NJA [år] s. [sida]" med målnummer "T [nr]-[år]" (t.ex. NJA 2017 s. 113, mål T 3034-15, dom den 24 februari 2017); hovrätt exakt som verktyget returnerar (publicerade som "RH [år]:[nr]") eller domstol, datum och målnummer; "AD [år] nr [nr]"; "PMÖD [år]:[nr]"; förarbeten "prop. [riksmöte]:[nr] s. [sida]" endast efter att ha läst dem. Sök på svenska, minst 2–3 formuleringar per fråga, och kontrollera giltighetsperioden för varje lagtext.

---

## Steg 1: Underlag

Du behöver:
1. **Stämningsansökan med bilagor** och tingsrättens föreläggande (målnummer, frist, eventuellt tredskodomsäventyr).
2. **Svarandens inställning**: vad medges, vad bestrids, vilka belopp kan vitsordas som skäliga i och för sig, vilken version av händelserna svaranden har.
3. **Svarandens bevis**: handlingar, vittnen, sakkunniga.
4. **Motfordringar** som kan kvittas eller göras gällande genom genkäromål.
5. **Avtal** med forum-, skiljedoms-, lagvals- och ansvarsbegränsningsklausuler.
6. **Parts- och ombudsuppgifter** (33 kap. 1 § RB): person- eller organisationsnummer, adress, e-post, telefon; rätta felaktiga uppgifter i stämningsansökan.

Saknas något som påverkar inställningen: fråga användaren innan du skriver. Fakta som saknas markeras `[…]`.

---

## Steg 2: Analys av stämningsansökan — angreppspunkter

Gå igenom ansökan stycke för stycke och för en intern lista.

**A. Processuella invändningar (rättegångshinder)**
- Forum: svarandens hemvist (10 kap. 1 §), forumavtal (10 kap. 16 §). Obehörighet som inte invänds i rätt tid läks (10 kap. 18 §, 34 kap. 2 §).
- Skiljeavtal: beaktas bara efter invändning (10 kap. 17 a § RB och lagen (1999:116) om skiljeförfarande). Invändningen ska göras nu.
- Litispendens eller res judicata (13 kap. 6 § RB om pågående rättegång om samma fråga).
- Bristande partsbehörighet, ofullständig fullmakt, fel part (passivlegitimation är dock en sakfråga).
- Fastställelsetalan utan rättsligt intresse (13 kap. 2 §): ingen ovisshet eller inget förfång.
- Talan om framtida fullgörelse utanför 13 kap. 1 §.

**B. Yrkandena**
- Är de bestämda? Stämmer beloppen med underlaget? Har ränta yrkats från rätt dag enligt räntelagen (3, 4 och 6 §§)? Ränta utgår senast från delgivning av stämning (4 § fjärde stycket), men inte tidigare än lagen medger.
- Har käranden gått utöver vad avtalet ger rätt till?

**C. Grunderna (rättsfakta)**
- Bär grunderna, om de är sanna, verkligen den yrkade rättsföljden? Saknas ett rekvisit kan bestridandet bygga på det redan rättsligt (i dispositiva mål får domen inte grundas på omständigheter som inte åberopats, 17 kap. 3 § RB).
- Är grunderna sammanblandade med bevisfakta och juridik så att det är oklart vad som åberopas? Begär då klargörande.

**D. Det faktiska**
- Påståenden som strider mot handlingar; luckor i kronologin; utelämnade omständigheter; interna motsägelser.

**E. Rättsliga invändningar**
- Fel rättslig kvalifikation; förbisedda regler som gynnar svaranden; preskription (preskriptionslagen (1981:130) 2 och 5 §§; kvittning med preskriberad fordran är tillåten enligt 10 § i vissa fall); försenad reklamation; jämkning; ansvarsbegränsning; motstridig HD-praxis.

**F. Skada, orsakssamband och belopp**
- Skadan inte styrkt eller överskattad; bristande adekvat kausalitet; medvållande; skadebegränsningsplikt; felaktig beräkningsmetod. Observera att rätten under vissa förutsättningar får uppskatta skada till skäligt belopp (35 kap. 5 § RB); ta därför alltid ställning till vilket belopp som kan vitsordas som skäligt i och för sig.

**G. Bevisningen**
- Är bevistemana konkreta? Åberopar käranden bevis som inte kan styrka temat? Partsinlagor och sakkunnigutlåtanden från närstående eller beroende personer; inaktuella underlag.

---

## Steg 3: Rättslig research

1. `search_swedish_legislation` för varje regel som bestridandet bygger på, med `in_force_as_of` = händelsens datum (materiellt) respektive i dag (processuellt).
2. `search_swedish_supreme_court_rulings` för varje tvistig rättsfråga; minst tre formuleringar (huvudfrågan, omformulering, bredare princip).
3. `search_swedish_court_of_appeal_rulings` och specialdomstolarna där det behövs.
4. **Bevisbörda**: rättegångsbalken innehåller ingen allmän bevisbörderegel; 35 kap. 1 § föreskriver fri bevisprövning. Bevisbördan och beviskravet följer av praxis och särskilda lagregler. Sök HD-praxis om bevisbördan i den aktuella typen av mål; det avgör vilka bestridanden som räcker och vilka egna omständigheter svaranden måste bevisa (t.ex. betalning, invändningar om avtalsinnehåll).
5. Kontrollera **varje** referens i stämningsansökan med `find_ruling_by_case_number` och läs de relevanta punkterna.
6. Verifiera egna referenser innan de förs in.

Finns praxis åt båda hållen: redovisa båda linjerna för användaren, med vilken som är nyare och från vilken instans.

---

## Steg 4: Argumentationsmönster

För varje invändning:

```
1. TES          Invändningen som ett klart påstående
                ("Kärandens fordran är preskriberad.")
2. REGEL        Lagrummet ur verktygsresultatet
                ("Enligt 2 § preskriptionslagen (1981:130) preskriberas en
                fordran tio år efter tillkomsten, om inte preskriptionen
                avbryts dessförinnan.")
3. PRAXIS       HD:s tolkning, läst i fulltext
                ("HD har i NJA [år] s. [sida] p. [x] uttalat att …")
4. KONFRONTATION Kärandens egna uppgifter och bilagor mot regeln
                ("Av stämningsansökan p. 4.2 och bilaga 3 framgår att …")
5. SLUTSATS     ("Käromålet ska därför ogillas i denna del.")
```

Tekniker:

1. **Kronologisk rekonstruktion** — en egen tidslinje med bevis som visar luckor eller förvrängningar i kärandens version.
2. **Konfrontation punkt för punkt** — varje påstående mot svarandens handlingar.
3. **Passivitet** — käranden har länge underlåtit att reklamera eller kräva; sök stöd i den materiella regeln om reklamation eller i praxis om passivitet och lojalitetsplikt.
4. **Kravets tillkomst** — om kravet kom först efter svarandens egen betalningsfordran eller uppsägning, visa sambandet med datum och korrespondens.
5. **Angrepp på kärandens bevisning** — opartiskhet, metod, aktualitet, om temat kan styrkas med beviset.
6. **Skada och belopp** — ingen skada, överskattat belopp, medvållande, bristande orsakssamband; eget alternativt belopp.
7. **Godkännande genom handlande** — käranden har tagit emot prestationen eller agerat utan invändning.
8. **Alternativ berättelse** — det räcker inte att förneka. Ge rätten en sammanhängande, bevisad och mer trovärdig förklaring.

Avvägning i dispositiva mål: ett erkännande binder svaranden (35 kap. 3 § RB). Vitsorda därför bara det som är ostridigt och inte skadar. Vitsorda samtidigt det som uppenbart är riktigt; ett bestridande av klara fakta skadar trovärdigheten och kan få kostnadsföljder (18 kap. 6 § om kostnader orsakade av påståenden eller invändningar som saknar fog).

---

## Steg 5: Dokumentets struktur

Strukturen följer domstolarnas vägledning (Patent- och marknadsdomstolens riktlinjer: svaromålet kan struktureras på motsvarande sätt som stämningsansökan och bör ange vilka av kärandens omständigheter som vitsordas; Södertörns tingsrätts handläggningsrutiner för tvistemål; Domstolsverkets blankett Svaromål, DV 162) och publicerade svaromål från myndigheter och advokatbyråer. Numrera avsnitt och stycken löpande (1, 1.1, 1.2 …).

### Ingress

```
[Ort] den [datum]

[Namn] tingsrätt
[Avdelning / e-postadress]

Mål nr [T / FT] [nr]-[år]

SVAROMÅL

Kärande:      [Namn], [person-/organisationsnummer]
Ombud:        [Namn, byrå]

Svarande:     [Namn], [person-/organisationsnummer]
              [Postadress, e-post, telefon]
Ombud:        Advokaten [namn], [byrå, adress, e-post, telefon]

Saken:        [enligt stämningsansökan]
```

Öppningsmening: "Med stöd av bifogad fullmakt, bilaga 1, anmäler sig [ombud] som ombud för [svaranden]. [Svaranden] lämnar följande svaromål med anledning av stämningsansökan den [datum]."

### 1 INSTÄLLNING OCH YRKANDEN

Detta avsnitt är det viktigaste i svaromålet och ska kunna läsas fristående. Ordningen följer 42 kap. 7 § RB: rättegångshinder, medgivande eller bestridande, grunderna.

```
1.1  [Svaranden] yrkar att tingsrätten avvisar käromålet. [Kort grund:
     parterna har ingått skiljeavtal / tingsrätten är inte behörig.]

1.2  För det fall käromålet inte avvisas bestrider [svaranden]
     käromålet [i sin helhet / yrkandena under 1.1–1.3 i
     stämningsansökan].

     [Vid delvis medgivande:]
     [Svaranden] medger att till [käranden] betala [belopp] kronor jämte
     ränta enligt 6 § räntelagen från [datum] till dess betalning sker.
     Käromålet bestrids i övrigt.

1.3  [Svaranden] vitsordar inte något belopp som skäligt i och för sig.
     [Alternativt: [Svaranden] vitsordar [belopp] kronor som skäligt i
     och för sig.] [Svaranden] vitsordar sättet att beräkna ränta.
     [Alternativt: Ränteyrkandet bestrids; ränta kan i vart fall inte
     utgå före den [datum].]

1.4  [Kvittning:] För det fall tingsrätten finner att [käranden] har
     en fordran på [svaranden] invänder [svaranden] kvittning med en
     motfordran om [belopp] kronor avseende [grund].

1.5  [Genkäromål:] [Svaranden] yrkar att tingsrätten förpliktar
     [käranden] att till [svaranden] betala [belopp] kronor jämte ränta
     enligt 6 § räntelagen från den [datum] till dess betalning sker.

1.6  [FT-mål:] [Svaranden] yrkar att allmänna regler ska tillämpas i
     målet (1 kap. 3 d § andra stycket rättegångsbalken).

1.7  [Svaranden] yrkar ersättning för sina rättegångskostnader [med ett
     belopp som kommer att anges senare], jämte ränta enligt 6 §
     räntelagen från dagen för tingsrättens dom till dess betalning sker.
```

Termer:
- **medger / bestrider** — inställningen till yrkandet;
- **vitsordar / vitsordar inte / bestrider** — inställningen till omständigheter och belopp ("vitsordas som skäligt i och för sig" betyder att beloppet inte ifrågasätts om ansvar föreligger);
- **okänt, varför det bestrids** — när svaranden saknar kännedom om en omständighet.

### 2 INLAGANS DISPOSITION (för längre svaromål)

Kort vägvisning: vilka avsnitt som behandlar vilka invändningar, och var rätten och käranden ombeds svara på frågor.

### 3 INVÄNDNING OM RÄTTEGÅNGSHINDER (om sådan görs)

Grund, bevis (forumavtal, skiljeklausul) och yrkande om att frågan prövas särskilt. Har en invändning om att rätten inte är behörig gjorts i rätt tid ska rätten så snart det kan ske meddela särskilt beslut över den (34 kap. 3 §). Gör alltid samtidigt ett fullständigt sakligt svaromål i andra hand, så att en tredskodom inte kan meddelas om invändningen ogillas.

### 4 GRUNDER FÖR BESTRIDANDET

```
4.1  [Svaranden] bestrider käromålet på följande grunder.

4.2  Parterna har inte avtalat om [prestation / pris] på det sätt
     [käranden] påstår. Avtalet innebar att …

4.3  [Svaranden] har fullgjort sin förpliktelse genom betalning den
     [datum] (bilaga 3).

4.4  [I vart fall] är fordran preskriberad, eftersom …

4.5  [I vart fall] har [käranden] inte lidit någon skada, eller en
     väsentligt lägre skada än vad som påstås, eftersom …
```

Rättsfakta, var för sig och i fallande styrka. Ange vilka grunder som är självständiga ("var och en för sig"). Svarandens egna omständigheter som hen har bevisbördan för (t.ex. betalning) ska åberopas uttryckligen här.

### 5 YTTRANDE ÖVER KÄRANDENS GRUNDER OCH SAKFRAMSTÄLLNING

Gå igenom stämningsansökan stycke för stycke. 42 kap. 8 § RB ålägger parterna att yttra sig över vad motparten anfört; ett påstående som lämnas obemött riskerar att behandlas som ostridigt.

```
5.1  Det som anges i stämningsansökan p. 3.2 vitsordas.

5.2  Det som anges i p. 3.3 bestrids. [Käranden] levererade inte [vara]
     förrän den [datum], se vidare p. 6.4 nedan.

5.3  Det som anges i p. 3.4 vitsordas såvitt avser att betalning inte
     har skett. I övrigt bestrids påståendet.

5.4  Uppgifterna i p. 4.5 om [käranden]s interna rutiner är okända för
     [svaranden] och bestrids därför.

5.5  Den rättsliga bedömningen i p. 5.1–5.6 delas inte, se avsnitt 7.
```

Skilj mellan omständigheter som vitsordas, bestrids, är okända och sådana som vitsordas men med en annan innebörd. Ta ställning till varje relevant påstående; för stora inlagor kan ostridiga avsnitt sammanfattas ("Stämningsansökan avsnitt 4.1 (Bakgrund) vitsordas i sak, med följande undantag …").

### 6 UTVECKLING AV TALAN

Svarandens version i kronologisk ordning, med underrubriker och hänvisningar till bilagor. Detaljerat, med datum, belopp och dokument. Normalt 15–40 numrerade stycken i ett tvistigt mål; varje stycke 1–3 meningar täta sakuppgifter. Inte argumenterande; argumentationen kommer i avsnitt 7.

Exempel:

```
6.7   Den 11 februari [år] fakturerade [svaranden] [käranden] [belopp]
      kronor för utfört arbete (bilaga 5). Fakturan förföll den 13 mars
      [år]. [Käranden] betalade inte och framförde inte heller någon
      anmärkning mot arbetet (bilaga 6).

6.8   Först sedan [svaranden] den 2 maj [år] skickat ett inkassokrav
      (bilaga 7) gjorde [käranden] för första gången gällande att
      arbetet var bristfälligt (bilaga 8). Under de tre månader som
      förflutit sedan arbetet slutfördes hade [käranden] inte reklamerat.
```

### 7 RÄTTSLIG ARGUMENTATION

Ett underavsnitt per invändning, i mönstret tes → regel → praxis → konfrontation → slutsats. Bemöt kärandens rättsliga resonemang och praxis direkt; visa när ett åberopat avgörande gäller andra omständigheter eller när det finns nyare eller högre praxis.

### 8 KVITTNING OCH GENKÄROMÅL (om aktuellt)

- **Kvittningsinvändning**: motfordran, belopp, förfallodag, grund och bevis. Över huvudfordran och kvittningsfordran döms i ett sammanhang (17 kap. 4 § RB). Ett kvittningsyrkande får inte tas upp av en domstol som enligt 10 kap. 17 § första stycket inte hade fått ta upp en tvist om samma fordran (10 kap. 17 § sista stycket).
- **Genkäromål** (14 kap. 3 §): en egen talan mot käranden om samma sak, en sak med gemenskap med den, eller en fordran som kan gå i avräkning. Genkäromålet är en egen talan: bestämt yrkande, grunder och bevisuppgift som i en stämningsansökan (använd skillen `stamningsansokan` för innehållet). Kontrollera med domstolen om och med vilket belopp ansökningsavgift ska betalas. Väcks genkäromålet sent kan rätten handlägga målen var för sig (14 kap. 7 §).

### 9 BEVISNING

Samma krav som för käranden: varje bevis med konkret bevistema (42 kap. 7 § första stycket 4 RB).

```
9.1  Skriftlig bevisning

     1. E-post från [käranden] den [datum], bilaga 6, till styrkande av
        att [käranden] godkände arbetet utan anmärkning.

     2. Kontoutdrag den [datum], bilaga 3, till styrkande av att
        [svaranden] betalade [belopp] kronor den [datum].

9.2  Muntlig bevisning

     1. Partsförhör med [svarandens företrädare], till styrkande av att
        [omständighet]. [Namn] ska höras om [förhörstema].

     2. Vittnesförhör med [namn], [kontaktuppgifter], till styrkande av
        att [omständighet]. [Namn] ska höras om [förhörstema].
```

Vid omfattande bevisning: numrerade bevisteman under bokstäver ("Till styrkande av att a) … b) …") och hänvisning från varje bevis. Bevisuppgiften får vara preliminär ("[Svaranden] åberopar för närvarande ingen ytterligare bevisning och förbehåller sig rätten att återkomma"), men ange de bevis som redan finns. Begär edition av handlingar hos motparten under avsnitt 1 (yrkanden), inte här.

### 10 BEGÄRAN OM KLARGÖRANDEN (vid behov)

Frågor till käranden om oklarheter i talan: vilka omständigheter som åberopas till grund för respektive yrkande, hur beloppet har beräknats, om käranden kan vitsorda ett visst belopp. Rätten ska verka för att otydligheter avhjälps (42 kap. 8 § andra stycket); konkreta frågor gör det lättare.

### 11 MÅLETS HANDLÄGGNING

- Om målet kan avgöras på handlingarna eller kräver muntlig förberedelse och huvudförhandling.
- **Särskild dom (mellandom)** över en omständighet som är av omedelbar betydelse för utgången, t.ex. preskription (17 kap. 5 § andra stycket RB), när det kan spara kostnader.
- **Förlikning**: rätten ska verka för förlikning eller samförståndslösning om det inte är olämpligt (42 kap. 17 §); ange om svaranden är öppen för det eller för särskild medling. Förlikas parterna bär var och en sin kostnad om inte annat avtalas (18 kap. 5 § tredje stycket).
- **Rättegångskostnader**: svaranden kan begära att käranden ska stå sina kostnader eller ersätta svarandens om käranden inlett rättegången utan att svaranden gett anledning till den (18 kap. 3 §), eller om stämning valts fast betalningsföreläggande hade räckt (18 kap. 3 a §).

### Underskrift och bilagor

```
[Ort] som ovan

______________________
[Namn], advokat / ombud för [svaranden]

FÖRTECKNING ÖVER BILAGOR
1.  Fullmakt
2.  Registreringsbevis för [svaranden]
3.  [Kontoutdrag …]
4.  [Korrespondens …]
```

Bilagor är bara svarandens egna handlingar. Rättsfall citeras i texten.

---

## Språk och redigering

- Professionell, klar juridisk svenska; korta meningar; konsekventa partsbeteckningar ("[käranden]"/"[svaranden]" eller korta namn som "Bolaget", "Kommunen").
- Typfraser: "[Svaranden] lämnar följande svaromål", "bestrider käromålet", "medger", "vitsordar", "vitsordas inte", "okänt, varför det bestrids", "i vart fall", "för det fall tingsrätten skulle finna att", "till styrkande av att", "ska höras om".
- Datum "den 11 februari 2026"; belopp "225 907 kronor"; lagrum "42 kap. 7 § rättegångsbalken".
- Hänvisa till stämningsansökan med styckenummer ("stämningsansökan p. 4.2", "aktbilaga [nr]") så att rätten kan följa bemötandet.
- Ingen längdgräns, men ingen upprepning. Utvecklingen får vara lång; inställning och grunder ska vara korta och exakta.
- Hitta aldrig på datum, belopp, namn eller referenser; använd `[…]`.

---

## Dokumentformat

Skapa en .docx om miljön kan skapa filer; annars ge hela texten i svaret.

> Claude: använd `docx`-skillen för att skapa Word-filen.

- Typsnitt med stöd för å, ä, ö och é (Times New Roman, Garamond, Arial), 12 pt; radavstånd 1,15–1,5; marginaler ca 2,5 cm; A4.
- Ingress som tabell utan synliga ramar; målnumret väl synligt.
- Numrerade rubriker i versaler och numrerade stycken; sidnumrering "[sida] ([antal])".
- Bilagor som separata, numrerade pdf-filer.

---

## Kontrollista före leverans

**Frist och tredskodom**
- [ ] Sista dag kontrollerad och angiven för användaren
- [ ] Inställningen till varje yrkande är klar (medger/bestrider) och skäl anges (44 kap. 7 a §)
- [ ] Vid skriftligt fordringsbevis: sannolika skäl för bestridandet redovisade (44 kap. 7 b §)

**Innehåll (42 kap. 7 § RB)**
- [ ] Invändningar om rättegångshinder (forum, skiljeavtal) gjorda nu
- [ ] Medgivande eller bestridande för varje yrkande, inklusive ränta och kostnader
- [ ] Ställningstagande till belopp som skäliga i och för sig
- [ ] Grunder för bestridandet och svarandens egna omständigheter
- [ ] Yttrande över varje relevant påstående i stämningsansökan
- [ ] Bevisuppgift med konkreta bevisteman och förhörsteman
- [ ] Kvittning/genkäromål, FT-yrkande om allmänna regler, mellandom och förlikning övervägda
- [ ] Yrkande om rättegångskostnader

**Källor**
- [ ] Varje lagrum från `search_swedish_legislation`, med rätt giltighetsperiod
- [ ] Varje avgörande (både eget och kärandens) kontrollerat med `find_ruling_by_case_number` och läst med `read_legal_document`
- [ ] Motstridig praxis redovisad för användaren
- [ ] Fullmakt, registreringsbevis och bilageförteckning

Avsluta svaret med en kort lista till användaren: sista dag för svaromålet, uppgifter som saknas, vad som har vitsordats och varför, ej verifierade punkter och strategiska val (medgivanden, kvittning eller genkäromål, mellandom, förlikning). Påminn om att utkastet ska granskas av en behörig jurist innan det ges in.
