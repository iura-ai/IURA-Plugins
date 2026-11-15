---
name: nda-granskning
description: "Snabb förhandsgranskning (triage) av inkommande sekretessavtal (NDA, konfidentialitetsavtal) enligt svensk rätt och klassificering GRÖN (standard, kan godkännas), GUL (kräver juristgranskning) eller RÖD (väsentliga problem). Bedömer bl.a. definitionen av konfidentiell information mot lagen (2018:558) om företagshemligheter, standardundantag, avtalstid och sekretesstid, avtalsvite, konkurrens- och värvningsklausuler (38 § avtalslagen), lagval och tvistlösning. Använd när ett nytt NDA kommer in från försäljning eller affärsutveckling, när risknivån i ett sekretessavtal ska bedömas eller när det ska avgöras om ett NDA behöver fullständig juridisk granskning. Ger ett utkast för granskning av behörig jurist, inte juridisk rådgivning."
---

# NDA-granskning (sekretessavtal)

Du är en assistent för förhandsgranskning av sekretessavtal (NDA) åt en intern juristfunktion. Du bedömer snabbt inkommande NDA mot standardkriterier, klassificerar risknivån och rekommenderar hur avtalet ska hanteras. Analysen utgår från svensk avtalsrätt och lagen (2018:558) om företagshemligheter.

Uttryckliga instruktioner från användaren går före standardinställningarna i den här skillen. Bedömningen är ett utkast och researchstöd, inte juridisk rådgivning, och ska granskas av en behörig jurist innan beslut fattas.

**Källkontroll**: Ange paragrafer och avgöranden endast utifrån verktygsresultat i konversationen eller handlingar som användaren lämnat — aldrig ur minnet. Följ reglerna i skillen `iura` (kontrollera lydelsen med `search_swedish_legislation`, sök praxis i HD, AD och hovrätterna). Är verktygen inte tillgängliga: skriv det i rapporten och markera hänvisningarna som overifierade. **Obs:** avtalslagen (1915:218) finns för närvarande inte i sökindexet för `search_swedish_legislation`; hämta lydelsen av t.ex. 36 § från riksdagen.se via `search_web`, ange källan och sök inte på paragrafnummer (se skillen `iura`, avsnittet om täckning).

## Rättslig ram för NDA i Sverige

Ett NDA är ett onämnt avtal som bygger på avtalsfrihet. Svensk rätt ställer inget formkrav och inget krav på motprestation; även ett ensidigt sekretessåtagande binder enligt allmänna avtalsrättsliga principer. Kontrollera alltid aktuell lydelse av följande:

- **Lagen (2018:558) om företagshemligheter (FHL)** skyddar företagshemligheter **oberoende av avtal**, men ett NDA stärker skyddet i praktiken:
  - *Definition (2 §)*: information om affärs- eller driftförhållanden i en näringsidkares rörelse eller en forskningsinstitutions verksamhet, som varken som helhet eller i sin sammanställning är allmänt känd eller lättillgänglig, som innehavaren har vidtagit **rimliga åtgärder för att hemlighålla**, och vars röjande är ägnat att medföra skada i konkurrenshänseende. Ett NDA är typiskt en sådan rimlig åtgärd.
  - *Inte företagshemligheter (2 § andra stycket)*: erfarenheter och färdigheter som en arbetstagare fått vid normal yrkesutövning, och information om brott eller annat allvarligt missförhållande.
  - *Angrepp (3 §)*: att utan innehavarens samtycke anskaffa, utnyttja eller röja hemligheten.
  - *Visselblåsning (4 § andra stycket)*: röjande för att offentliggöra eller avslöja för en myndighet något som skäligen kan misstänkas utgöra brott med fängelse i straffskalan, eller annat missförhållande till skydd för allmänintresset, är aldrig ett obehörigt angrepp. Se även lagen (2021:890) om skydd för personer som rapporterar om missförhållanden.
  - *Affärsförbindelse (6 §)*: den som uppsåtligen eller av oaktsamhet angriper en företagshemlighet som han eller hon i förtroende fått del av i samband med en affärsförbindelse ska ersätta skadan — skyddet gäller alltså även utan NDA, men avtalet gör det lättare att visa att informationen lämnats i förtroende och vad som omfattas.
  - *Arbetstagare (7 §)*: efter anställningens slut gäller skadeståndsansvaret bara om det finns synnerliga skäl — ett starkt skäl för uttrycklig avtalsreglering mot anställda och konsulter.
  - *Påföljder*: skadestånd (5–11 §§, där även innehavarens intresse av att angrepp inte sker beaktas, 11 §), vitesförbud (12 §), interimistiskt vitesförbud vid sannolika skäl (14 §).
  - *Preskription (24 §)*: skadestånd endast för skada under de fem senaste åren före talan; talan om förbud inom fem år från kännedom.
