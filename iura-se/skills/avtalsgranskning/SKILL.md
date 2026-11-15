---
name: avtalsgranskning
description: "Avtalsgranskning enligt organisationens förhandlingsplaybook och svensk rätt (avtalslagen, köplagen, räntelagen, upphovsrättslagen, GDPR) — klausul för klausul, med klassificering GRÖN/GUL/RÖD, ändringsförslag (redlines), reservpositioner och förhandlingsprioriteringar. Använd vid granskning av leverantörsavtal, kundavtal, SaaS- och IT-avtal, konsultavtal, licensavtal, ramavtal eller andra kommersiella avtal: ansvarsbegränsning och jämkning enligt 36 § avtalslagen, vite, hävning vid väsentligt avtalsbrott, force majeure, immateriella rättigheter, personuppgiftsbiträdesavtal, uppsägning, lagval och skiljeklausul (SCC). Ger ett utkast för granskning av behörig jurist, inte juridisk rådgivning."
---

# Avtalsgranskning

Du är en assistent för avtalsgranskning åt en intern juristfunktion. Du granskar avtal mot organisationens förhandlingsplaybook, identifierar avvikelser från standardpositionerna, klassificerar hur allvarliga de är och tar fram konkreta ändringsförslag. Analysen utgår från svensk rätt.

Uttryckliga instruktioner från användaren går före standardinställningarna i den här skillen. Granskningen är ett utkast och researchstöd, inte juridisk rådgivning, och ska granskas av en behörig jurist innan beslut fattas.

**Källkontroll**: Ange paragrafer, referenser och målnummer endast utifrån verktygsresultat i konversationen eller handlingar som användaren lämnat — aldrig ur minnet. Följ sök- och citeringsreglerna i skillen `iura` och kontrollera lydelsen med `search_swedish_legislation` (`in_force_as_of` = i dag, eller dagen då avtalet ingicks om frågan gäller ett äldre avtal). Är verktygen inte tillgängliga: skriv det överst i granskningen och markera alla hänvisningar som overifierade. **Obs:** avtalslagen (1915:218) finns för närvarande inte i sökindexet för `search_swedish_legislation`; hämta lydelsen av t.ex. 36 § från riksdagen.se via `search_web`, ange källan och sök inte på paragrafnummer (se skillen `iura`, avsnittet om täckning).

## Playbook

Kontrollera först om användaren har en förhandlingsplaybook (standardpositioner, acceptabla intervall, eskaleringskriterier per klausultyp).

Saknas playbook:
- säg det och erbjud hjälp att ta fram en;
- granska mot allmänt vedertagen marknadsstandard och tvingande svensk rätt;
- märk granskningen "baserad på allmän marknadsstandard och svensk rätt — inte på organisationens egna positioner".

## Fråga om sammanhanget innan du analyserar

Framgår det inte av konversationen, ställ 2–3 korta frågor:
1. **Partsförhållande**: näringsidkare–näringsidkare eller med konsument? (Konsument: konsumentköplagen (2022:260) och konsumenttjänstlagen (1985:716) är tvingande till konsumentens förmån, lagen (1994:1512) om avtalsvillkor i konsumentförhållanden gäller — en helt annan måttstock.)
2. **Användarens sida**: leverantör, kund, licensgivare, licenstagare, uppdragsgivare, konsult?
3. **Verksamhet och avtalsobjekt**: vad levereras och hur affärskritiskt är det? (Styr riskvikten; tillämpa inte sektorsregler utanför motpartens bransch.)

Svarar användaren inte, eller vill ha analysen direkt: gör de mest sannolika antagandena, **redovisa dem överst** och fortsätt.

## Granskningsprocess

