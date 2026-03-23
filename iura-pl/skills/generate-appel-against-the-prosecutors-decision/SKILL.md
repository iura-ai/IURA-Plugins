---
name: generate-appel-against-the-prosecutors-decision
description: A skill for generating procedurally correct appels against the prosecutors decisions (zażalenie), following polish regulations.
---

# Generate Appel Against The Prosecutors Decision

## Instructions
Clear, step-by-step guidance for the agent.

# Zażalenie na postanowienie prokuratora

Skill służy do generowania zażaleń na postanowienia prokuratora (o umorzeniu
postępowania, odmowie wszczęcia, zawieszeniu itd.). Treść wygenerowana stanowi
poprawną formę pisma procesowego wynikającą z przepisów Kodeksu postępowania
karnego (k.p.k.).

---

## Zasada nadrzędna

Zażalenie to **środek odwoławczy** wnoszony do sądu za pośrednictwem prokuratury.
Jego celem jest wykazanie, że postanowienie prokuratora jest wadliwe — czy to
na skutek błędnych ustaleń faktycznych, czy naruszenia przepisów postępowania.

Zawsze używaj narzędzi wyszukiwania

Styl: profesjonalny, rzeczowy, perswazyjny, bez emocjonalnych dygresji. Każdy
argument musi być zakotwiczony w materiale dowodowym. NIE W FORMACIE MARKDOWN

---

## Krok wstępny: identyfikacja scenariusza procesowego

Przed generowaniem pisma **MUSISZ** ustalić, w którym scenariuszu procesowym
znajduje się sprawa. Od tego zależy adresat, podstawa prawna i dopuszczalność
zażalenia. Zadaj użytkownikowi pytania, jeśli brak danych.

### Scenariusz A — Pierwsze zaskarżenie postanowienia (art. 306 k.p.k.)

Pokrzywdzony (lub jego pełnomocnik) po raz pierwszy zaskarża postanowienie
prokuratora. Zażalenie kieruje się **do sądu** za pośrednictwem prokuratora.

### Scenariusz B — Ponowne postanowienie po uchyleniu przez sąd (art. 330 § 2 k.p.k.)

Sąd uchylił wcześniejsze postanowienie i przekazał sprawę do dalszego
prowadzenia. Prokurator ponownie wydał postanowienie o umorzeniu lub odmowie
wszczęcia, nie znajdując podstaw do wniesienia aktu oskarżenia. W tym scenariuszu
zażalenie kieruje się **do prokuratora nadrzędnego**, NIE do sądu.

**UWAGA KRYTYCZNA:** Błędne skierowanie zażalenia do sądu w scenariuszu B
stanowi rażące naruszenie art. 330 § 2 k.p.k. (por. SN III KK 566/24,
SN II KK 261/22, SN II KK 617/22, SN IV KK 560/23). Sąd, który rozpozna
takie zażalenie, naruszy prawo, a postanowienie sądu zostanie uchylone.

**UWAGA — WYMÓG TOŻSAMOŚCI PRZEDMIOTOWEJ (SN I KZ 2/25):** Art. 330 § 2
k.p.k. stosuje się wyłącznie gdy ponowne postanowienie dotyczy **tego samego
zdarzenia historycznego** co postanowienie uchylone przez sąd (tożsamość
przedmiotowa i podmiotowa). Jeżeli ponowne postanowienie obejmuje czyny,
które **nie były przedmiotem wcześniejszej kontroli sądowej** ani nie są
tożsame przedmiotowo z czynem objętym pierwotnym postanowieniem, zażalenie
przysługuje na zasadach ogólnych — **do sądu** (Scenariusz A), a nie do
prokuratora nadrzędnego. Przed zakwalifikowaniem sprawy do Scenariusza B
**MUSISZ** zweryfikować tożsamość przedmiotową obu postanowień.

**UWAGA — NIEJEDNORODNOŚĆ DECYZJI (SN II DO 76/20, SN IV KK 87/13):**
Jeżeli pierwotne postanowienie to odmowa wszczęcia, a ponowne to umorzenie
(lub odwrotnie), ścieżka z art. 330 § 2 k.p.k. może nie otworzyć drogi
do subsydiarnego aktu oskarżenia. Poinformuj użytkownika o tym ryzyku.

### Scenariusz C — Subsydiarny akt oskarżenia (art. 55 § 1 k.p.k.)

Jeżeli po wyczerpaniu ścieżki z art. 330 § 2 k.p.k. prokurator nadrzędny
utrzyma w mocy zaskarżone postanowienie, pokrzywdzony uzyskuje prawo do
wniesienia **subsydiarnego aktu oskarżenia** w terminie miesiąca od doręczenia
zawiadomienia o utrzymaniu postanowienia w mocy (art. 55 § 1 k.p.k. w zw.
z art. 330 § 2 zd. 3 k.p.k.). Ten scenariusz wykracza poza zakres tego skilla,
ale skill powinien poinformować użytkownika o tej możliwości, jeśli się ujawni.

