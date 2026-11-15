---
name: juridisk-pm
description: "Upprättande av juridiska PM (promemorior, legal memo) enligt svensk rätt — objektiv analys av en rättsfråga med fråga, kort svar, bakgrund och sakförhållanden, rättslig analys utifrån lag, förarbeten, prejudikat och doktrin, slutsats och rekommendation samt källförteckning. Använd när användaren behöver svar på en juridisk fråga från verksamheten, en riskbedömning av en konkret situation, en bedömning av om en åtgärd är tillåten, ett internt PM till styrelse, ledning eller klient, eller en promemoria med hänvisningar till lagtext, NJA, HFD, AD och förarbeten. Ger ett utkast för granskning av behörig jurist, inte juridisk rådgivning."
---

# Juridiskt PM (promemoria)

Du upprättar professionella juridiska PM för en intern juristfunktion eller en advokatbyrå. PM:et är en objektiv, strukturerad analys av en rättsfråga enligt svensk rätt, byggd på lagtext, förarbeten, rättspraxis och — när den finns tillgänglig — doktrin.

Uttryckliga instruktioner från användaren (struktur, längd, mottagare, språk) går före standardinställningarna i den här skillen. PM:et är ett utkast och researchstöd, inte juridisk rådgivning, och ska granskas av en behörig jurist innan beslut fattas.

**Källkontroll**: Ange paragrafer, SFS-nummer, NJA- och andra referenser, målnummer och förarbetsställen endast utifrån verktygsresultat i konversationen eller dokument som användaren lämnat — aldrig ur minnet. Följ sök- och citeringsreglerna i skillen `iura` (verktyg, `in_force_as_of`, referatformat). Hittas ingen källa för ett påstående: skriv det i PM:et och markera påståendet som overifierat. Är verktygen inte tillgängliga: skriv det överst i PM:et och markera alla hänvisningar som overifierade.

## Vad ett juridiskt PM är

- **Besvarar en avgränsad rättsfråga** från verksamheten, styrelsen eller en kollega.
- **Är objektivt** — redovisar argument för och emot; det är ingen partsinlaga.
- **Bygger på rättskällor** — i svensk rättskälleordning: lag, förarbeten, prejudikat, doktrin.
- **Mynnar ut i slutsats och rekommendation** som mottagaren kan agera på.

## Indata — fråga bara efter det som saknas

1. **Rättsfrågan** — vad exakt ska besvaras.
2. **Sakförhållanden** — datum, parter, avtal, belopp; konsument eller näringsidkare; anställd eller uppdragstagare.
3. **Mottagare** — styrelse, ledning, bolagsjurist, extern klient (styr ton och djup).
4. **Ramar** — tidsfrist, längd, språk (standard svenska).
5. **Kända källor** — avtal, beslut, avgöranden som användaren vill få bedömda (kontrollera även dessa).

Är fakta knapphändiga: skriv utifrån uttryckliga antaganden och redovisa dem i PM:et.

## Arbetsgång

1. Formulera rättsfrågan och dela upp den i delfrågor.
2. Fastställ relevant datum för lydelsen (`in_force_as_of`: i dag, eller datum för händelsen).
3. Sök för varje delfråga **innan** du skriver:
   - lagtext: `search_swedish_legislation` (avtalslagen och rättegångsbalken finns inte i sökindexet: hämta dem från riksdagen.se via `search_web` och ange källan);
   - prejudikat: `search_swedish_supreme_court_rulings` / `search_swedish_supreme_administrative_court_rulings`, inom arbetsrätt `search_swedish_labour_court_rulings`, inom specialområden MIG/MÖD/PMÖD-verktygen;
   - underrättspraxis: `search_swedish_court_of_appeal_rulings`, `search_swedish_administrative_court_of_appeal_rulings`;
   - kända referenser: `find_ruling_by_case_number`, därefter `read_legal_document` för de stycken du stöder dig på;
   - förarbeten (prop., SOU, Ds, bet.) och aktuella lagförslag: `search_web` (riksdagen.se, regeringen.se);
   - EU-rätt där den är relevant: `search_eu_legislation`, `search_eu_court_of_justice_case_law`.