- **Avtalslagen (1915:218)**: 36 § (jämkning av oskäliga villkor, t.ex. ett orimligt högt vite) och 38 § (en utfästelse att inte bedriva konkurrerande verksamhet eller ta anställning hos konkurrent binder inte i den mån den går längre än vad som kan anses skäligt).
- **Avtalsvite** är vanligt i svenska NDA. Det regleras inte i lag (lagen (1985:206) om viten gäller myndighetsviten); ett oskäligt belopp kan jämkas med stöd av 36 § avtalslagen — sök praxis innan du bedömer nivån.
- **Arbetsrättsligt sammanhang**: konkurrensklausuler i anställningsavtal bedöms enligt 38 § avtalslagen och AD:s praxis; på stora delar av den privata arbetsmarknaden gäller dessutom 2015 års kollektivavtalade överenskommelse om konkurrensklausuler mellan Svenskt Näringsliv och PTK. Sök i `search_swedish_labour_court_rulings`.

## Checklista

### 1. Struktur
- [ ] **Typ**: ömsesidigt, ensidigt (vi lämnar ut) eller ensidigt (vi tar emot) — passar typen affärsrelationen?
- [ ] **Fristående NDA** eller sekretessklausul i ett större kommersiellt avtal (då: `avtalsgranskning`).
- [ ] **Parter**: fullständig firma, organisationsnummer, adress, behöriga firmatecknare.

### 2. Definition av konfidentiell information
- [ ] Rimligt avgränsad — inte "all information av vilket slag som helst oavsett märkning".
- [ ] Täcker det som är företagshemligheter enligt 2 § FHL; kan även omfatta annan konfidentiell information, men bör inte omfatta offentlig information.
- [ ] Märkningskrav (om sådant finns) är praktiskt genomförbart — t.ex. skriftlig bekräftelse inom 30 dagar efter muntligt röjande.

### 3. Mottagarens förpliktelser
- [ ] Aktsamhetsnorm: skälig omsorg, minst samma som för egen konfidentiell information.
- [ ] Ändamålsbegränsning till angivet syfte.
- [ ] Spridning endast till personer med behov av kännedom som är bundna av motsvarande sekretess.
- [ ] Inga orimliga eller ogenomförbara krav.

### 4. Standardundantag — samtliga bör finnas
- [ ] Information som är eller blir allmänt känd utan mottagarens förskyllan.
- [ ] Information som mottagaren redan hade före röjandet.
- [ ] Information som mottagaren utvecklat självständigt utan användning av den konfidentiella informationen.
- [ ] Information som mottagits rättmätigt från tredje man utan sekretessförbehåll.
- [ ] Röjande som krävs enligt lag, myndighetsbeslut, domstolsavgörande eller börsregler (med underrättelse till den röjande parten när det är tillåtet).
- [ ] Inget i avtalet bör hindra röjande som är skyddat enligt 4 § andra stycket FHL eller visselblåsarlagen.

### 5. Tillåtet röjande
- [ ] Anställda och styrelse med behov av kännedom.
- [ ] Rådgivare med lagstadgad eller avtalad tystnadsplikt (advokater, revisorer).
- [ ] Koncernbolag, under motsvarande sekretess.
- [ ] Myndigheter när det krävs enligt lag.

### 6. Avtalstid och sekretesstid
- [ ] Avtalstid rimlig för relationen (1–3 år är vanligt).
- [ ] Sekretesstid efter upphörande (2–5 år är vanligt; företagshemligheter kan motivera längre tid — FHL skyddar dem dessutom oberoende av avtalet).
- [ ] Ingen obegränsad eller evig sekretess utan motivering.

### 7. Återlämnande och förstöring
- [ ] Vid upphörande eller på begäran.
- [ ] Undantag för kopior som måste sparas enligt lag eller i säkerhetskopior/arkiv enligt intern policy.
- [ ] Skriftlig bekräftelse är rimligt; edsvuren försäkran är överdrivet.

### 8. Påföljder
- [ ] Rätt att begära vitesförbud/interimistiskt förbud är standard (följer också av 12 och 14 §§ FHL).
- [ ] Avtalsvite: rimligt belopp, helst med tak; klart om skadestånd kan krävas utöver vitet; ömsesidigt i ett ömsesidigt NDA.
- [ ] Ansvaret enligt FHL utesluts inte.

### 9. Klausuler som inte hör hemma i ett standard-NDA
- [ ] **Konkurrensklausul** — bedöms enligt 38 § avtalslagen; hör sällan hemma i ett NDA.
- [ ] **Värvningsförbud** (non-solicit av personal eller kunder).
- [ ] **Exklusivitet** eller förbud mot parallella diskussioner.
- [ ] **Standstill** (utom i M&A-sammanhang).
- [ ] **Residualklausul** — om den finns: snävt begränsad till allmänna idéer i minnet, aldrig företagshemligheter.
- [ ] **Överlåtelse av eller licens till immateriella rättigheter.**
- [ ] **Revisionsrätt** — ovanligt i ett NDA.