---

## Baza prawna — przepisy rządzące formą i dopuszczalnością

### Dopuszczalność zażalenia (Scenariusz A)

| Rodzaj postanowienia | Podstawa prawna | Krąg uprawnionych |
|---|---|---|
| **Odmowa wszczęcia śledztwa** | art. 306 **§ 1** k.p.k. | Pokrzywdzony; instytucja z art. 305 § 4; osoba z art. 305 § 4, jeżeli naruszono jej prawa |
| **Umorzenie śledztwa** | art. 306 **§ 1a** k.p.k. | Strony; instytucja państwowa/samorządowa składająca zawiadomienie; osoby niebędące pokrzywdzonym w zakresie przestępstw z art. 228–231, 233, 235, 236, 245, 270–294, 296–306c k.k. |
| **Odmowa wszczęcia dochodzenia** | art. 306 § 1 k.p.k. w zw. z art. 325a § 2 k.p.k. | Jak dla odmowy wszczęcia śledztwa |
| **Umorzenie dochodzenia** | art. 306 § 1a k.p.k. w zw. z art. 325a § 2 k.p.k. | Jak dla umorzenia śledztwa |

**WAŻNE:** Paragraf 1 dotyczy **odmowy wszczęcia**, paragraf 1a dotyczy
**umorzenia**. Krąg uprawnionych jest RÓŻNY — § 1a jest szerszy. Błędne
wskazanie podstawy prawnej to potencjalny brak formalny.

### Dopuszczalność zażalenia (Scenariusz B — art. 330 § 2 k.p.k.)

Ponowne postanowienie po uchyleniu przez sąd — zażalenie przysługuje **tylko
do prokuratora nadrzędnego**. Organ, forma pisma i podstawa prawna różnią
się zasadniczo od Scenariusza A.

### Termin do wniesienia zażalenia

- **7 dni** od daty doręczenia postanowienia (art. 460 k.p.k.)

### Prawo do przeglądania akt

Przed wniesieniem zażalenia uprawnionym przysługuje prawo do przeglądania akt
sprawy (art. 306 § 1b k.p.k.). Prokurator może udostępnić akta w postaci
elektronicznej.

### Wymogi formalne pisma procesowego (art. 119 § 1 k.p.k.)

Każde pismo procesowe powinno zawierać:

1. **Oznaczenie organu**, do którego jest skierowane, oraz sprawy, której dotyczy
2. **Oznaczenie oraz adres wnoszącego** pismo, a w pierwszym piśmie w sprawie:
   - numer telefonu, faksu i adres e-mail (lub oświadczenie o ich nieposiadaniu)
   - oświadczenie o zgodzie na doręczenia elektroniczne (lub brak zgody)
3. **Numer wpisu na listę adwokatów/radców prawnych** — w przypadku pełnomocnika
   będącego adwokatem lub radcą prawnym (art. 119 § 1 pkt 2a k.p.k.)
4. **Treść wniosku lub oświadczenia**, w miarę potrzeby z uzasadnieniem
5. **Datę i podpis** składającego pismo

**UWAGA — ELEKTRONIZACJA (ustawa z 9 lipca 2025 r.):** Nowelizacja k.p.k.
wprowadza możliwość wnoszenia pism procesowych za pośrednictwem portalu
informacyjnego sądów. Pisma elektroniczne muszą być opatrzone **kwalifikowanym
podpisem elektronicznym lub podpisem zaufanym**. Jeśli użytkownik wskaże,
że zamierza wnieść zażalenie elektronicznie, uwzględnij ten tryb w piśmie.

### Wymogi środka odwoławczego (art. 427 § 1 i § 2 k.p.k.)

Odwołujący się powinien wskazać:
- **Zaskarżone rozstrzygnięcie lub ustalenie** (§ 1)
- **Czego się domaga** — wniosek odwoławczy (§ 1)
- Jeżeli środek pochodzi od **oskarżyciela publicznego, obrońcy lub
  pełnomocnika** — obligatoryjnie:
  - **Zarzuty stawiane rozstrzygnięciu** (§ 2)
  - **Uzasadnienie** (§ 2)

**UWAGA:** Gdy pokrzywdzony działa **osobiście** (bez pełnomocnika), zarzuty
i uzasadnienie NIE są obligatoryjne — wystarczy wskazanie zaskarżonego
rozstrzygnięcia i wniosku odwoławczego (art. 427 § 1 k.p.k.). Pismo powinno
jednak zawierać argumentację, aby było skuteczne — brak zarzutów nie oznacza,
że sąd nie oceni sprawy, ale ogranicza zakres kontroli (por. art. 433 § 1 k.p.k.).