4. Skriv PM:et i strukturen nedan.
5. Gå igenom checklistan före leverans.
6. Anropa gärna `show_sources_panel` med `cited_document_ids` för de citerade källorna.

## Struktur

### 1. Rubrik

```
PROMEMORIA

Till:          [Mottagare — namn, funktion]
Från:          [Författare / juristfunktion]
Datum:         [ÅÅÅÅ-MM-DD]
Ärende:        [Kort beskrivning av frågan — en mening]
Konfidentiell: [Ja/Nej — standard: Ja]
```

Saknas mottagare: skriv "Juridiska avdelningen" eller fråga.

### 2. Fråga

En precis formulering av rättsfrågan (eller huvudfråga och delfrågor). Frågan ska vara snäv, innehålla de avgörande fakta och vara neutral.

- Inte: "Vad gäller om ansvarsbegränsningar?"
- Utan: "Kan bolagets ansvarsbegränsning till tolv månadsavgifter i ett SaaS-avtal med en näringsidkare göras gällande om ett dataintrång har orsakats av grov vårdslöshet hos bolaget, eller riskerar den att jämkas med stöd av 36 § avtalslagen?"
- "Är en konkurrensklausul på 24 månader utan ersättning i ett anställningsavtal för en säljare bindande, med hänsyn till 38 § avtalslagen?"
- "Har bolaget avbrutit preskriptionen av fordran genom e-postmeddelandet den [datum]?"

### 3. Kort svar

1–3 stycken. Börja med en tydlig slutsats: **Ja**, **Nej**, **Sannolikt**, **Det beror på …**. Ange den bärande regeln och den viktigaste risken eller reservationen. Inga referenser här — det är en sammanfattning. Den som bara läser det korta svaret ska kunna fatta ett preliminärt beslut.

### 4. Bakgrund och sakförhållanden

Objektiv redogörelse för relevanta fakta, kronologiskt eller tematiskt, **utan rättsliga kvalificeringar** (skriv inte "avtalsbrott" eller "grov vårdslöshet" här). Skilj mellan:
- **Fakta** (lämnade av användaren eller framgår av handlingar), och
- **Antaganden** (gjorda för att analysen ska gå att genomföra — markera dem som användaren bör bekräfta).

### 5. Rättslig analys

Kärnan i PM:et. Redovisa rättskällorna i svensk ordning och tillämpa dem fråga för fråga.

**Rättskällor, i denna ordning:**
1. **Lag** — paragraf med SFS-nummer och kontrollerad lydelse ("36 § lagen (1915:218) om avtal och andra rättshandlingar på förmögenhetsrättens område, lydelse gällande [datum]"). EU-förordningar gäller direkt; vid direktiv: den svenska genomförandelagen.
2. **Förarbeten** — prop., SOU, Ds, bet. Ange sida endast om du har sett den ("prop. 1975/76:81 s. 137").
3. **Prejudikat** — HD (NJA) och HFD; AD, MIG, MÖD, PMÖD inom sina områden. Ange domstol, datum, referens eller målnummer exakt som verktyget returnerar och de punkter i domskälen du bygger på.
4. **Underrättspraxis** — hovrätter och kammarrätter, uttryckligen markerad som icke-prejudicerande.
5. **Doktrin** — bara om den citeras i ett avgörande du läst eller har lämnats av användaren; ange då var den citeras.

**IRAC för varje delfråga** (egen underrubrik per delfråga):
- **I — Fråga**: den specifika delfrågan.
- **R — Regel**: lag, förarbeten, prejudikat, underrättspraxis enligt ovan. Finns motstridig praxis: redovisa båda linjerna med referenser och ange vilken som är nyare eller dominerande — det är en av de mest värdefulla delarna av ett PM.
- **A — Tillämpning**: tillämpa regeln på fakta; analogier och distinktioner mot avgörandena; argument **för och emot**; motpartens troliga invändningar; bedöm argumentens styrka och osäkerhetsgrad ("fast praxis", "inget direkt prejudikat — analogi med …", "obesvarad fråga").
- **C — Delslutsats**: svaret på delfrågan.

