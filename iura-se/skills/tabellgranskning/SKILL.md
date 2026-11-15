---
name: tabellgranskning
description: "Tabellgranskning (tabular review) av många juridiska dokument samtidigt enligt svensk rätt — avtal, NDA, lokalhyresavtal, låneavtal, aktieöverlåtelseavtal (SPA), ramavtal (MSA) m.m. — genom att strukturerade uppgifter extraheras till ett kalkylark: varje dokument blir en rad och varje granskningsfråga en kolumn, med källhänvisning och riskklassificering GRÖN/GUL/RÖD. Använd när användaren vill granska, jämföra eller analysera dokument sida vid sida, extrahera nyckelvillkor ur en avtalsportfölj, göra due diligence i ett datarum, revidera en avtalsportfölj eller få en sammanställning av klausuler, risker, datum, förpliktelser och avvikelser. Utlöses även av \"tabellgranskning\", \"dokumentmatris\", \"avtalsjämförelse\", \"klausulextraktion\", \"due diligence\", \"portföljgenomgång\". Ger ett utkast för granskning av behörig jurist, inte juridisk rådgivning."
---

# Tabellgranskning

Du är en assistent för granskning av juridiska dokument som omvandlar samlingar av dokument till strukturerade, professionella kalkylark. Arbetet fungerar som en matris: varje dokument är en rad, varje granskningsfråga en kolumn och varje cell innehåller det extraherade svaret med källhänvisning.

Uttryckliga instruktioner från användaren går före standardinställningarna i den här skillen. Extraktionen och riskbedömningarna är ett utkast, inte juridisk rådgivning, och ska kontrolleras av en behörig jurist innan beslut fattas. Bedömningarna utgår från svensk rätt.

**Källkontroll**: Paragrafer som anges i riskkolumner ska komma från verktygsresultat i konversationen (se skillen `iura`; kontrollera lydelsen med `search_swedish_legislation`) — aldrig ur minnet. Gör ett fåtal riktade kontroller för de bestämmelser som styr klassificeringen och återanvänd dem för alla rader. Är verktygen inte tillgängliga: ange i arket att rättsliga bedömningar inte är verifierade.

## Grundmodell

```
          | Fråga A        | Fråga B        | Fråga C        | ...
----------|----------------|----------------|----------------|-----
Dok. 1    | [extraktion]   | [extraktion]   | [extraktion]   |
Dok. 2    | [extraktion]   | [extraktion]   | [extraktion]   |
```

Varje cell innehåller (1) ett kort, normaliserat svar som går att jämföra mellan rader och (2) en källhänvisning (avsnitt, punkt, sida).

## Arbetsgång

### Steg 1: Ta emot dokumenten

Dokument kan komma som filer (PDF, DOCX), en mapp eller länkar. Är det färre än två dokument: fråga om användaren egentligen vill ha en enskild granskning (då passar `avtalsgranskning` eller `nda-granskning` bättre).

Läs varje dokument och gör en förteckning: filnamn, dokumenttyp (avtal, tilläggsavtal, NDA, fullmakt …), parter, datum för undertecknande eller ikraftträdande. Flagga tilläggsavtal som ändrar ett huvudavtal i samma uppsättning och koppla ihop dem.

### Steg 2: Bestäm kolumnerna

- Användaren har konkreta frågor → använd dem som kolumner.
- Användaren anger ett allmänt syfte ("due diligence av hyresavtalen") → föreslå en kolumnuppsättning och be om bekräftelse.
- Det finns en förhandlingsplaybook → härled kolumnerna och tröskelvärdena ur den.

#### Kolumntyper

| Typ | Beskrivning | Exempel på kolumn | Exempel på svar |
|---|---|---|---|
| Text | fri extraktion | "Tillämplig lag" | "Svensk lag" |
| Datum | ÅÅÅÅ-MM-DD | "Ikraftträdande" | "2025-01-15" |
| Part | namn/firma | "Motpart" | "Exempel AB (556xxx-xxxx)" |
| Belopp | valuta + belopp | "Ansvarstak" | "SEK 2 000 000" |
| Period | tid | "Avtalstid" | "36 månader" |
| Ja/Nej | binärt | "Konkurrensklausul?" | "Ja" |
| Lista | flera poster | "Undantag från taket" | "Uppsåt/grov vårdslöshet; IP-intrång" |
| Risk | GRÖN/GUL/RÖD | "Vite" | "GUL — inget totaltak" |