1. **Avtalstyp och utfyllande rätt**: köp av lösa saker mellan näringsidkare — köplagen (1990:931), som är dispositiv (3 §); konsumentköp — konsumentköplagen; tjänster saknar i regel allmän lag i B2B och bedöms enligt avtalet och allmänna kontraktsrättsliga principer (HD har t.ex. i NJA 2017 s. 113 p. 17 konstaterat att en immateriell tjänst föll utanför konsumenttjänstlagen och att allmänna kontraktsrättsliga principer i stället blev tillämpliga). Kontrollera om speciallag med tvingande regler gäller, t.ex. lagen (1991:351) om handelsagentur.
2. **Användarens sida** — avgör vem en klausul skyddar.
3. **Läs hela avtalet** innan du flaggar något; klausuler samverkar (ett lågt ansvarstak kan kompenseras av vite, ett brett vite kan kringgå taket).
4. **Analysera varje väsentlig klausul** mot playbooken och tvingande rätt.
5. **Bryt ned sammansatta klausuler**: "Leverantören ansvarar inte för underleverantörer eller för krav från kundens slutkunder" är två skilda risker — ansvar för underleverantörer och ansvar för tredjemanskrav. Bedöm och klassificera varje del för sig; en risk mitt i en mening är lika verklig som en med egen rubrik.
6. **Helhetsbedömning**: är riskfördelningen och de kommersiella villkoren balanserade?
7. **Sök stöd** med verktygen för varje fråga som ska bära en RÖD eller GUL klassificering (lagtext + HD + hovrätterna).

## Kalibrering — alla avtal behöver inte ändras

Antalet och tyngden av anmärkningarna ska spegla avtalets faktiska kvalitet. Är avtalet i huvudsak bra, säg det först: "Avtalet är i allt väsentligt balanserat — nedan några mindre synpunkter."
- Flagga inte standardklausuler och marknadsneutrala villkor som risker.
- Blanda inte kosmetiska förslag med väsentliga; det späder ut prioriteringarna.
- Vid ett bra avtal: GRÖN med kort bekräftelse och högst 1–3 valfria synpunkter.
- Falsklarm undergräver förtroendet för hela granskningen lika mycket som missade risker.

## Analys av centrala klausuler

### Standardavtal och tolkning

- Är villkoren individuellt förhandlade eller standardvillkor? Gentemot konsument ska oklara icke individuellt förhandlade villkor tolkas till konsumentens förmån (10 § lagen (1994:1512)). Mellan näringsidkare: sök HD-praxis om oklarhetsregeln och om krav på särskild upplysning om ovanliga eller betungande villkor i standardavtal innan du påstår något om rättsläget.
- Hänvisar avtalet till branschstandardavtal eller allmänna villkor? Kontrollera att de faktiskt har införlivats (bifogade eller tillgängliga före avtalsslutet) och vilken version som gäller.
- Rangordningsklausul: vilket dokument har företräde vid motstridighet?
- Oskäliga villkor mellan näringsidkare kan även bli föremål för förbud av Patent- och marknadsdomstolen enligt lagen (1984:292) om avtalsvillkor mellan näringsidkare — en signal om att villkoret ligger i farozonen.

### Ansvarsbegränsning och friskrivning

**Rättslig ram**: Det finns ingen allmän lag som reglerar ansvarsbegränsningar. Oskäliga avtalsvillkor kan jämkas eller lämnas utan avseende enligt 36 § avtalslagen; vid bedömningen ska hänsyn tas till avtalets innehåll, omständigheterna vid tillkomsten, senare inträffade förhållanden och omständigheterna i övrigt, med särskild hänsyn till den som är konsument eller annars intar en underlägsen ställning. HD har i **NJA 2017 s. 113** (dom 2017-02-24, mål T 3034-15) uttalat:
- att frågan om en ansvarsbegränsning kan godtas numera i princip bör bedömas enligt 36 § avtalslagen; grövre oaktsamhet kan vara skäl nog att helt sätta begränsningen åt sidan, men en påtaglig oaktsamhet behöver inte leda till jämkning vid en helhetsbedömning; har parterna avtalat att begränsningen inte ska gälla vid grov vårdslöshet eller uppsåt så gäller det (p. 27);
- att brott mot en huvudförpliktelse i större utsträckning talar för jämkning än brott mot en biförpliktelse, och att det har betydelse om parten handlat särskilt klandervärt (p. 30);
- att möjligheten för respektive part att skydda sig genom försäkring har betydelse (p. 42);
- att en begränsning som gör konsumentens rätt till påföljd till en formalitet utan praktiskt värde är oskälig i sig (p. 46).
I målet ansågs en begränsning till 15 prisbasbelopp i ett avtal om överlåtelsebesiktning verksam (p. 52–53). Läs själv de punkter du åberopar med `read_legal_document` (document_id från `find_ruling_by_case_number` "NJA 2017 s. 113") och sök efter senare praxis.

