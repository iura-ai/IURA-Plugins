---
name: pozew-cywilny
description: >
  Generowanie pozwów w postępowaniu cywilnym — precyzyjnie skonstruowany akt
  prawniczej argumentacji z pełną subsumpcją, warstwową argumentacją
  i antycypowaniem zarzutów strony przeciwnej.
---

# Generowanie pozwów w postępowaniu cywilnym

## Filozofia skilla

Pozew to najważniejsze pismo procesowe — od jego jakości zależy wynik sprawy. Skuteczny pozew nie jest prostym opisem zdarzeń z żądaniem, lecz precyzyjnie skonstruowanym aktem prawniczej argumentacji, w którym każde twierdzenie faktyczne jest powiązane z normą prawną i poparte dowodem. Celem tego skilla jest generowanie pozwów o jakości dorównującej pracy doświadczonego radcy prawnego — z pełną subsumpcją, warstwową argumentacją i antycypowaniem zarzutów strony przeciwnej.

Kluczowa zasada: **nigdy nie ograniczaj długości generowanego pozwu**. Pozew ma być tak wyczerpujący, jak wymaga tego sprawa. Lepiej napisać za dużo niż pominąć argument, który mógłby przesądzić o wyniku.

---

## Faza 0: Zebranie informacji od użytkownika

Zanim zaczniesz cokolwiek pisać, musisz zebrać kompletny stan faktyczny. Użyj narzędzia AskUserQuestion, aby uzyskać następujące informacje (dostosuj pytania do typu sprawy):

### Informacje obowiązkowe:

1. **Strony postępowania:**
   - Dane powoda: imię, nazwisko/firma, adres, PESEL/KRS/NIP, status (konsument, przedsiębiorca, osoba prawna)
   - Dane pełnomocnika (jeśli jest): imię, nazwisko, tytuł zawodowy (radca prawny/adwokat), adres kancelarii, email, telefon
   - Dane pozwanego: nazwa/imię nazwisko, adres/siedziba, KRS/NIP

2. **Stan faktyczny** — co się wydarzyło, kiedy, jakie dokumenty istnieją, jakie działania podjęły strony

3. **Czego dotyczy roszczenie** — zapłata, ustalenie, odszkodowanie, zadośćuczynienie, wydanie rzeczy, inne

4. **Kwota roszczenia** (jeśli majątkowe) lub opis żądania niemajątkowego

5. **Czy podjęto próbę mediacji/pozasądowego rozwiązania sporu** (wymóg z art. 187 § 1 pkt 4 KPC)

6. **Czy wysłano wezwanie do zapłaty/wezwanie przedsądowe** i kiedy

7. **Jakie dowody posiada powód** (dokumenty, świadkowie, nagrania, korespondencja)

8. **Data wymagalności roszczenia** (od kiedy roszczenie jest wymagalne — art. 187 § 1 pkt 2 KPC)

Jeśli użytkownik nie poda wszystkich danych, oznacz brakujące jako „…" (wielokropek) w pozwie — to standardowa praktyka przy draftach.

---

## Faza 1: Badanie prawne (OBOWIĄZKOWE)

Po zebraniu stanu faktycznego, ZANIM zaczniesz pisać pozew, MUSISZ przeprowadzić badanie prawne przy użyciu narzędzi IuraMCP. To nie jest opcjonalne — pozew bez aktualnych podstaw prawnych i orzecznictwa jest bezwartościowy.

### Strategia wyszukiwania:

Wykonaj **równoległe** zapytania do minimum 3-4 z poniższych narzędzi (dobierz do typu sprawy):

**Search_DU** (Dziennik Ustaw) — zawsze:
- Przepisy materialnoprawne stanowiące podstawę roszczenia (np. art. 471 KC dla odpowiedzialności kontraktowej, art. 415 KC dla deliktowej, art. 405/410 KC dla bezpodstawnego wzbogacenia)
- Przepisy procesowe: art. 126, 187 KPC (wymogi formalne), art. 189 KPC (jeśli powództwo o ustalenie)
- Przepisy szczególne właściwe dla danej dziedziny (prawo bankowe, ustawa o ochronie konsumentów, prawo pracy, kodeks spółek handlowych, itp.)
- Przepisy o kosztach sądowych (ustawa o kosztach sądowych w sprawach cywilnych — art. 13, 13a)
- Przepisy o przedawnieniu (art. 117-125 KC)
- Przepisy o właściwości sądu (art. 16-17, 27-39 KPC)
- Ustaw parametr `in_force_as_of` na bieżącą datę

**Search_SN** (Sąd Najwyższy) — zawsze:
- Orzecznictwo dotyczące kluczowej instytucji prawnej roszczenia
- Uchwały SN rozstrzygające wątpliwości interpretacyjne
- Wyroki dotyczące podobnych stanów faktycznych

**Search_SP** (sądy powszechne) — zalecane:
- Linia orzecznicza sądów niższych instancji w analogicznych sprawach
- Praktyka orzecznicza w danym rejonie/apelacji

**Search_CBOSA** (sądy administracyjne) — jeśli sprawa ma wątek administracyjnoprawny

**Search_TK** (Trybunał Konstytucyjny) — jeśli sprawa dotyczy konstytucyjności przepisu

### Co wyciągasz z badania:

Dla każdego znalezionego źródła zanotuj:
- **Przepis**: pełne brzmienie artykułu z oznaczeniem aktu (np. „art. 385¹ § 1 KC")
- **Orzeczenie**: sygnaturę, datę, kluczową tezę, sąd (np. „wyrok SN z 15.01.2023 r., II CSKP 212/22")
- **Zasadę prawną**: jaką regułę orzeczenie ustanawia
- **Zastosowanie**: jak ten przepis/orzeczenie wspiera argumentację powoda

---

## Faza 2: Konstrukcja strategii procesowej

Na podstawie stanu faktycznego i wyników badania prawnego, przed pisaniem pozwu, opracuj strategię:

### 2.1 Dobór podstawy prawnej roszczenia

Zidentyfikuj WSZYSTKIE możliwe podstawy prawne i ułóż je hierarchicznie:

- **Roszczenie główne** — najmocniejsza podstawa prawna
- **Roszczenie ewentualne** (alternatywne) — na wypadek gdyby sąd nie podzielił głównej argumentacji
- Rozważ czy istnieje zbieg roszczeń (kontraktowa + deliktowa, condictio + odszkodowanie)

Zastosuj następujący **wzorzec hierarchicznej struktury żądań**:

```
ROSZCZENIE GŁÓWNE (najsilniejsza podstawa):
na podst. art. 187 § 1 pkt 1) k.p.c. w zw. z art. [X] k.c. wnoszę o [żądanie];

ROSZCZENIE EWENTUALNE (na wypadek nieuwzględnienia głównego):
ewentualnie, w przypadku [warunek]:
na podst. art. 187 § 1 pkt 1) k.p.c. w zw. z art. [Y] k.c. wnoszę o [żądanie alternatywne];

W KAŻDYM PRZYPADKU (niezależnie od wyniku powyższych):
na podst. art. 98 § 1 i § 1¹ k.p.c. wnoszę o zasądzenie kosztów postępowania...
```

### 2.2 Struktura argumentacji (subsumpcja warstwowa)

Dla każdego roszczenia przygotuj łańcuch subsumpcji. Stosuj **wzorzec subsumpcji pełnej (klasyczny sylogizm prawniczy)**:

```
NORMA: Zgodnie z art. [X] [aktu prawnego], [treść normy rozłożona na przesłanki].
Dla powstania [skutku prawnego] konieczne jest zatem łączne spełnienie następujących przesłanek:
(1) [przesłanka 1], (2) [przesłanka 2], (3) [przesłanka N].

AD. (1) [PRZESŁANKA 1]:
[Opis stanu faktycznego odpowiadającego przesłance].
Dowód: [wskazanie dowodu]
[Opcjonalnie: orzecznictwo potwierdzające spełnienie przesłanki]
Przesłanka spełniona.

AD. (2) [PRZESŁANKA 2]:
[Analogicznie]

KONKLUZJA: Skoro wszystkie przesłanki z art. [X] zostały spełnione, [skutek prawny]
zachodzi w niniejszej sprawie. [Strona Pozwana jest zatem zobowiązana do / Strona Powodowa
jest uprawniona do...]
```

Każdy argument budowany jest jako pięcioelementowy łańcuch:

```
TEZA → NORMA PRAWNA → SUBSUMPCJA → ORZECZNICTWO → KONKLUZJA
```

### 2.3 Antycypowanie zarzutów pozwanego

Przemyśl, jakie zarzuty może podnieść strona przeciwna, i przygotuj prewencyjne odparcie. Stosuj **wzorzec prewencyjnego odparcia zarzutów**:

```
Uprzedzając spodziewaną argumentację Strony Pozwanej, jakoby [opis
przewidywanego zarzutu], wskazać należy, że argumentacja ta jest
oczywiście bezzasadna.

Po pierwsze, [argument 1 odparcia — np. literalna wykładnia przepisu].
Po drugie, [argument 2 — np. orzecznictwo odrzucające taką argumentację].
Po trzecie, [argument 3 — np. ratio legis przepisu sprzeciwia się takiej wykładni].

W konsekwencji, nawet gdyby Strona Pozwana podniosła powyższy zarzut,
nie zasługiwałby on na uwzględnienie.
```

Typowe zarzuty do antycypowania:
- Zarzut przedawnienia → argumentacja o początku biegu terminu
- Zarzut przyczynienia się powoda → dlaczego nie zachodzi
- Zarzut potrącenia → dlaczego nieskuteczny
- Zarzut braku legitymacji → dlaczego powód jest uprawniony
- Zarzuty specyficzne dla danego typu sprawy

---

## Faza 3: Generowanie pozwu — STRUKTURA DOKUMENTU

Pozew generuj jako plik .docx przy użyciu skilla docx (npm docx-js). Zastosuj poniższą strukturę — KAŻDA sekcja jest obowiązkowa (chyba że wprost oznaczono inaczej).

### NAGŁÓWEK DOKUMENTU

```
[Miejscowość], dnia [data] r.

Sąd:                           Sąd [Rejonowy/Okręgowy] w [miasto]
                               [Wydział] Wydział Cywilny
                               Ul. [adres sądu]

Strona Powodowa:               [imię i nazwisko / firma]
                               [adres]
                               PESEL: [numer] / KRS: [numer]
                               e-mail: [email]

                               reprezentowany/-a przez:
                               [tytuł zawodowy] [imię nazwisko]
                               e-mail pełnomocnika: [email]
                               tel. pełnomocnika: [tel]
                               adres dla doręczeń: [adres kancelarii]

Strona Pozwana:                [nazwa / imię nazwisko]
                               [adres / siedziba]
                               KRS: [numer] / NIP: [numer]

Wartość przedmiotu sporu:      [kwota] zł (słownie: [kwota słownie])
```

**Zasady doboru sądu:**
- Sąd rejonowy: WPS ≤ 100.000 zł (art. 16 KPC) — chyba że sprawa należy do właściwości sądu okręgowego z art. 17 KPC
- Sąd okręgowy: WPS > 100.000 zł lub sprawa z art. 17 KPC
- Właściwość miejscowa ogólna: sąd miejsca zamieszkania/siedziby pozwanego (art. 27 KPC)
- Właściwość przemienna: np. sąd miejsca wykonania umowy (art. 34 KPC), sąd miejsca zamieszkania powoda w sprawach z czynności bankowych (art. 37² KPC)

### TYTUŁ

```
POZEW
o [zapłatę / ustalenie / zapłatę i ustalenie / odszkodowanie / ...]
```

### PETITUM (żądania)

Zacznij zawsze od formuły otwierającej:

> Działając w imieniu Strony Powodowej, na podst. pełnomocnictwa przedkładanego w załączeniu, niniejszym:

Lub jeśli powód działa sam:

> Niniejszym:

Następnie sformułuj żądania w następujący sposób:

**A. Roszczenie główne:**

> na podst. art. 187 § 1 pkt 1) k.p.c. w zw. z art. [podstawa materialnoprawna] wnoszę o zasądzenie od [pozwany] na rzecz [powód] kwoty: [kwota] zł (słownie: [słownie]), wraz z odsetkami ustawowymi za opóźnienie liczonymi od dnia [data wymagalności] r. do dnia zapłaty;

**B. Roszczenie ewentualne** (jeśli jest — wprowadź słowem „ewentualnie"):

> ewentualnie, w przypadku [warunek]:
> na podst. art. 187 § 1 pkt 1) k.p.c. w zw. z art. [alternatywna podstawa] wnoszę o [żądanie alternatywne];

**C. Roszczenie o ustalenie** (jeśli dotyczy — art. 189 KPC):

> na podst. art. 187 § 1 pkt 1) k.p.c. w zw. z art. 189 k.p.c. wnoszę o ustalenie [istnienia/nieistnienia] stosunku prawnego [opis stosunku] wynikającego z [dokument/umowa];