Exempel på hur en verifierad källa redovisas: *"HD har i NJA 2017 s. 113 (dom den 24 februari 2017, mål T 3034-15, p. 27) uttalat att frågan om en ansvarsbegränsning kan godtas numera i princip bör bedömas enligt 36 § avtalslagen."* Använd det endast om det är relevant och om du själv har kontrollerat stycket med `read_legal_document`.

### 6. Slutsats och rekommendation

- **Svar på frågan** — tydligt och direkt.
- **Riskbedömning** — låg / måttlig / hög / kritisk, med en mening om varför.
- **Rekommendation** — t.ex. "gå vidare under förutsättning att …", "omförhandla klausul X", "avstå", "inhämta extern rådgivning i fråga Y".
- **Reservationer** — vilka antaganden slutsatsen vilar på och vilka fakta som behöver bekräftas.
- **Nästa steg** — konkreta åtgärder med tidsfrister där sådana finns (t.ex. preskriptions- eller reklamationsfrister; ange dem bara om de har kontrollerats i lagtexten).

### 7. Källförteckning

Numrerad lista, i ordningen:
1. Lagstiftning (inkl. EU-rätt) — fullständig rubrik, SFS- eller CELEX-nummer, paragraf, kontrollerad lydelse.
2. Förarbeten.
3. Rättspraxis — domstol, datum, referens/målnummer; prejudikat före underrättspraxis.
4. Övrigt (doktrin, myndighetsvägledning från `search_web`, markerat som icke-bindande).

Varje post anger vilket påstående i PM:et den stöder.

## Skrivregler

- **Objektivitet**: analysera, övertyga inte. Slutsatsen ska följa av analysen, inte tvärtom.
- **Precision i hänvisningar**: "3 kap. 1 § skadeståndslagen (1972:207)", "NJA [år] s. [sida]", "AD [år] nr [nr]", "prop. [riksmöte]:[nr] s. [sida]". Hovrätts- och kammarrättsavgöranden citeras exakt som verktyget returnerar dem — omvandla inte själv till RH- eller RK-nummer.
- **Lydelse**: säg vilken lydelse du har kontrollerat; gäller frågan en händelse i det förflutna, kontrollera lydelsen vid den tidpunkten och eventuella övergångsbestämmelser.
- **Språk**: professionell men tillgänglig svenska; mottagaren är ofta inte jurist. Förklara facktermer första gången (t.ex. "jämkning — domstolen får sätta ned eller bortse från ett villkor"). Korta meningar, aktiv form.
- **Skilj** verktygsresultat från egen bedömning ("Av domskälen framgår …" respektive "Enligt min bedömning …").
- **Längd**: kort PM (en enkel fråga) 2–4 sidor; standard (1–2 frågor med delfrågor) 5–10 sidor; omfattande analys 10–20 sidor. Hellre kort och precist än långt och urvattnat.

## Filformat

Skapa en .docx om miljön kan skapa filer; annars ge hela texten i svaret.
> Claude: använd `docx`-skillen för Word-filen.

Använd typsnitt med fullt stöd för svenska tecken (å, ä, ö, é).

## Checklista före leverans

- [ ] Rubrik, fråga, kort svar, bakgrund, rättslig analys, slutsats/rekommendation och källförteckning finns.
- [ ] Varje paragraf, referens, målnummer och förarbetsställe kommer från verktygsresultat eller användarens handlingar.
- [ ] Kontrollerad lydelse (giltighetsperiod) anges för den lag som bär analysen.
- [ ] Nyckelstycken i de avgöranden som bär slutsatsen är lästa med `read_legal_document`.
- [ ] Prejudikat skiljs från underrättspraxis; motstridig praxis redovisas.
- [ ] Fakta skiljs från antaganden.
- [ ] Slutsatsen följer av analysen och riskbedömningen är motiverad.
- [ ] Det framgår att PM:et är ett utkast för granskning av behörig jurist.

## Samspel med andra skills

- `iura` — sökmetod och citeringsregler.
- `avtalsgranskning` — när frågan kräver genomgång av ett helt avtal; ett PM kan fördjupa en omtvistad klausul därifrån.
- `nda-granskning` — sekretessavtal.
- `tabellgranskning` — RÖDA flaggor i en portfölj kan kräva ett fördjupat PM.
- `stamningsansokan` / `svaromal` — när analysen leder till process.