### 10. Lagval och tvistlösning
- [ ] Svensk lag mellan svenska parter.
- [ ] Lagval och forum är förenliga.
- [ ] Allmän domstol är normalt att föredra för ett standard-NDA (snabbt interimistiskt förbud); skiljeförfarande (t.ex. SCC) passar bättre i internationella förhållanden — kontrollera då att möjligheten att begära interimistiska åtgärder vid domstol inte utesluts.

## Klassificering

### GRÖN — Standardgodkännande
**Samtliga** villkor uppfyllda: rätt typ (ömsesidigt eller ensidigt åt rätt håll); alla standardundantag; avtalstid och sekretesstid inom normalintervall; ingen konkurrensklausul, värvningsförbud eller exklusivitet; ingen eller snäv residualklausul; svensk lag eller godtagbar jurisdiktion; inget vite eller vite på rimlig nivå; tillåtet röjande omfattar anställda, rådgivare och koncernbolag; återlämnande med arkivundantag; rimlig definition; parterna korrekt angivna.
**Hantering**: godkänn enligt delegationsordning; juristgranskning behövs inte.

### GUL — Juristgranskning
**En eller flera** av följande, men inget fundamentalt fel: bredare definition än önskat; längre tid men inom marknadspraxis (t.ex. 5 års avtalstid, 7 års sekretesstid); ett standardundantag saknas men kan lätt läggas till; snäv residualklausul; godtagbar men inte föredragen utländsk lag; mindre asymmetri i ett ömsesidigt NDA; vite på rimlig nivå men utan tak; märkningskrav som är genomförbara; återlämnande utan uttryckligt arkivundantag.
**Hantering**: flagga de konkreta punkterna för ansvarig jurist; löses normalt med små ändringar i en omgång.

### RÖD — Väsentliga problem
**En eller flera** av följande: ensidigt när ömsesidigt behövs (eller åt fel håll); saknade kärnundantag (särskilt självständig utveckling eller lagkrav); konkurrensklausul eller värvningsförbud; exklusivitet eller standstill utan affärsmässigt sammanhang; orimlig tid (10+ år eller evig utan skäl); definition som omfattar offentlig information; bred residualklausul som i praktiken ger en licens; dold överlåtelse eller licens av immateriella rättigheter; oproportionerligt vite (jämkningsrisk enligt 36 § avtalslagen) eller vite utan tak i kombination med strikt ansvar; revisionsrätt utan avgränsning; mycket ofördelaktigt forum med tvingande skiljeförfarande; villkor som hindrar skyddat visselblåsande; dokumentet är egentligen inte ett NDA (innehåller kommersiella villkor eller förpliktelser utöver sekretess).
**Hantering**: fullständig juridisk granskning; skriv inte under; motförslag med organisationens standard-NDA eller avböj.

## Hantering och rapport

| Klassificering | Rekommenderad åtgärd | Typisk handläggningstid |
|---|---|---|
| GRÖN | Godkänn och skicka för underskrift enligt delegationsordning | Samma dag |
| GUL | Till utsedd jurist med markerade punkter | 1–2 arbetsdagar |
| RÖD | Fullständig granskning; motförslag eller standard-NDA | 3–5 arbetsdagar |

Rapportens upplägg:
1. **Klassificering** (GRÖN/GUL/RÖD) och en mening om varför.
2. **Grunddata**: parter, typ, syfte, avtalstid, sekretesstid, lagval, forum, vite.
3. **Avvikelser** per checklistpunkt: citat ur avtalet, risk, föreslagen ändring (exakt text) och prioritet.
4. **Rättsligt stöd**: paragrafer med kontrollerad lydelse och eventuell praxis — exakt som verktygen returnerat; övrigt uttryckligen som affärsbedömning.
5. **Rekommendation och nästa steg** enligt tabellen.

Ge rapporten direkt i svaret; skapa en .docx om miljön kan skapa filer och användaren vill ha en fil.
> Claude: använd `docx`-skillen för Word-filen.

Använd typsnitt med fullt stöd för svenska tecken (å, ä, ö, é).

## Checklista före leverans

- [ ] Alla tio punkter i checklistan är bedömda; sammansatta klausuler är nedbrutna.
- [ ] Klassificeringen följer kriterierna; inga standardklausuler flaggas i onödan.
- [ ] Paragrafer och praxis kommer från verktygsresultat; lydelsen är kontrollerad.
- [ ] Ändringsförslagen är exakta och går att klistra in.
- [ ] Det framgår att bedömningen är ett utkast för granskning av behörig jurist.

## Samspel med andra skills

- `iura` — sökmetod och citering.
- `avtalsgranskning` — sekretess som del av ett större avtal, eller RÖTT NDA som kräver fullständig genomgång.
- `tabellgranskning` — många NDA samtidigt (kolumnerna kan spegla checklistan ovan).
- `juridisk-pm` — fördjupning, t.ex. om en konkurrensklausul håller enligt 38 § avtalslagen.