**D. Koszty procesu** (zawsze):

> na podst. art. 98 § 1 i § 1¹ k.p.c. wnoszę o zasądzenie od [pozwany] na rzecz [powód] zwrotu kosztów postępowania, wraz z odsetkami ustawowymi za opóźnienie liczonymi od dnia uprawomocnienia się orzeczenia do dnia zapłaty, w tym kosztów zastępstwa procesowego według norm przepisanych [ewentualnie: w wysokości dwukrotności norm przepisanych — uzasadnij nakładem pracy i złożonością sprawy] oraz opłat skarbowych od pełnomocnictw w wysokości [kwota] zł;

### WNIOSKI PROCESOWE

Po petitum, wnioski na podstawie art. 187 § 2 KPC:

**Wnioski dowodowe** — na podst. art. 235¹ k.p.c.:

> na podst. art. 235¹ k.p.c. wnoszę o dopuszczenie i przeprowadzenie dowodów z:

Dla każdego dowodu podaj:
1. Rodzaj dowodu (dokument, zeznania, opinia biegłego)
2. Cel dowodowy: „na fakty: [wyliczenie faktów do udowodnienia]"

Stosuj **wzorzec dowodowy (evidence anchoring)** — każde twierdzenie faktyczne kotwicz dowodem:

```
[Twierdzenie faktyczne].

Dowód:
- [dokument 1]
- [dokument 2]
- przesłuchanie Strony Powodowej

[Opcjonalnie — dowód warunkowy:]
Ewentualnie, na wypadek skutecznego zakwestionowania przez Stronę Pozwaną
[okoliczności], wnoszę o dopuszczenie dowodu z opinii biegłego sądowego
z zakresu [dziedzina] na fakty: [lista faktów].
```

Przykład struktury dowodowej w petitum:
```
1) dołączonych do Pozwu dokumentów, wskazanych w treści Uzasadnienia przy
   oznaczeniu „Dowód:", na fakty wskazane każdorazowo przy danym dowodzie;

2) przesłuchania Stron, ograniczonego do przesłuchania Strony Powodowej,
   na fakty: [lista faktów];

3) ewentualnie, na wypadek skutecznego zakwestionowania przez Stronę Pozwaną
   przedstawionych wyliczeń — opinii biegłego sądowego z zakresu [dziedzina],
   na fakty: [lista faktów];
```

**Wnioski organizacyjne** (opcjonalnie, ale zalecane):
- Wniosek o rozpoznanie sprawy w trybie zdalnym (art. 151 § 2 KPC)
- Wniosek o rozpoznanie sprawy pod nieobecność powoda
- Wniosek o zobowiązanie pozwanego do przedłożenia dokumentów (art. 187 § 2 pkt 3 KPC)
- Wniosek o zobowiązanie pozwanego do ustosunkowania się do twierdzeń (art. 205³ KPC)

### OŚWIADCZENIA PROCESOWE

Sekcja obowiązkowa, zawiera:

1. **Oświadczenie o mediacji** (art. 187 § 1 pkt 4 KPC):
   > oświadczam, że Strona Powodowa [podjęła / nie podjęła] próby mediacji/pozasądowego rozwiązania sporu [opis: wezwanie do zapłaty z dnia…, odpowiedź pozwanego / brak odpowiedzi]