### Katalog zarzutów odwoławczych (art. 438 k.p.k.)

Orzeczenie ulega uchyleniu lub zmianie w razie stwierdzenia:

| art. 438 pkt | Rodzaj uchybienia | Zastosowanie w zażaleniu |
|---|---|---|
| **pkt 1** | Obraza przepisów prawa materialnego — kwalifikacja prawna | Błędna kwalifikacja lub niewłaściwa wykładnia znamion |
| **pkt 1a** | Obraza prawa materialnego — inny wypadek niż kwalifikacja | Np. błędne zastosowanie instytucji przedawnienia |
| **pkt 2** | Obraza przepisów postępowania, jeśli mogła mieć wpływ na treść | Najczęstszy zarzut — naruszenie art. 7, art. 92, art. 167 k.p.k. |
| **pkt 3** | Błąd w ustaleniach faktycznych przyjętych za podstawę orzeczenia | Ustalenia sprzeczne z materiałem dowodowym |
| **pkt 4** | Rażąca niewspółmierność kary | Nie dotyczy postanowień o umorzeniu |

### Ograniczenia przy formułowaniu zarzutów

**Ograniczenie z art. 427 § 3a k.p.k.** — W środku odwoławczym **nie można
podnosić zarzutu nieprzeprowadzenia dowodu z urzędu** (art. 167 k.p.k.),
**chyba że** okoliczność, która ma być udowodniona, ma istotne znaczenie
dla ustalenia: czy został popełniony czyn zabroniony, czy stanowi on
przestępstwo i jakie, czy czyn popełniono w warunkach z art. 64 lub 65 k.k.,
czy zachodzą warunki do orzeczenia pobytu w zakładzie psychiatrycznym.

W praktyce przy zażaleniach na umorzenie ograniczenie to zwykle nie wyklucza
zarzutu (bo chodzi o ustalenie, czy czyn został popełniony), ale należy je
mieć na uwadze i powoływać się na odpowiedni wyjątek.

**Ograniczenie z art. 427 § 4 k.p.k. (prekluzja dowodowa)** — Zarzut
nieprzeprowadzenia dowodu z art. 167 k.p.k. może być niedopuszczalny, jeśli
strona **sama nie składała wniosku dowodowego** w toku postępowania (por.
SN III KK 352/17). Przed formułowaniem zarzutu z art. 167 k.p.k. ustal,
czy pokrzywdzony lub pełnomocnik składał wnioski dowodowe. Jeśli nie —
rozważ, czy zarzut jest dopuszczalny w świetle § 4.

### Najczęściej powoływane przepisy przy zarzutach

| Przepis | Treść zasady | Kontekst zarzutu | WAŻNE ZASTRZEŻENIE |
|---|---|---|---|
| **art. 7 k.p.k.** | Swobodna ocena dowodów | Ocena dowolna, nielogiczna, sprzeczna z doświadczeniem życiowym | Samodzielna podstawa zarzutu — DOPUSZCZALNA |
| **art. 4 k.p.k.** | Zasada obiektywizmu | Jednostronne uwzględnienie jednej wersji wydarzeń | **NIE MOŻE stanowić samodzielnej podstawy zarzutu** — musi być powiązany z art. 7, 92, 167 k.p.k. (ugruntowane orzecznictwo SN: V KK 391/23, V KK 63/13, III KK 562/17, V KK 345/20, IV KK 12/24) |
| **art. 2 § 2 k.p.k.** | Dążenie do prawdy materialnej | Zaniechanie wyjaśnienia istotnych okoliczności | **NIE MOŻE stanowić samodzielnej podstawy zarzutu** — zasada generalna wymagająca konkretyzacji (SN V KK 300/12, IV KK 256/16, III KK 28/14). ZAWSZE łącz z art. 7 lub innym przepisem szczegółowym |
| **art. 92 k.p.k.** | Podstawa orzeczenia — całokształt okoliczności | Pominięcie kluczowych dowodów | **WŁAŚCIWSZY** od art. 410 k.p.k. w postępowaniu przygotowawczym |
| **art. 167 k.p.k.** | Inicjatywa dowodowa organu | Zaniechanie przeprowadzenia dowodów z urzędu | Z zastrzeżeniem art. 427 § 3a **i** art. 427 § 4 k.p.k. |
| **art. 410 k.p.k.** | Obowiązek uwzględnienia całokształtu okoliczności | Pominięcie kluczowych dowodów | Formalnie dotyczy wyrokowania; w postępowaniu przygotowawczym stosuje się odpowiednio — **preferuj art. 92 k.p.k.** |
| **art. 366 § 1 k.p.k.** | Obowiązek wszechstronnego wyjaśnienia | Niewyjaśnienie istotnych wątpliwości | Dotyczy rozprawy — w postępowaniu przygotowawczym stosuje się odpowiednio przez art. 465 § 1 k.p.k. |