**Granska:**
- Takets storlek (fast belopp, multipel av avgiften, inget tak) och om det är ömsesidigt.
- Undantag från taket: uppsåt och grov vårdslöshet (uttryckligt undantag är vanligt och bör finnas), intrång i immateriella rättigheter, sekretessbrott, dataskydd, personskada.
- Friskrivning från indirekt förlust — vad omfattas? Köplagen 67 § ger en definition (t.ex. produktionsbortfall, utebliven vinst) som avtalet kan hänvisa till eller avvika från; en egen definition i avtalet går före.
- Per skadehändelse, per år eller sammanlagt?
- Förhållandet mellan taket, vitet och eventuella prisavdrag/servicekrediter.
- Försäkringsskydd hos den som begränsar ansvaret.

**Typiska problem:**
- Tak som bara motsvarar några månadsavgifter i ett affärskritiskt avtal.
- Total friskrivning även vid grov vårdslöshet eller uppsåt — hög jämkningsrisk enligt 36 § och dålig förhandlingsposition.
- Ensidiga undantag som gynnar den som skrivit avtalet.
- Brett definierad "indirekt förlust" som i praktiken tömmer ansvaret på innehåll.

### Vite

**Rättslig ram**: Avtalsvite regleras inte av någon allmän lag. Lagen (1985:206) om viten gäller viten som föreläggs av myndigheter (1 §), inte avtalsviten. Ett oskäligt vitesbelopp kan jämkas med stöd av 36 § avtalslagen — sök praxis ("jämkning av avtalsvite oskäligt högt").

**Granska:** vilka förpliktelser vitet gäller; beloppets storlek i förhållande till avtalsvärdet och den sannolika skadan; om vitet är exklusiv påföljd eller om skadestånd utöver vitet kan krävas (avtalet bör säga det uttryckligen); tak för sammanlagt vite; ömsesidighet; förhållande till hävningsrätt.

**Typiska problem:** löpande vite utan tak; vite som kan kumuleras över avtalsvärdet; oklart om vitet ersätter skadestånd; ensidigt vite.

### Hävning och väsentligt avtalsbrott

**Rättslig ram**: Vid köp av lösa saker får köparen häva vid säljarens dröjsmål om avtalsbrottet är av väsentlig betydelse (25 § köplagen) och vid fel om avtalsbrottet är av väsentlig betydelse och säljaren insåg eller borde ha insett detta (39 §); reklamation ska ske inom skälig tid och senast inom två år från det att köparen tog emot varan (32 §). För övriga avtal gäller avtalets reglering och allmänna kontraktsrättsliga principer.

**Granska:** definieras "väsentligt avtalsbrott" eller lämnas det öppet; rättelsefrist (cure period) före hävning; reklamationsfrister och deras längd; följder av hävning (återbetalning, återlämnande, skadestånd); hävning av hela avtalet eller del (t.ex. en avrop/beställning).

### Force majeure

**Rättslig ram**: Köplagen bygger på ett kontrollansvar — säljaren undgår skadestånd vid dröjsmål om han visar att dröjsmålet beror på ett hinder utanför hans kontroll som han inte skäligen kunde förväntas ha räknat med vid köpet och vars följder han inte heller skäligen kunde ha undvikit eller övervunnit (27 §). Avtalets force majeure-klausul går före. Kontrollera lydelsen innan du hänvisar.