2. **Oświadczenie o wezwaniu do zapłaty**:
   > oświadczam, że pismem z dnia [data] Strona Powodowa wezwała Stronę Pozwaną do [zapłaty/spełnienia świadczenia], wyznaczając [termin]. Strona Pozwana [nie odpowiedziała / odmówiła].

3. **Opłata sądowa**:
   > oświadczam, że wysokość opłaty sądowej od niniejszego Pozwu wynika z treści art. [13/13a/26/inne] ustawy o kosztach sądowych w sprawach cywilnych i wynosi [kwota] zł.

4. **Właściwość sądu**:
   > oświadczam, że niniejszy Sąd jest właściwy na podstawie art. [numer] k.p.c. (miejscowo) oraz na podstawie art. [16/17] § [1] k.p.c. (rzeczowo).

5. **Wymagalność roszczenia** (art. 187 § 1 pkt 2 KPC):
   > oświadczam, że roszczenie Strony Powodowej stało się wymagalne w dniu [data], gdyż [uzasadnienie: upływ terminu płatności / doręczenie wezwania + upływ terminu / inne zdarzenie].

---

### UZASADNIENIE

To serce pozwu. Uzasadnienie składa się z następujących części, w tej kolejności:

#### I. STAN FAKTYCZNY

Przedstaw fakty chronologicznie, z następującymi zasadami:

1. **Każde twierdzenie faktyczne natychmiast popieraj dowodem** (evidence anchoring):
   > W dniu [data] Strona Powodowa zawarła ze Stroną Pozwaną umowę [typ umowy] nr [numer].
   >
   > Dowód:
   > - Umowa z dnia [data]
   > - przesłuchanie Strony Powodowej

2. **Używaj precyzyjnego języka prawniczego** — nie „podpisał umowę" lecz „zawarł umowę"; nie „nie zapłacił" lecz „nie spełnił świadczenia pieniężnego"

3. **Buduj narrację od ogółu do szczegółu:**
   - Kontekst zawarcia stosunku prawnego
   - Treść istotnych postanowień
   - Przebieg wykonywania zobowiązań
   - Moment powstania sporu
   - Działania podjęte przed wniesieniem pozwu

4. **Ustal status stron** — jeśli powód jest konsumentem, wyraźnie to zaznacz, bo otwiera to ochronę z art. 385¹ KC i Dyrektywy 93/13/EWG:
   > Strona Powodowa zawarła ww. umowę działając w charakterze konsumenta w rozumieniu art. 22¹ k.c., tj. dokonując czynności prawnej niezwiązanej bezpośrednio z jej działalnością gospodarczą lub zawodową.

#### II. ARGUMENTACJA PRAWNA — METODA SUBSUMPCJI WARSTWOWEJ

To najważniejsza część pozwu. Stosuj metodę **subsumpcji warstwowej** — każdy argument budowany jest jako łańcuch:

```
TEZA → NORMA PRAWNA → SUBSUMPCJA → ORZECZNICTWO → KONKLUZJA
```

**Krok 1: Sformułuj tezę prawną** — co chcesz udowodnić w danej sekcji

> Klauzula [opis] zawarta w § [X] Umowy stanowi niedozwolone postanowienie umowne w rozumieniu art. 385¹ § 1 k.c.

**Krok 2: Przypomnij normę prawną** — zacytuj lub sparafrazuj przepis

> Zgodnie z art. 385¹ § 1 k.c., postanowienia umowy zawieranej z konsumentem nieuzgodnione indywidualnie nie wiążą go, jeżeli kształtują jego prawa i obowiązki w sposób sprzeczny z dobrymi obyczajami, rażąco naruszając jego interesy. Dla uznania postanowienia za niedozwolone muszą zatem zostać spełnione łącznie następujące przesłanki: (1) umowa zawarta z konsumentem, (2) postanowienie nieuzgodnione indywidualnie, (3) kształtowanie praw i obowiązków sprzecznie z dobrymi obyczajami, (4) rażące naruszenie interesów konsumenta.

**Krok 3: Dokonaj subsumpcji** — przyporządkuj fakty do każdej przesłanki

> Ad. (1) Status konsumenta: Jak wskazano w części Stan Faktyczny, Strona Powodowa zawarła Umowę w celach niezwiązanych z działalnością gospodarczą (Dowód: przesłuchanie Strony Powodowej). Przesłanka spełniona.
>
> Ad. (2) Brak indywidualnego uzgodnienia: Umowa została zawarta na wzorcu stosowanym przez Stronę Pozwaną. Strona Powodowa mogła jedynie zaakceptować zaproponowane warunki; w innej sytuacji — przy braku akceptacji — nie doszłoby do zawarcia Umowy (Dowód: przesłuchanie Strony Powodowej, wzorzec umowy). Zgodnie z art. 385¹ § 3 k.c. nieuzgodnione indywidualnie są te postanowienia umowy, na których treść konsument nie miał rzeczywistego wpływu. Ciężar dowodu, że postanowienie zostało uzgodnione indywidualnie, spoczywa na Stronie Pozwanej (art. 385¹ § 4 k.c.). Przesłanka spełniona.
>
> [analogicznie dla pozostałych przesłanek]

**Krok 4: Wzmocnij orzecznictwem** — cytuj orzeczenia uzyskane z IuraMCP

Stosuj **wzorce integracji orzecznictwa** — dobierz odpowiedni wzorzec do kontekstu:

*Orzeczenie jako potwierdzenie tezy:*
> Powyższe stanowisko znajduje potwierdzenie w orzecznictwie Sądu Najwyższego. W wyroku z dnia [data] r. (sygn. akt [sygnatura]) Sąd Najwyższy wskazał, że „[cytat z tezy orzeczenia]". Przenosząc powyższe rozważania na grunt niniejszej sprawy, nie ulega wątpliwości, że [zastosowanie do konkretnego stanu faktycznego].

*Orzeczenie TSUE jako wykładnia prounijna:*
> W kontekście prounijnej wykładni prawa krajowego wskazać należy na wyrok Trybunału Sprawiedliwości Unii Europejskiej z dnia [data] r. w sprawie [C-XXX/XX], w którym Trybunał orzekł, że „[cytat]". Z powyższego judykatu wynika zatem, że [zasada prawna], co w niniejszej sprawie oznacza [zastosowanie].

*Spójna linia orzecznicza:*
> Stanowisko to jest konsekwentnie prezentowane w orzecznictwie — por. wyrok SN z [data] r., sygn. [X]; wyrok SN z [data] r., sygn. [Y]; wyrok SA w [miasto] z [data] r., sygn. [Z]. W żadnym z przywołanych orzeczeń sąd nie zakwestionował [tezy], co potwierdza ugruntowany charakter prezentowanej wykładni.

**Krok 5: Sformułuj konkluzję cząstkową**

> W świetle powyższego nie ulega wątpliwości, że sporna klauzula stanowi niedozwolone postanowienie umowne, które nie wiąże Strony Powodowej.

---

### Wzorce fraz przejściowych między argumentami:

| Funkcja | Frazy |
|---------|-------|
| Wprowadzenie argumentu głównego | „W pierwszym rzędzie wskazać należy, że…", „Fundamentalne znaczenie ma…" |
| Przejście do kolejnego argumentu | „Dalej wskazać należy, że…", „Niezależnie od powyższego…", „Ponadto…" |
| Wzmocnienie argumentu | „Powyższe stanowisko znajduje potwierdzenie w…", „Warto w tym miejscu przywołać…" |
| Konkluzja cząstkowa | „W świetle powyższego…", „Z powyższego wynika zatem…", „Prowadzi to do jednoznacznego wniosku…" |
| Subsumpcja | „Skoro zatem…", „Przenosząc powyższe rozważania na grunt niniejszej sprawy…" |
| Antycypowanie zarzutu | „Uprzedzając spodziewaną argumentację Strony Pozwanej…", „Na marginesie, nawet gdyby Strona Pozwana podniosła zarzut…" |
| Argument a contrario | „A contrario…", „Wprost przeciwnie…" |
| Argument z celu przepisu | „Celem tego przepisu jest…", „Ratio legis omawianej regulacji sprowadza się do…" |
| Argument z hierarchii źródeł | „W kontekście prounijnej wykładni prawa krajowego…" |
| Pewność | „prowadzi do jednoznacznego wniosku", „nie ulega wątpliwości", „oczywistym jest" |
| Ostrożna teza | „w ocenie Strony Powodowej", „jak się wydaje", „zasadne jest twierdzenie" |

---

### Hierarchia źródeł prawa w argumentacji:

Przy budowaniu argumentacji przestrzegaj następującej hierarchii cytowania:

1. **Prawo UE** (jeśli sprawa ma wymiar unijny): Traktaty, Dyrektywy, Rozporządzenia → wyroki TSUE → opinie Rzeczników Generalnych
2. **Konstytucja RP** (jeśli sprawa dotyczy praw konstytucyjnych) → wyroki TK
3. **Ustawy polskie** (KC, KPC, ustawy szczególne) → uchwały SN → wyroki SN → wyroki sądów apelacyjnych → wyroki sądów okręgowych
4. **Doktryna** (komentarze, monografie) — jako uzupełnienie, nie jako samodzielna podstawa

---

### Techniki argumentacyjne do zastosowania:

**1. Sylogizm prawniczy** (obowiązkowy dla każdego roszczenia):
```
Przesłanka większa: Norma prawna (art. X stanowi, że jeśli A i B, to C)
Przesłanka mniejsza: Stan faktyczny (w niniejszej sprawie zachodzi A i B)
Wniosek: Konsekwencja prawna (zatem zachodzi C)
```

**2. Argument z precedensu** — pokaż spójność linii orzeczniczej:
> Stanowisko to jest konsekwentnie prezentowane w orzecznictwie — por. wyrok SN z [data], sygn. [X]; wyrok SA w [miasto] z [data], sygn. [Y]; wyrok SO w [miasto] z [data], sygn. [Z].

**3. Argument teleologiczny** — odwołaj się do celu regulacji. Stosuj **wzorzec argumentu z celu przepisu**:

```
Celem art. [X] jest [opis celu regulacji — np. ochrona konsumenta jako
strony słabszej stosunku prawnego]. Jak wskazał Sąd Najwyższy w [orzeczeniu],
wymóg [opis wymogu] musi podlegać wykładni rozszerzającej, gdyż tylko taka
interpretacja realizuje ratio legis omawianej regulacji. Wąska wykładnia,
na którą mogłaby powoływać się Strona Pozwana, prowadziłaby do
zniweczenia ochronnego celu przepisu.
```

**4. Argument systemowy** — pokaż spójność z innymi przepisami. Stosuj **wzorzec argumentu z wykładni systemowej**:

```
Wykładnia ta jest spójna z systematyką [aktu prawnego]. Art. [X] stanowi,
że [treść], natomiast art. [Y] przewiduje, że [treść]. Czytane łącznie,
przepisy te tworzą spójny mechanizm [opis mechanizmu]. Przyjęcie odmiennej
interpretacji prowadziłoby do wewnętrznej sprzeczności systemu prawa,
gdyż [opis sprzeczności].
```

**5. Argument komparatystyczny** — porównanie z innymi jurysdykcjami (opcjonalnie, wzmacniająco):
> Warto zauważyć, że analogiczne rozwiązanie przyjęto w [jurysdykcja], gdzie [opis rozwiązania].

**6. Prewencyjne odparcie zarzutów** — antycypuj argumenty pozwanego:
> Uprzedzając spodziewaną argumentację Strony Pozwanej, jakoby [opis zarzutu], wskazać należy, że argumentacja ta jest bezzasadna, albowiem [odparcie]. Potwierdza to [orzecznictwo/przepis].

---

#### III. SEKCJE TEMATYCZNE UZASADNIENIA

W zależności od typu sprawy, uzasadnienie powinno zawierać odpowiednie sekcje. Typowe sekcje (adaptuj do sprawy):

**Dla spraw o zapłatę:**
- Stan faktyczny
- Podstawa prawna roszczenia (subsumpcja)
- Wysokość roszczenia (kalkulacja)
- Odsetki (podstawa prawna, termin wymagalności)
- Przedawnienie (dlaczego roszczenie nie jest przedawnione)
- Koszty zastępstwa procesowego

**Dla spraw konsumenckich (np. kredyty, umowy adhezyjne):**
- Stan faktyczny
- Naruszenie obowiązków informacyjnych
- Niedozwolone postanowienia umowne (analiza klauzula po klauzuli z subsumpcją)
- Skutki abuzywności (nieważność/bezskuteczność)
- Zwrot nienależnego świadczenia (art. 405 w zw. z art. 410 KC)
- Interes prawny w ustaleniu (jeśli roszczenie o ustalenie — art. 189 KPC)
- Przedawnienie
- Koszty zastępstwa procesowego

**Dla spraw odszkodowawczych:**
- Stan faktyczny
- Odpowiedzialność pozwanego (deliktowa art. 415+ KC / kontraktowa art. 471+ KC)
- Szkoda (damnum emergens + lucrum cessans)
- Związek przyczynowy (adekwatny — art. 361 § 1 KC)
- Przyczynienie się poszkodowanego (prewencyjnie odeprzeć — art. 362 KC)
- Wysokość odszkodowania
- Przedawnienie
- Koszty

---

#### IV. ZWROT NIENALEŻNEGO ŚWIADCZENIA (jeśli dotyczy)

Jeśli roszczenie opiera się na art. 405 w zw. z art. 410 KC, zastosuj następujący **wzorzec obliczenia nienależnego świadczenia**:

```
ZWROT NIENALEŻNEGO ŚWIADCZENIA

Na podst. art. 410 § 1 k.c. w zw. z art. 405 k.c., Strona Pozwana
jest zobowiązana do zwrotu świadczenia nienależnie uzyskanego od Strony
Powodowej.

Świadczenie Strony Powodowej jest nienależne, albowiem [wybrać odpowiednią
condictio z art. 410 § 2 k.c.]:
- czynność prawna zobowiązująca do świadczenia była nieważna (condictio sine causa), lub
- podstawa świadczenia odpadła (condictio causa finita), lub
- Strona Powodowa nie była w ogóle zobowiązana (condictio indebiti).

Obliczenie kwoty roszczenia:
[Transparentny wzór matematyczny, np.:]
Kwota nienależnego świadczenia = Suma wpłat dokonanych przez Stronę Powodową
([kwota]) minus suma świadczeń, do których Strona Powodowa była rzeczywiście
zobowiązana ([kwota]) = [kwota roszczenia].

Dowód:
- zestawienie wpłat / harmonogram spłat
- historia rachunku bankowego
- [ewentualnie] opinia biegłego
```

Schemat argumentacyjny:

1. **Ustal przesłanki**: świadczenie spełnione bez podstawy prawnej (condictio indebiti), odpadnięcie podstawy (condictio causa finita), nieważność czynności prawnej (condictio sine causa)
2. **Kalkulacja**: pokaż transparentnie sposób obliczenia kwoty roszczenia — podaj wzór matematyczny, odwołaj się do zestawień spłat / faktur / potwierdzeń
3. **Teoria dwóch kondykcji vs. teoria salda**: jeśli relewantne, zajmij stanowisko (w polskim orzecznictwie SN preferuje teorię dwóch kondykcji — por. uchwała SN z 16.02.2021, III CZP 11/20)

---

#### V. INTERES PRAWNY W USTALENIU (jeśli jest roszczenie z art. 189 KPC)

Stosuj **wzorzec interesu prawnego**:

```
INTERES PRAWNY W USTALENIU

W orzecznictwie oraz doktrynie przyjmuje się, że interes prawny w rozumieniu
art. 189 k.p.c. istnieje wówczas, gdy zachodzi niepewność stanu prawnego
lub prawa, powodująca potrzebę ochrony prawnej. Niepewność ta musi mieć
charakter obiektywny, tj. musi istnieć na podstawie rozumnej oceny sytuacji,
w której powód występuje z powództwem o ustalenie.

W niniejszej sprawie interes prawny Strony Powodowej wyraża się w tym, że:

1. Między Stronami istnieje [długoterminowy / trwający] stosunek prawny
   wynikający z [umowy/decyzji/innego źródła], którego ważność/treść jest sporna.

2. Samo powództwo o zapłatę nie zapewniłoby Stronie Powodowej pełnej ochrony
   prawnej, gdyż [roszczenie o zapłatę dotyczy świadczeń już spełnionych,
   podczas gdy stosunek prawny generuje dalsze zobowiązania na przyszłość /
   inne uzasadnienie].

3. Prawomocne ustalenie [nieistnienia/istnienia] stosunku prawnego zapobiegnie
   przyszłym sporom między Stronami i definitywnie rozstrzygnie kwestię
   [opis kwestii].
```

Schemat argumentacyjny:

1. **Definicja**: interes prawny istnieje, gdy zachodzi obiektywna niepewność stanu prawnego wymagająca ochrony
2. **Niepewność**: opisz, na czym polega niepewność (np. długoterminowy stosunek prawny, którego ważność jest kwestionowana)
3. **Ochrona**: wyjaśnij, dlaczego samo powództwo o zapłatę nie zapewnia pełnej ochrony (np. roszczenie o zapłatę dotyczy przeszłości, a stosunek trwa nadal)
4. **Prewencja**: ustalenie zapobiegnie przyszłym sporom między stronami

---

#### VI. PRZEDAWNIENIE

Zawsze odnieś się do kwestii przedawnienia — nawet jeśli jest oczywiste, że roszczenie nie jest przedawnione. Pokaż sądowi, że kontrolujesz tę kwestię. Stosuj **wzorzec argumentacji o przedawnieniu**:

```
TERMIN PRZEDAWNIENIA

Roszczenie Strony Powodowej podlega [X]-letniemu terminowi przedawnienia,
zgodnie z art. [118/inne] k.c.

Kluczową kwestią jest ustalenie momentu, od którego bieg przedawnienia
się rozpoczyna. Zgodnie z art. 120 § 1 k.c., bieg przedawnienia rozpoczyna
się od dnia, w którym roszczenie stało się wymagalne.

[Jeśli sprawa konsumencka:]
W orzecznictwie TSUE konsekwentnie przyjmuje się, że termin przedawnienia
roszczenia konsumenta nie może rozpoczynać biegu, dopóki konsument nie miał
realnej możliwości dowiedzenia się o nieuczciwym charakterze warunku umownego
(por. wyrok TSUE z [data] w sprawie [C-XXX/XX]).

W niniejszym przypadku momentem, w którym Strona Powodowa powzięła wiedzę
o [wadliwości/nieuczciwości] jest [data i okoliczność].

Roszczenie zostało zatem wniesione [przed upływem / w terminie] przedawnienia.
```

Schemat argumentacyjny:

1. Wskaż termin przedawnienia (art. 118 KC: 6 lat ogólny, 3 lata dla roszczeń okresowych i związanych z działalnością gospodarczą)
2. Wskaż początek biegu (art. 120 § 1 KC)
3. Jeśli bieg był zawieszony/przerwany — wyjaśnij (art. 121, 123 KC)
4. Jeśli sprawa dotyczy konsumenta — powołaj się na orzecznictwo TSUE o początku biegu przedawnienia (konsument musi mieć realną możliwość poznania swoich praw)

---

#### VII. KOSZTY ZASTĘPSTWA PROCESOWEGO

> Na zakończenie, Strona Powodowa wnosi o zasądzenie kosztów zastępstwa procesowego [w podwójnej / potrójnej wysokości norm przepisanych]. Uzasadnieniem dla takiego wniosku jest [znaczny nakład pracy pełnomocnika / wysoki stopień skomplikowania sprawy / konieczność analizy obszernej dokumentacji / wielowątkowość sprawy / precedensowy charakter zagadnienia].

---

### PODPIS I ZAŁĄCZNIKI

```
                                        ____________________________
                                        [tytuł zawodowy] [imię nazwisko]
                                        Pełnomocnik Strony Powodowej

Załączniki:
1. Pełnomocnictwo wraz z dowodem uiszczenia opłaty skarbowej
2. Potwierdzenie uiszczenia opłaty sądowej w kwocie [X] zł
3. Odpis KRS Strony Pozwanej [jeśli osoba prawna]
4. Umowa [opis] z dnia [data]
5. [kolejne załączniki — dokumenty powołane jako dowody]
6. Wezwanie do zapłaty z dnia [data] z potwierdzeniem nadania/doręczenia
7. [korespondencja stron]
8. [zestawienia, kalkulacje]
9. Odpis Pozwu z załącznikami dla Strony Pozwanej
```

---

## Faza 4: Generowanie pliku .docx

Użyj skilla docx do wygenerowania dokumentu Word. Ważne wytyczne formatowania:

### Format dokumentu:
- **Papier**: A4 (11906 x 16838 DXA)
- **Marginesy**: 1 cal (1440 DXA) z każdej strony
- **Font**: Times New Roman 12pt (standardowy font pism sądowych w Polsce)
- **Interlinia**: 1.15 lub 1.5
- **Justowanie**: pełne (obustronne) dla treści uzasadnienia
- **Numeracja stron**: na dole, wycentrowana

### Formatowanie nagłówka:
- Tabulator prawy dla danych sądu i pozwanego (wyrównanie do prawej)
- Dane stron z wcięciami tabulacji
- „POZEW" — wycentrowany, pogrubiony, duże litery
- „o zapłatę" — wycentrowany, mniejszy