---

## Struktura zażalenia — schemat uniwersalny

### Część I: Nagłówek (dane adresowe i oznaczenie stron)

**Scenariusz A (zażalenie do sądu):**
```
[Miejscowość], dnia [dzień] [miesiąca słownie] [rok] roku

Sygn. akt: [sygnatura sprawy prokuratorskiej]

[Nazwa sądu rejonowego/okręgowego]
[ulica]
[kod pocztowy, miejscowość]

za pośrednictwem

[Nazwa prokuratury]
[ulica]
[kod pocztowy, miejscowość]

[Imię i Nazwisko pełnomocnika]
[tytuł zawodowy — adwokat / radca prawny]
[numer wpisu na listę]
[adres kancelarii]
[tel./e-mail]
pełnomocnik pokrzywdzonego/pokrzywdzonej [Imię i Nazwisko]
```

**Scenariusz B (zażalenie do prokuratora nadrzędnego — art. 330 § 2 k.p.k.):**
```
[Miejscowość], dnia [dzień] [miesiąca słownie] [rok] roku

Sygn. akt: [sygnatura sprawy prokuratorskiej]

[Nazwa prokuratury nadrzędnej]
[ulica]
[kod pocztowy, miejscowość]

za pośrednictwem

[Nazwa prokuratury, która wydała postanowienie]
[ulica]
[kod pocztowy, miejscowość]

[dane pełnomocnika / pokrzywdzonego — jak wyżej]
```

**REGUŁY NAGŁÓWKA:**
- Scenariusz A: Zażalenie wnosi się do **sądu** właściwego do rozpoznania
  sprawy w I instancji, **za pośrednictwem prokuratora** który wydał
  postanowienie (art. 306 § 1/1a k.p.k., art. 465 § 2 k.p.k.)
- Scenariusz B: Zażalenie wnosi się do **prokuratora nadrzędnego** za
  pośrednictwem prokuratora, który wydał ponowne postanowienie (art. 330 § 2 k.p.k.)
- Pełnomocnik podaje numer wpisu na listę adwokatów/radców prawnych
  (art. 119 § 1 pkt 2a k.p.k.)
- W pierwszym piśmie w sprawie: numer telefonu, e-mail lub oświadczenie
  o ich nieposiadaniu (art. 119 § 1 pkt 2 k.p.k.)
- Data w formacie: „15 stycznia 2026 roku"

### Część II: Tytuł (petitum nagłówkowe)

**Scenariusz A:**
```
ZAŻALENIE
NA POSTANOWIENIE [organu wydającego: PROKURATORA PROKURATURY (szczebel) W (miasto)
/ POLICJI, ZATWIERDZONE PRZEZ PROKURATORA PROKURATURY (szczebel) W (miasto)]
Z DNIA [data] ROKU O [UMORZENIU ŚLEDZTWA / UMORZENIU DOCHODZENIA / ODMOWIE
WSZCZĘCIA ŚLEDZTWA / ODMOWIE WSZCZĘCIA DOCHODZENIA],
SYGN. AKT: [sygnatura]
```

**Scenariusz B:**
```
ZAŻALENIE
NA PONOWNE POSTANOWIENIE PROKURATORA PROKURATURY [szczebel] W [miasto]
Z DNIA [data] ROKU O [UMORZENIU DOCHODZENIA / UMORZENIU ŚLEDZTWA / ODMOWIE
WSZCZĘCIA POSTĘPOWANIA],
WYDANE W TRYBIE ART. 330 § 2 K.P.K.,
SYGN. AKT: [sygnatura]
```

**REGUŁY:**
- Tytuł pisany WERSALIKAMI
- Zawiera: organ wydający, datę, rodzaj decyzji, sygnaturę
- Jeżeli postanowienie było zatwierdzone — wskazać to w tytule

### Część III: Komparycja i zakres zaskarżenia

Jeden blok tekstu zawierający legitymację skarżącego, podstawę prawną,
zakres zaskarżenia i identyfikację zaskarżonego postanowienia.

**Formuły wzorcowe komparycji:**

#### Pełnomocnik, umorzenie dochodzenia (Scenariusz A):
```
Działając jako pełnomocnik pokrzywdzonego/pokrzywdzonej [Imię Nazwisko]
/pełnomocnictwo w aktach sprawy/, na podstawie art. 306 § 1a k.p.k.
w zw. z art. 325a § 2 k.p.k. i art. 465 § 2 k.p.k., zaskarżam w całości
postanowienie z dnia [data] o umorzeniu dochodzenia w sprawie o sygn.
akt: [sygnatura], toczącego się przeciwko [Imię Nazwisko podejrzanego],
zatwierdzonego przez Prokuratora Prokuratury [szczebel] w [miasto].
```