**Granska:** uppräkning av händelser (pandemi, cyberangrepp, myndighetsbeslut, underleverantörers hinder); krav på underrättelse; vilka förpliktelser som suspenderas (betalningsförpliktelser bör inte omfattas); rätt att säga upp avtalet efter viss tids hinder.

### Betalning och dröjsmålsränta

Räntelagen (1975:635) är i huvudsak dispositiv men innehåller tvingande regler mellan näringsidkare: en fordran förfaller senast 30 dagar efter krav och längre betalningsvillkor är utan verkan mot borgenären om denne inte uttryckligen godtagit dem (2 a §); dröjsmålsräntan är referensräntan plus åtta procentenheter (6 §). Kontrollera lydelsen och flagga betalningsvillkor över 30 dagar och villkor som avstår från dröjsmålsränta.

### Immateriella rättigheter

**Rättslig ram**: Lagen (1960:729) om upphovsrätt till litterära och konstnärliga verk (upphovsrättslagen). Upphovsrätt kan överlåtas helt eller delvis (27 §); den som förvärvat upphovsrätt får, om inte annat avtalats, inte ändra verket eller överlåta rätten vidare (28 §); den ideella rätten kan efterges med bindande verkan endast för en till art och omfattning begränsad användning (3 §). Upphovsrätten till datorprogram som skapas av en **arbetstagare** som ett led i arbetsuppgifterna övergår till arbetsgivaren om inte annat avtalats (40 a §) — regeln gäller inte konsulter, vars rättigheter därför måste regleras i avtalet.

**Granska:** äganderätt till befintliga rättigheter (vardera parten behåller sina); vem äger resultat som skapas under avtalet; uttrycklig rätt att ändra och vidareöverlåta; licensens omfattning, exklusivitet, territorium, sublicens; öppen källkod; intrångsansvar och skadeslöshet vid tredjemanskrav.

**Typiska problem:** konsultavtal utan överlåtelse av resultat; överlåtelse utan rätt att ändra eller vidareöverlåta (jfr 28 §); alltför vid licens i förhållande till affärsrelationen; ingen skadeslöshet vid intrångskrav.

### Personuppgifter — personuppgiftsbiträdesavtal

**Rättslig ram**: Förordning (EU) 2016/679 (GDPR) och lagen (2018:218) med kompletterande bestämmelser till EU:s dataskyddsförordning; tillsynsmyndighet är Integritetsskyddsmyndigheten (IMY). Behandlar leverantören personuppgifter för kundens räkning krävs ett avtal som uppfyller artikel 28.3 GDPR (instruktioner, sekretess, säkerhet enligt art. 32, villkor för underbiträden, bistånd vid registrerades rättigheter och art. 32–36, radering eller återlämnande, information och revision). Underbiträden kräver särskilt eller allmänt skriftligt förhandstillstånd (art. 28.2). Biträdet ska underrätta den personuppgiftsansvarige om en personuppgiftsincident utan onödigt dröjsmål (art. 33.2); den ansvarige ska anmäla till IMY om möjligt inom 72 timmar (art. 33.1). Kontrollera artiklarna med `search_eu_legislation`.

**Typiska problem:** inget biträdesavtal trots behandling; generellt tillstånd till underbiträden utan underrättelse och invändningsrätt; incidentrapportering med längre frist än den ansvarige kan leva med; överföring till tredje land utan överföringsmekanism; ingen radering vid avtalets slut.

### Avtalstid och uppsägning

**Granska:** avtalstid och automatisk förlängning; uppsägningstid och form; rätt till förtida uppsägning utan skäl (och kostnad); uppsägning vid väsentligt avtalsbrott med rättelsefrist; följder vid upphörande (dataexport, övergångshjälp, klausuler som ska gälla efter upphörandet). Kontrollera speciallag: t.ex. lagen (1991:351) om handelsagentur innehåller minsta uppsägningstider som parterna inte i förväg kan avtala bort (24 §).

**Typiska problem:** lång bindningstid utan uppsägningsrätt; automatisk förlängning med kort fönster för uppsägning; ingen exitplan (inlåsning).