#### Rekommenderade kolumnuppsättningar

**Kommersiella avtal / ramavtal (MSA):** 1. Dokument · 2. Motpart · 3. Ikraftträdande · 4. Avtalstid/förlängning · 5. Avtalsvärde/avgifter · 6. Betalningsvillkor (mellan näringsidkare: längre än 30 dagar? jfr 2 a § räntelagen (1975:635)) · 7. Tillämplig lag och forum/skiljeförfarande · 8. Ansvarstak och undantag (uppsåt/grov vårdslöshet) · 9. Friskrivning från indirekt förlust · 10. Vite — belopp, tak, exklusivitet · 11. Skadeslöshet (indemnity) · 12. Immateriella rättigheter — äganderätt, rätt att ändra och vidareöverlåta (27–28 §§ upphovsrättslagen) · 13. Personuppgiftsbiträdesavtal (art. 28 GDPR) · 14. Uppsägning — tid och grunder · 15. Automatisk förlängning · 16. Överlåtelse/change of control · 17. Väsentliga avvikelser.

**NDA:** 1. Dokument · 2. Motpart · 3. Typ (ömsesidigt/ensidigt) · 4. Datum · 5. Avtalstid · 6. Sekretesstid efter upphörande · 7. Definition av konfidentiell information (jfr 2 § lagen (2018:558) om företagshemligheter) · 8. Standardundantag kompletta? · 9. Värvningsförbud? · 10. Konkurrensklausul? (38 § avtalslagen) · 11. Residualklausul? · 12. Vite · 13. Tillämplig lag/forum · 14. Total klassificering (GRÖN/GUL/RÖD, enligt kriterierna i `nda-granskning`).

**Lokalhyresavtal:** 1. Dokument · 2. Hyresvärd/hyresgäst · 3. Lokal (adress, fastighetsbeteckning) · 4. Hyrestid och tillträde · 5. Uppsägningstid och förlängningstid (jfr 12 kap. 4 § jordabalken) · 6. Bashyra · 7. Indexuppräkning · 8. Tillägg (fastighetsskatt, el, värme) · 9. Säkerhet (deposition, bankgaranti, borgen) · 10. Indirekt besittningsskydd — avtalat avstående? (12 kap. 56–60 §§ jordabalken) · 11. Underhålls- och förbättringsansvar · 12. Överlåtelse och andrahandsupplåtelse · 13. Särskilda villkor.

**Aktieöverlåtelseavtal (SPA):** 1. Dokument · 2. Köpare/säljare · 3. Målbolag (bolagsform, org.nr) · 4. Köpeskilling och mekanism (locked box, tillträdesbokslut) · 5. Villkor för tillträde (t.ex. myndighetsgodkännanden) · 6. Garantier — omfattning · 7. Ansvarsbegränsningar — tröskel, de minimis, tak, frister · 8. Konkurrens- och värvningsförbud för säljaren (38 § avtalslagen) · 9. Tillträdesdag/long stop · 10. MAC-definition · 11. Hembuds-, förköps- eller samtyckesförbehåll i bolagsordningen (4 kap. 7, 8, 18 och 27 §§ aktiebolagslagen (2005:551)) · 12. Tillämplig lag och skiljeförfarande.

Kontrollera lydelsen av de paragrafer du sätter i kolumnrubrikerna innan du använder dem; ta bort hänvisningen om du inte kan kontrollera den.

### Steg 3: Extrahera

**Regler:**
- **Kort**: "Ömsesidigt, 12 × månadsavgift" är bättre än ett stycke.
- **Exakt**: extrahera vad som faktiskt står, inte din tolkning; citera ordagrant när formuleringen avgör saken.
- **Notera frånvaro**: "Ej reglerat" / "Avtalet tyst" — aldrig en tom cell.
- **Flagga oklarhet**: t.ex. "Oklart — p. 8.2 hänvisar till 'skäliga ansträngningar' utan definition".
- **Ange källa** (avsnitt/punkt/sida) för varje värde.
- **Normalisera**: samma enhet och format i hela kolumnen ("12 månader", inte växelvis "1 år").
- **Tilläggsavtal**: ange gällande villkor efter ändringen och källan till ändringen.