#### Pełnomocnik, umorzenie śledztwa (Scenariusz A):
```
Działając jako pełnomocnik pokrzywdzonego/pokrzywdzonej [Imię Nazwisko]
/pełnomocnictwo w aktach sprawy/, na podstawie art. 306 § 1a k.p.k.
i art. 465 § 2 k.p.k., zaskarżam w całości postanowienie z dnia [data]
o umorzeniu śledztwa w sprawie o sygn. akt: [sygnatura].
```

#### Pełnomocnik, odmowa wszczęcia śledztwa/dochodzenia (Scenariusz A):
```
Działając jako pełnomocnik pokrzywdzonego/pokrzywdzonej [Imię Nazwisko]
/pełnomocnictwo w aktach sprawy/, na podstawie art. 306 § 1 k.p.k.
i art. 465 § 2 k.p.k., zaskarżam w całości postanowienie z dnia [data]
o odmowie wszczęcia [śledztwa/dochodzenia] w sprawie o sygn. akt:
[sygnatura].
```

#### Pokrzywdzony osobiście (Scenariusz A):
```
Działając jako pokrzywdzony/pokrzywdzona w sprawie o sygn. akt:
[sygnatura], na podstawie art. 306 § [1/1a] k.p.k., zaskarżam w całości
postanowienie z dnia [data] o [umorzeniu śledztwa / umorzeniu dochodzenia
/ odmowie wszczęcia postępowania].
```

#### Pełnomocnik, ponowne postanowienie (Scenariusz B — art. 330 § 2 k.p.k.):
```
Działając jako pełnomocnik pokrzywdzonego/pokrzywdzonej [Imię Nazwisko]
/pełnomocnictwo w aktach sprawy/, na podstawie art. 330 § 2 k.p.k.,
zaskarżam w całości ponowne postanowienie z dnia [data] o [umorzeniu
dochodzenia / umorzeniu śledztwa / odmowie wszczęcia postępowania]
w sprawie o sygn. akt: [sygnatura], wydane po uprzednim uchyleniu
postanowienia z dnia [data pierwotnego postanowienia] przez [Sąd Rejonowy /
Sąd Okręgowy] w [miasto] postanowieniem z dnia [data postanowienia sądu].
```

**Tabela — dobór podstawy prawnej komparycji:**

| Scenariusz | Forma postępowania | Podstawa prawna w komparycji |
|---|---|---|
| A | Odmowa wszczęcia śledztwa | art. 306 § 1 k.p.k. i art. 465 § 2 k.p.k. |
| A | Odmowa wszczęcia dochodzenia | art. 306 § 1 k.p.k. w zw. z art. 325a § 2 k.p.k. i art. 465 § 2 k.p.k. |
| A | Umorzenie śledztwa | art. 306 § 1a k.p.k. i art. 465 § 2 k.p.k. |
| A | Umorzenie dochodzenia | art. 306 § 1a k.p.k. w zw. z art. 325a § 2 k.p.k. i art. 465 § 2 k.p.k. |
| B | Ponowne postanowienie (dowolne) | art. 330 § 2 k.p.k. |

**WYJĄTEK — oskarżenie prywatne (art. 465 § 2a k.p.k.):** W sprawach
z oskarżenia prywatnego, gdy postanowienie zapadło z uwagi na brak interesu
społecznego w ściganiu z urzędu, zażalenie rozpoznaje **prokurator nadrzędny**,
nie sąd.

### Część IV: Zarzuty

Formuła wprowadzająca: `Na podstawie art. 427 § 2 k.p.k. w zw. z art. 438
pkt [nr] k.p.k. postanowieniu zarzucam:`

**UWAGA:** Tę część generuj TYLKO gdy autorem zażalenia jest pełnomocnik
(adwokat/radca prawny). Gdy pokrzywdzony działa osobiście, zarzuty formalne
nie są obligatoryjne (art. 427 § 2 k.p.k. a contrario) — można przejść
od razu do uzasadnienia z argumentacją.

**Formuły wzorcowe zarzutów:**

#### Zarzut naruszenia art. 7 k.p.k. (dowolna ocena dowodów)
```
obrazę art. 7 k.p.k. — poprzez dokonanie dowolnej, a nie swobodnej
oceny materiału dowodowego, polegającej na [opis konkretnego uchybienia],
podczas gdy prawidłowa ocena zgromadzonych dowodów, w szczególności
[wskazanie dowodów], prowadzi do wniosku, że [wniosek przeciwny
do przyjętego przez prokuratora];
```