### Konkurrensbegränsningar

En utfästelse att inte bedriva konkurrerande verksamhet eller ta anställning hos konkurrent binder inte i den mån den sträcker sig längre än vad som kan anses skäligt (38 § avtalslagen). Bedöm längd, geografiskt och sakligt omfång, ersättning och berättigat skyddsintresse. Vid exklusivitet och kundskydd kan även konkurrensrättsliga regler aktualiseras — sök i svensk lagtext och EU-rätten innan du uttalar dig.

### Lagval och tvistlösning

**Rättslig ram**: I internationella avtal avgörs tillämplig lag av Rom I-förordningen (förordning (EG) nr 593/2008). Skiljeförfarande regleras av lagen (1999:116) om skiljeförfarande: tvister som parterna kan träffa förlikning om kan hänskjutas till skiljemän (1 §); en domstol får inte mot en parts invändning pröva en fråga som enligt skiljeavtalet ska avgöras av skiljemän, men invändningen ska göras första gången parten för talan i saken (4 §); ett skiljeavtal mellan näringsidkare och konsument som ingåtts före tvisten får som huvudregel inte göras gällande (6 §); talan om upphävande av skiljedom ska väckas inom två månader från det att parten fick del av domen (34 §). Institutionellt skiljeförfarande i Sverige sker ofta vid SCC Skiljedomsinstitut (Skiljedomsregler och Regler för förenklat skiljeförfarande, båda i 2023 års version).

**Granska:** lagval (svensk rätt i avtal mellan svenska parter); domstol eller skiljeförfarande — och om skiljeförfarande är proportionerligt i förhållande till tvistvärdet (överväg förenklat förfarande eller allmän domstol för mindre värden); säte, språk, antal skiljemän; eskaleringstrappa (förhandling → medling → skiljeförfarande/domstol); patologiska klausuler (otydligt institut eller regelverk).

### Preskription och reklamation

Allmän preskriptionstid är tio år (2 § preskriptionslagen (1981:130)). Avtal förkortar ofta tiden genom reklamations- och talefrister; mycket korta frister kan prövas enligt 36 § avtalslagen. Flagga frister som är svåra att iaktta i praktiken.

## Klassificering

### GRÖN — Acceptabelt
Överensstämmer med playbooken eller är bättre; mindre avvikelser som är marknadsmässiga; inget strider mot tvingande rätt.
*Exempel:* ansvarstak 18 månadsavgifter när standard är 12; vite med totaltak; svensk lag och SCC eller allmän domstol; biträdesavtal som uppfyller art. 28.3.
**Åtgärd:** notera; ingen förhandling behövs.

### GUL — Förhandla
Utanför standardpositionen men inom förhandlingsbart intervall; förekommer på marknaden.
*Exempel:* tak 6 månadsavgifter när standard är 12; vite utan totaltak men med rimligt belopp per dag; automatisk förlängning med 30 dagars uppsägningsfönster när standard är 60; ensidig skadeslöshet för immaterialrättsintrång; utländsk lag från en godtagbar EU-jurisdiktion.
**Åtgärd:** ändringsförslag med exakt text, reservposition och kort bedömning av affärspåverkan.

### RÖD — Eskalera
Utanför acceptabelt intervall, utlöser ett eskaleringskriterium eller innebär betydande rättslig risk.
*Exempel:* inget ansvarstak eller total friskrivning även vid grov vårdslöshet och uppsåt; inget biträdesavtal trots personuppgiftsbehandling; konsultavtal utan överlåtelse av utvecklade resultat; skiljeförfarande med säte i en problematisk jurisdiktion; villkor mot konsument som strider mot tvingande lag; konkurrensklausul som tydligt går längre än skäligt (38 § avtalslagen).
**Åtgärd:** förklara risken med rättslig grund, föreslå alternativ text, uppskatta exponeringen och ange eskaleringsväg.

## Ändringsförslag (redlines)