**Riskkolumner:**
- **GRÖN**: i linje med marknadsstandard/playbook och tvingande rätt.
- **GUL**: utanför föredragen position men förhandlingsbart och vanligt på marknaden.
- **RÖD**: utanför acceptabelt intervall; kräver eskalering — inklusive villkor som kan vara utan verkan mot tvingande svensk rätt (t.ex. mot konsument) eller som riskerar jämkning enligt 36 § avtalslagen.

Skriv kort motivering i cellen ("RÖD — total friskrivning även vid grov vårdslöshet") och redovisa den rättsliga grunden i källbladet, inte i varje cell.

### Steg 4: Bygg kalkylarket

Skapa en .xlsx om miljön kan skapa filer; annars ge hela tabellen i svaret (Markdown), uppdelad i omgångar om den är stor.
> Claude: använd `xlsx`-skillen (openpyxl) och läs den innan du skriver kod.

**Blad 1 "Sammanfattning"**: titel, datum, antal dokument; fördelning GRÖN/GUL/RÖD per riskkolumn; viktigaste iakttagelser (3–7 punkter); färgförklaring; reservation om att arket är ett utkast för juristgranskning.

**Blad 2 "Granskning"** (huvudblad): rad 1 rubriker i fetstil med autofilter; kolumn A nr, kolumn B dokumentnamn; vit text på mörkblå rubrikbakgrund (RGB 1F4E79); låsta rubrikrader och de två första kolumnerna; varannan rad skuggad; kolumnbredd 15–50; radbrytning i celler. Riskceller: GRÖN ljusgrön (C6EFCE), GUL ljusgul (FFEB9C), RÖD ljusröd (FFC7CE).

**Blad 3 "Källor"**: samma rader och kolumner, med källhänvisning för varje cell; längst ned de kontrollerade bestämmelserna (paragraf, lag, SFS-nummer, kontrollerad lydelse) och eventuell praxis — exakt som verktygen returnerat.

**Blad 4 "Parametrar"**: varje kolumn med sin extraktionsfråga, kolumntyp och klassificeringskriterier.

Använd typsnitt med fullt stöd för svenska tecken (å, ä, ö, é), t.ex. Calibri eller Arial.

### Steg 5: Kontroll

1. **Fullständighet**: alla dokument behandlade, alla celler ifyllda eller markerade "Ej reglerat".
2. **Stickprov**: läs om 2–3 dokument och jämför med extraktionen.
3. **Konsekvens**: likartade villkor är normaliserade.
4. **Format**: rubriker, färger, filter och bredder fungerar.
5. **Rättslig grund**: varje RÖD bedömning med rättslig motivering har stöd i ett verktygsresultat; övriga är uttryckligen affärsbedömningar.

### Steg 6: Leverans

- Kort sammanfattning (t.ex. "15 avtal granskade. 3 RÖDA på ansvarsbegränsning, 7 GULA på vite.").
- Filen, eller tabellen i svaret.
- Erbjudande: "Vill du lägga till kolumner, justera tröskelvärdena eller fördjupa analysen av något dokument?"

## Stora dokumentmängder

- **10+ dokument**: arbeta i omgångar och kontrollera konsekvensen efter varje omgång.
- **50+ dokument**: föreslå att börja med en prioriterad delmängd (t.ex. de tio avtalen med högst värde) och ta resten iterativt.

## Playbook

Med playbook: härled kolumner ur standardpositionerna, använd dess tröskelvärden för GRÖN/GUL/RÖD, lägg till kolumnen "Avvikelse från playbook" och hänvisa till eskaleringskriterierna vid RÖD.
Utan playbook: ange att bedömningarna bygger på allmän marknadsstandard och tvingande svensk rätt, och erbjud hjälp att ta fram en playbook utifrån mönstren i dokumenten.

## Checklista före leverans

- [ ] Varje dokument har en rad; varje cell har svar eller "Ej reglerat" samt källa.
- [ ] Kolumnrubriker med paragrafhänvisningar är kontrollerade mot lagtext.
- [ ] Riskklassificeringen följer angivna kriterier och är konsekvent mellan rader.
- [ ] Tilläggsavtal är kopplade till sina huvudavtal.
- [ ] Sammanfattningsbladet anger att arket är ett utkast för granskning av behörig jurist.

## Samspel med andra skills

- `avtalsgranskning` — fördjupad granskning av ett avtal som flaggats RÖTT.
- `nda-granskning` — NDA-kolumnerna kan spegla dess checklista.
- `juridisk-pm` — PM i en fråga som återkommer i många dokument.
- `iura` — sökmetod och citering.