#### Zarzut naruszenia art. 7 k.p.k. w zw. z art. 4 k.p.k. (dowolna ocena + obiektywizm)
```
obrazę art. 7 k.p.k. w zw. z art. 4 k.p.k. — poprzez dokonanie
dowolnej oceny materiału dowodowego z naruszeniem zasady obiektywizmu,
polegającą na jednostronnym uwzględnieniu [wyjaśnień podejrzanego /
jednej wersji wydarzeń] z jednoczesnym pominięciem dowodów wskazujących
na [opis], w szczególności [wyliczenie pominiętych dowodów];
```

**⚠ NIGDY nie formułuj art. 4 k.p.k. jako samodzielnego zarzutu.** Art. 4 k.p.k.
jako ogólna zasada procesu nie może stanowić samodzielnej podstawy zarzutu
odwoławczego — musi być powiązany z konkretnymi przepisami szczegółowymi
(ugruntowane orzecznictwo SN: V KK 391/23, V KK 63/13, IV KK 414/18,
V KK 345/20, III KK 562/17, IV KK 12/24).

#### Zarzut naruszenia art. 7 k.p.k. w zw. z art. 92 k.p.k. (kompleksowy)
```
obrazę art. 7 k.p.k. w zw. z art. 92 k.p.k. — poprzez dokonanie
dowolnej oceny materiału dowodowego, z pominięciem istotnych okoliczności
wynikających ze zgromadzonych dowodów, polegającą na [opis], podczas gdy
całokształt materiału dowodowego, w szczególności [wyliczenie dowodów],
wskazuje na [wniosek przeciwny];
```

**Dlaczego art. 92 k.p.k., a nie art. 410 k.p.k.?** Art. 410 k.p.k. dotyczy
formalnie wyrokowania na rozprawie. W postępowaniu przygotowawczym właściwszym
przepisem jest art. 92 k.p.k. (podstawa orzeczenia — całokształt okoliczności
ujawnionych w postępowaniu), który stosuje się wprost, a nie odpowiednio.
Art. 410 k.p.k. jest dopuszczalny przy odpowiednim stosowaniu (art. 465 § 1
k.p.k.), ale art. 92 k.p.k. jest merytorycznie trafniejszy.

#### Zarzut naruszenia art. 2 § 2 k.p.k. w zw. z art. 7 k.p.k. (prawda materialna)
```
obrazę art. 2 § 2 k.p.k. w zw. z art. 7 k.p.k. — poprzez zaniechanie
dążenia do ustalenia prawdy materialnej i przedwczesne umorzenie
postępowania pomimo niewyjaśnienia istotnych okoliczności sprawy,
w tym [wyliczenie], co było wynikiem dowolnej oceny materiału
dowodowego;
```

**⚠ NIGDY nie formułuj art. 2 § 2 k.p.k. jako samodzielnego zarzutu.**
Art. 2 § 2 k.p.k. jako zasada generalna nie może stanowić samodzielnej
podstawy zarzutu — wymaga konkretyzacji przez powiązanie z przepisami
szczegółowymi, np. art. 7, art. 92, art. 167 k.p.k. (ugruntowane
orzecznictwo SN: V KK 300/12, IV KK 256/16, III KK 28/14).

#### Zarzut naruszenia art. 167 k.p.k. (inicjatywa dowodowa)
```
obrazę art. 167 k.p.k. — poprzez zaniechanie przeprowadzenia z urzędu
dowodów niezbędnych do prawidłowego rozstrzygnięcia sprawy, a mianowicie
[wyliczenie nieprzeprowadzonych dowodów], co miało istotny wpływ na treść
zaskarżonego postanowienia, przy czym zarzut ten jest dopuszczalny, gdyż
okoliczności, które miały być udowodnione, mają istotne znaczenie dla
ustalenia, czy został popełniony czyn zabroniony i czy stanowi on
przestępstwo (art. 427 § 3a k.p.k.);
```

#### Zarzut błędu w ustaleniach faktycznych (art. 438 pkt 3 k.p.k.)
```
błąd w ustaleniach faktycznych przyjętych za podstawę orzeczenia,
mający wpływ na jego treść, polegający na przyjęciu, że [ustalenie
prokuratora], podczas gdy z materiału dowodowego, w szczególności
z [wyliczenie dowodów], wynika, że [prawidłowe ustalenie];
```

#### Zarzut obrazy prawa materialnego (art. 438 pkt 1 lub 1a k.p.k.)
```
obrazę przepisów prawa materialnego, a mianowicie art. [numer] k.k.,
poprzez [błędną wykładnię / niewłaściwe zastosowanie / niezastosowanie],
polegającą na [opis uchybienia];
```

**REGUŁY FORMUŁOWANIA ZARZUTÓW:**
- Każdy zarzut kończy się średnikiem, ostatni — kropką
- Zarzuty można łączyć (np. art. 7 k.p.k. w zw. z art. 92 k.p.k.)
- Przy pełnomocniku zarzuty są **obligatoryjne** (art. 427 § 2 k.p.k.)
- Zarzut z art. 438 pkt 2 k.p.k. musi wskazywać **wpływ uchybienia
  na treść orzeczenia**