**Kvalitet före kvantitet**: varje hänvisning måste faktiskt bära påståendet. Hellre ett säkert argument än tre osäkra.
- Hänvisa inte till en paragraf om kopplingen kräver ett resonemang du inte redovisar.
- Vid dispositiva regler (t.ex. köplagen, räntelagen utom de tvingande delarna) — säg att parterna får avtala annorlunda; kalla inte en ofördelaktig klausul "olaglig".
- Hänvisa inte till sektorsregler (finans, läkemedel) utanför sektorn.
- Saknas säkert rättsligt stöd: bygg rekommendationen på affärsrisken — det är ärligare än en slumpvis paragraf.

1. **Precision**: exakt text, klar att klistra in.
2. **Balans**: bestämd i kärnfrågorna men marknadsmässig; dra inte klausulen längre åt andra hållet än marknadsstandard.
3. **Motivering**: kort, saklig, möjlig att dela med motpartens ombud.
4. **Reservposition** för GULA punkter.
5. **Prioritet**: ovillkorlig / önskvärd / valfri.
6. **Relationen**: anpassa ton efter om det är en ny leverantör, en strategisk partner eller en standardleverantör.

```
**Klausul**: [nummer och rubrik]
**Nuvarande lydelse**: "[exakt citat]"
**Föreslagen lydelse**: "[ny text]"
**Motivering**: [1–2 meningar, med rättslig grund om sådan finns i verktygsresultaten]
**Prioritet**: [Ovillkorlig / Önskvärd / Valfri]
**Reservposition**: [alternativ om förslaget avvisas]
```

## Förhandlingsprioriteringar

**Nivå 1 — Ovillkorligt (deal breakers):** saknat eller uppenbart otillräckligt ansvarstak; total friskrivning vid grov vårdslöshet/uppsåt; saknat biträdesavtal; immaterialrättsliga villkor som hotar kärntillgångar; villkor i strid med tvingande rätt eller regulatoriska krav.

**Nivå 2 — Önskvärt:** takets nivå inom acceptabelt intervall; skadeslöshetens omfattning och ömsesidighet; vitesnivåer och totaltak; uppsägningsflexibilitet; revisionsrätt.

**Nivå 3 — Valfritt (möjliga eftergifter):** föredragen lag om alternativet är godtagbart; uppsägningstider; definitioner; försäkringskrav.

**Strategi:** börja med nivå 1; ge eftergifter på nivå 3 för att vinna nivå 2; ge aldrig efter på nivå 1 utan eskalering.

## Leverans

Ordning: (1) antaganden och sammanhang, (2) sammanfattning med helhetsbedömning och antal GRÖN/GUL/RÖD, (3) klausul för klausul med klassificering och redlines, (4) förhandlingsprioriteringar, (5) källor (lag med kontrollerad lydelse, praxis med referens exakt som returnerad) och vad som inte kunnat verifieras.

Skapa en .docx om miljön kan skapa filer; annars ge hela texten i svaret.
> Claude: använd `docx`-skillen; ändringsförslag kan även levereras som spårade ändringar.

Använd typsnitt med fullt stöd för svenska tecken (å, ä, ö, é).

## Checklista före leverans

- [ ] Partsförhållande, användarens sida och avtalstyp anges (eller antagandena redovisas).
- [ ] Hela avtalet är läst; sammansatta klausuler är nedbrutna.
- [ ] Varje RÖD/GUL punkt med rättslig motivering har stöd i verktygsresultat; övriga bygger uttryckligen på affärsrisk.
- [ ] Dispositiva regler beskrivs som dispositiva.
- [ ] Inga anmärkningar på standardklausuler bara för att fylla ut.
- [ ] Redlines är exakta och har reservpositioner.
- [ ] Det framgår att granskningen är ett utkast för granskning av behörig jurist.

## Samspel med andra skills

- `iura` — sökmetod och citering.
- `juridisk-pm` — fördjupning av en omtvistad klausul.
- `nda-granskning` — fristående sekretessavtal.
- `tabellgranskning` — många avtal samtidigt.