### Formatowanie treści:
- Śródtytuły sekcji (np. „UZASADNIENIE", „I. STAN FAKTYCZNY") — pogrubione, wycentrowane lub wyrównane do lewej
- „Dowód:" — z wcięciem, po nim lista myślnikowa dowodów
- Cytaty z orzeczeń — w cudzysłowie, możliwe kursywą
- Każdy punkt petitum — numerowany (z wcięciem)
- Brak pustych linii wewnątrz akapitów uzasadnienia — zamiast tego spacing between paragraphs

---

## Faza 5: Weryfikacja końcowa

Po wygenerowaniu pozwu, przeprowadź samoweryfikację:

### Checklist formalny (art. 126 + 187 KPC):
- [ ] Oznaczenie sądu
- [ ] Imiona, nazwiska/nazwy stron, adresy, PESEL/KRS/NIP
- [ ] Oznaczenie rodzaju pisma („POZEW")
- [ ] Dokładnie określone żądanie (petitum)
- [ ] Wartość przedmiotu sporu (w sprawach majątkowych)
- [ ] Data wymagalności roszczenia
- [ ] Wskazanie faktów + dowodów
- [ ] Oświadczenie o mediacji
- [ ] Podpis
- [ ] Lista załączników

### Checklist merytoryczny:
- [ ] Każde roszczenie ma podstawę prawną
- [ ] Każda przesłanka normy prawnej jest zaadresowana w subsumpcji
- [ ] Każde twierdzenie faktyczne ma dowód
- [ ] Powołano aktualne orzecznictwo (z IuraMCP)
- [ ] Powołano aktualne przepisy (z IuraMCP)
- [ ] Odniesiono się do przedawnienia
- [ ] Odniesiono się do właściwości sądu
- [ ] Poprawnie obliczono opłatę sądową
- [ ] Antycypowano główne zarzuty pozwanego

### Checklist strategiczny:
- [ ] Roszczenia ułożone hierarchicznie (główne → ewentualne)
- [ ] Argumentacja płynna i logicznie spójna
- [ ] Brak powtórzeń i brak luk argumentacyjnych
- [ ] Pozew jest wyczerpujący — nie pominięto żadnego istotnego argumentu

---

## Ważne zasady generowania

1. **Nie ograniczaj długości** — pozew ma być tak długi, jak wymaga sprawa. Profesjonalne pozwy mają regularnie 30-80 stron.

2. **Zawsze szukaj w IuraMCP** — nigdy nie cytuj przepisów i orzeczeń z pamięci. Zawsze użyj Search_DU dla przepisów i Search_SN/Search_SP dla orzecznictwa. Podawaj rzeczywiste sygnatury i daty.

3. **Subsumpcja jest obowiązkowa** — nie wystarczy napisać „roszczenie jest zasadne na podstawie art. X". Musisz rozbić normę na przesłanki i udowodnić każdą z osobna.

4. **Język prawniczy** — używaj profesjonalnego języka prawniczego, ale czytelnego. Unikaj żargonu tam, gdzie zwykły język jest jaśniejszy.

5. **Spójność wewnętrzna** — fakty z części faktycznej muszą korespondować z argumentami z części prawnej. Dowody wskazane w petitum muszą być wymienione w załącznikach.

6. **Hierarchia żądań** — roszczenie główne zawsze przed ewentualnym. „w każdym przypadku" dla wniosków niezależnych od wyniku (koszty procesu).

7. **Daty i kwoty** — jeśli użytkownik nie podał, wstaw „…" (wielokropek). Nigdy nie wymyślaj dat i kwot.

8. **Prawo UE** — jeśli sprawa dotyczy konsumenta, ZAWSZE rozważ powołanie Dyrektywy 93/13/EWG (nieuczciwe warunki umowne) i orzecznictwa TSUE. Polskie sądy coraz częściej odwołują się bezpośrednio do prawa unijnego.

9. **Generuj plik .docx** — pozew MUSI być dostarczony jako plik Word, nie jako tekst w konwersacji.

---

## REFERENCJE: Kluczowe formaty cytowania

Przy sporządzaniu pozwu stosuj poniższe konwencje cytowania — ich spójne użycie świadczy o profesjonalizmie pisma:

### Przepis ustawy:
- `art. 385¹ § 1 k.c.` (Kodeks cywilny)
- `art. 187 § 1 pkt 1) k.p.c.` (Kodeks postępowania cywilnego)
- `art. 69 ust. 2 pkt 5) Prawa bankowego`

### Łączenie przepisów:
- `art. 410 § 1 k.c. w zw. z art. 405 k.c.` (stosowanie łącznie)
- `art. 187 § 1 pkt 1) k.p.c. w zw. z art. 189 k.p.c.` (procesowy + materialny)

### Orzeczenie SN:
- `wyrok SN z dnia 15 stycznia 2023 r., sygn. akt II CSKP 212/22`
- `uchwała SN z dnia 16 lutego 2021 r., sygn. akt III CZP 11/20`

### Orzeczenie TSUE:
- `wyrok TSUE z dnia [data] r. w sprawie C-XXX/XX ([nazwa sprawy])`

### Dyrektywa UE:
- `Dyrektywa Rady 93/13/EWG z dnia 5 kwietnia 1993 r. w sprawie nieuczciwych warunków w umowach konsumenckich`