- Unikać formułowania jednego „mega-zarzutu" — lepiej rozbić na odrębne
- **NIGDY** nie formułować art. 4 k.p.k. samodzielnie — ZAWSZE w powiązaniu
  z art. 7 lub innym przepisem szczegółowym
- **NIGDY** nie formułować art. 2 § 2 k.p.k. samodzielnie — ZAWSZE
  w powiązaniu z art. 7 lub innym przepisem szczegółowym
- Zarzut z art. 167 k.p.k. — uwzględnić ograniczenie z art. 427 § 3a
  **oraz** prekluzję z art. 427 § 4 k.p.k.

### Część V: Wniosek odwoławczy

Formuła wprowadzająca: `Na podstawie art. 427 § 1 k.p.k. wnoszę o:`

**Formuły wzorcowe wniosków:**

#### Uchylenie i przekazanie do dalszego prowadzenia (najczęstszy):
```
uchylenie zaskarżonego postanowienia w całości i przekazanie sprawy
do dalszego prowadzenia.
```

#### Uchylenie i kontynuowanie w określonym kierunku:
```
uchylenie zaskarżonego postanowienia w całości i kontynuowanie
postępowania w kierunku czynu z art. [kwalifikacja] k.k.
```

#### Zmiana postanowienia (rzadki):
```
zmianę zaskarżonego postanowienia poprzez [opis żądanej zmiany].
```

**REGUŁA:** Wniosek musi korespondować z zarzutami. Jeśli zarzucamy błędną
ocenę dowodów i przedwczesne umorzenie → wnosimy o uchylenie i dalsze
prowadzenie. Jeśli zarzucamy błędną kwalifikację → możemy wnosić o zmianę.

### Część VI: Uzasadnienie

Nagłówek: `UZASADNIENIE` (wersalikami).

Uzasadnienie redaguje się **ciągłym tekstem akapitowym**. Kolejność treści:

**Akapit 1 — Tło sprawy.**
Zwięzłe przedstawienie: czego dotyczyło postępowanie, przeciwko komu, jaka
była kwalifikacja prawna, czym się zakończyło (umorzenie z jakiej przyczyny).

**Akapit 2 — Istota błędu organu.**
Wskazanie kluczowego uchybienia prokuratora — jaki błąd popełnił i dlaczego
postanowienie jest wadliwe. Centralny akapit ustawiający argumentację.

**Akapit 3 — Bezsporny stan faktyczny.**
Okoliczności wynikające z materiału dowodowego, obiektywnie sprawdzalne —
dokumenty, umowy, protokoły, inwentaryzacje, wezwania. Cel: pokazać twarde
fakty, których organ nie uwzględnił.

**Akapit 4 — Analiza dowodów obciążających.**
Omówienie dowodów przeczących ustaleniom prokuratora: zeznania świadków,
dokumentacja, wyniki oględzin. Wskazanie, jak organ je pominął lub wadliwie
ocenił.

**Akapit 5 — Krytyka wersji przeciwnej.**
Wykazanie, że wersja wydarzeń przyjęta przez prokuratora jest gołosłowna,
sprzeczna z dowodami lub nieweryfikowalna. Argumentacja musi być RZECZOWA —
bez sarkazmu, retorycznych pytań, emocjonalnych zwrotów.

**Akapit 6 — Zeznania świadków.**
Kluczowe zeznania i ich korelacja z pozostałym materiałem dowodowym.

**Akapit 7 — Konkluzja prawna.**
Podsumowanie: które przepisy naruszono, dlaczego umorzenie było
przedwczesne/bezpodstawne, odwołanie do zasad procesu.

**Akapit 8 — Petitum końcowe.**
Krótkie podsumowanie żądania z uzasadnieniem celowości dalszego prowadzenia.

**REGUŁY SYSTEMATYKI UZASADNIENIA:**

| Reguła | Uzasadnienie |
|---|---|
| Ciągły tekst akapitowy | Forma naturalna dla pisma procesowego |
| BEZ numerowanych sekcji (I, II, III) | Numeracja dopuszczalna, ale niekonieczna |
| BEZ podtytułów „Stan faktyczny", „Ocena prawna" | Płynne przejście od faktów do argumentacji |
| Argumentacja zakotwiczona w dowodach | Każde twierdzenie poparte odwołaniem do dowodu |
| Ton profesjonalny, bez emocji | BEZ retorycznych pytań, sarkazmu, wykrzykników |
| Odwołania do przepisów — precyzyjne | Art., §, pkt — zawsze |

### Część VII: Zakończenie

Zażalenie kończy się na konkluzji lub petitum końcowym. NIE dodaje się:
- Rozbudowanego pouczenia
- Listy załączników (chyba że nowe dowody — wówczas „Załączniki:")
- Formuł grzecznościowych („Z poważaniem") — to pismo procesowe

Podpis:
```
[Imię Nazwisko]
[tytuł zawodowy — adwokat / radca prawny]
```

---

## Wzorce formułek i mapowanie przyczyn umorzenia

Gotowe wzorce argumentacji (gołosłowność wyjaśnień, bezkrytyczne przyjęcie
wyjaśnień, przedwczesność umorzenia, konkluzja prawna, petitum końcowe)
oraz tabela mapowania przyczyn umorzenia na typowe zarzuty znajdują się
w pliku **`references/formulki.md`**. Odczytaj go przed generowaniem
uzasadnienia — zawiera sprawdzone formuły do bezpośredniego użycia.

---

## Adaptacja do rodzaju sprawy

Systematyka (struktura, kolejność, styl) pozostaje TAKA SAMA niezależnie
od rodzaju sprawy. Wskazówki do dostosowania treści uzasadnienia w zależności
od typu przestępstwa (przywłaszczenie, oszustwo, pobicie, znęcanie się,
groźby karalne, sprawy gospodarcze, odmowa wszczęcia) znajdują się w pliku
**`references/adaptacja.md`**. Odczytaj go, jeśli sprawa dotyczy konkretnego
rodzaju przestępstwa.

---

## Checklist walidacyjny

Przed uznaniem zażalenia za gotowe zweryfikuj każdy punkt:

**Scenariusz procesowy:**
- [ ] Zidentyfikowano prawidłowy scenariusz (A, B lub C)
- [ ] Adresat zażalenia jest prawidłowy (sąd vs. prokurator nadrzędny)
- [ ] Podstawa prawna dopuszczalności odpowiada scenariuszowi
- [ ] W Scenariuszu B: zweryfikowano tożsamość przedmiotową postanowień (SN I KZ 2/25)

**Wymogi formalne pisma procesowego (art. 119 k.p.k.):**
- [ ] Oznaczenie organu docelowego i pośredniczącego
- [ ] Dane wnoszącego z adresem
- [ ] Numer wpisu na listę (pełnomocnik) — art. 119 § 1 pkt 2a k.p.k.
- [ ] Telefon/e-mail lub oświadczenie o nieposiadaniu (pierwsze pismo)
- [ ] Data sporządzenia
- [ ] Sygnatura akt sprawy

**Wymogi środka odwoławczego (art. 427 k.p.k.):**
- [ ] Wskazanie zaskarżonego postanowienia (data, organ, sygnatura, rodzaj)
- [ ] Zakres zaskarżenia (w całości / w części)
- [ ] Zarzuty z powołaniem art. 438 k.p.k. (obligatoryjne TYLKO dla pełnomocnika)
- [ ] Wniosek odwoławczy
- [ ] Uzasadnienie

**Dopuszczalność:**
- [ ] Prawidłowa podstawa: § 1 dla odmowy, § 1a dla umorzenia
- [ ] Prawidłowy organ odwoławczy (sąd w Scenariuszu A, prokurator nadrzędny w B)
- [ ] Termin 7 dni (art. 460 k.p.k.)

**Poprawność zarzutów:**
- [ ] Art. 4 k.p.k. NIGDY jako samodzielny zarzut — zawsze w powiązaniu
- [ ] Art. 2 § 2 k.p.k. NIGDY jako samodzielny zarzut — zawsze w powiązaniu
- [ ] Art. 167 k.p.k. — uwzględniono ograniczenie z art. 427 § 3a k.p.k.
- [ ] Art. 167 k.p.k. — uwzględniono prekluzję z art. 427 § 4 k.p.k.
- [ ] Art. 92 k.p.k. preferowany nad art. 410 k.p.k. w postępowaniu przygotowawczym
- [ ] Każdy zarzut precyzyjny — konkretny przepis + konkretne uchybienie
- [ ] Zarzut z art. 438 pkt 2 wskazuje wpływ na treść orzeczenia

**Jakość merytoryczna:**
- [ ] Uzasadnienie spójne z zarzutami — każdy zarzut rozwinięty
- [ ] Argumentacja zakotwiczona w materiale dowodowym
- [ ] Wniosek koresponduje z zarzutami
- [ ] Ton profesjonalny — bez emocji, retorycznych pytań, sarkazmu

**Styl i systematyka:**
- [ ] Tytuł WERSALIKAMI
- [ ] Komparycja: legitymacja + podstawa prawna + zakres zaskarżenia
- [ ] Zarzuty w punktach z kwalifikacją uchybienia
- [ ] Uzasadnienie: ciągły tekst akapitowy
- [ ] Brak formuł grzecznościowych
- [ ] Objętość proporcjonalna do złożoności sprawy