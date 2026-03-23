---
name: generate-appeal-in-criminal-proceedings
description: A skill for generating procedurally correct appels from the first instance court ruling in criminal proceedings (apelacja).
---

# Appeal In Criminal Proceedings

## Instructions
Clear, step-by-step guidance for the agent.

# Apelacja od wyroku karnego — skill generujący

## Cel skilla

Generujesz profesjonalną apelację od wyroku sądu I instancji w postępowaniu karnym. Apelacja musi spełniać wymogi formalne k.p.k. i stosować prawniczy sposób argumentacji: precyzyjne wskazanie podstaw prawnych zarzutów, logiczną strukturę wywodu, odwołania do orzecznictwa i doktryny, oraz konsekwentne powiązanie zarzutów z wnioskami.

---

## KROK 0 — Zbierz informacje od użytkownika

Zanim zaczniesz pisać, ustal z użytkownikiem następujące dane. Nie generuj apelacji bez tych informacji:

1. **Sąd, który wydał wyrok** (nazwa, wydział, sygnatura, data wyroku)
2. **Sąd odwoławczy** (wynikający z właściwości instancyjnej)
3. **Dane oskarżonego** (imię, nazwisko; ewentualnie dane obrońcy jeśli apelację składa obrońca)
4. **Kwalifikacja prawna czynu** przypisanego wyrokiem (np. art. 286 § 1 k.k., art. 56 § 1 k.k.s.)
5. **Orzeczona kara i środki karne**
6. **Stan faktyczny sprawy** — co ustalił sąd i co jest kwestionowane
7. **Zakres zaskarżenia** — w całości czy w części, na korzyść czy na niekorzyść
8. **Główne zarzuty** — jakie uchybienia sądu I instancji użytkownik chce podnieść
9. **Czego domaga się skarżący** — uniewinnienie, umorzenie, uchylenie i przekazanie do ponownego rozpoznania, zmiana kary
10. **Nowe dowody** (jeśli są) — art. 427 § 3 k.p.k.

---

## KROK 1 — Wyszukaj podstawy prawne

OBOWIĄZKOWE: przed napisaniem apelacji ZAWSZE użyj narzędzi wyszukiwania prawnego, aby pozyskać aktualne i relewantne:

### Przepisy (Search_DU)
Wyszukaj aktualne brzmienie kluczowych przepisów k.p.k. i k.k./k.k.s. relewantnych dla sprawy:
- Przepisy o apelacji: art. 425, 427, 428, 437, 438, 439, 444-449a k.p.k.
- Zasady procesowe naruszane w zarzutach: art. 4, 5, 6, 7, 410, 424 k.p.k.
- Negatywne przesłanki procesowe: art. 17 k.p.k.
- Przepisy prawa materialnego dotyczące kwalifikacji czynu
- Przepisy o wymiarze kary: art. 53 k.k. i dalsze

### Orzecznictwo Sądu Najwyższego (Search_SN)
Wyszukaj orzecznictwo SN dotyczące:
- Standardów kontroli odwoławczej
- Wykładni naruszonego przepisu
- Granic swobodnej oceny dowodów (art. 7 k.p.k.)
- Bezwzględnych przyczyn odwoławczych (jeśli dotyczy)
- Specyfiki danego typu przestępstwa

### Orzecznictwo sądów powszechnych (Search_SP)
Wyszukaj orzeczenia sądów apelacyjnych i okręgowych dotyczące:
- Analogicznych stanów faktycznych
- Skuteczności podobnych zarzutów
- Wymiaru kary w podobnych sprawach

### Inne narzędzia (opcjonalnie)
- Search_TK — jeśli sprawa dotyczy konstytucyjności przepisu
- Search_KIO, Search_IP — jeśli sprawa ma aspekty szczególne
- Search_CBOSA — jeśli sprawa dotyczy zagadnień administracyjnych powiązanych z karnym (np. decyzje podatkowe w sprawach kks)

---

## KROK 2 — Zidentyfikuj i uporządkuj zarzuty

### Ogólna filozofia argumentacji

Apelacja karna to pismo procesowe, które musi łączyć precyzję prawniczą z siłą perswazji. Każdy element apelacji — od zarzutów po uzasadnienie — powinien tworzyć spójny, logiczny ciąg argumentacyjny.

### Zasady naczelne

**Zasada konkretności**: Każdy zarzut musi wskazywać KONKRETNY przepis naruszony, KONKRETNY dowód pominięty lub błędnie oceniony, KONKRETNE ustalenie faktyczne, które jest wadliwe. Zarzuty ogólnikowe są nieskuteczne.

**Zasada powiązania**: Zarzuty procesowe (art. 438 pkt 2) muszą być powiązane z wykazaniem wpływu na treść orzeczenia. Błąd w ustaleniach faktycznych (art. 438 pkt 3) musi wynikać z naruszenia reguł oceny dowodów.

**Zasada graduacji**: Zarzuty prezentuj od najsilniejszych (bezwzględne przyczyny odwoławcze) do najsłabszych (kara). Wnioski graduuj od najdalej idących (umorzenie) do ewentualnych (uchylenie).

**Zasada uczciwości procesowej**: Nie przemilczaj dowodów niekorzystnych — odniesienie się do nich i wyjaśnienie, dlaczego nie przesądzają o winie, jest silniejsze niż ich pominięcie.

### Zasada kaskadowości zarzutów

Jeśli stawiasz zarówno zarzuty procesowe (pkt 2) jak i błędu w ustaleniach faktycznych (pkt 3), zarzuty z pkt 3 formułuj jako KONSEKWENCJĘ naruszeń procesowych. Nie stawiaj zarzutu obrazy prawa materialnego, jeśli kwestionujesz ustalenia faktyczne.

---

### Hierarchia zarzutów (od najsilniejszych do najsłabszych)

Apelacja powinna prezentować zarzuty w następującej kolejności priorytetowej:

---

#### POZIOM 1 — Bezwzględne przyczyny odwoławcze (art. 439 § 1 k.p.k.)

Sąd odwoławczy uwzględnia je z urzędu, niezależnie od granic zaskarżenia. Jeśli zachodzą — stawiaj je na pierwszym miejscu. Najczęstsze:
- pkt 8: res iudicata (powaga rzeczy osądzonej) — postępowanie co do tego samego czynu tej samej osoby zostało już prawomocnie zakończone
- pkt 10: brak obrońcy obligatoryjnego
- pkt 11: nieobecność oskarżonego, którego obecność była obowiązkowa

##### Wzorzec formułowania zarzutu bezwzględnej przyczyny odwoławczej

```
Na podstawie art. 439 § 1 pkt [X] k.p.k.
[ewentualnie: w zw. z art. 17 § 1 pkt [Y] k.p.k.]
wyrokowi temu zarzucam, iż [opis uchybienia].
```

Ważne: bezwzględne przyczyny odwoławcze NIE wymagają wykazania wpływu na treść orzeczenia — sąd odwoławczy uwzględnia je z urzędu.

##### Art. 439 § 1 pkt 8 k.p.k. — powaga rzeczy osądzonej (res iudicata)

Najsilniejszy możliwy zarzut. Zachodzi, gdy postępowanie karne co do tego samego czynu tej samej osoby zostało już prawomocnie zakończone.

**Mechanizm argumentacji:**

1. Wykaż tożsamość podmiotową (ta sama osoba)
2. Wykaż tożsamość przedmiotową (ten sam czyn) — tu kluczowa jest argumentacja:
   - Tożsamość czasu i miejsca działania
   - Tożsamość sposobu działania
   - Tożsamość zamiaru sprawcy
   - Tożsamość chronionego dobra prawnego
3. Podkreśl, że odmienna kwalifikacja prawna NIE wyklucza tożsamości czynu
4. Powołaj się na zasadę ne bis in idem
5. Wskaż konkretne orzeczenie kończące wcześniejsze postępowanie (sygnatura, data, sąd)

**Kluczowe orzecznictwo:**
- SN, V KK 238/19: „Skazanie za czyn, który stanowi przedmiot wcześniejszego prawomocnego postępowania karnego zakończonego skazaniem, stanowi rażące naruszenie art. 17 § 1 pkt 7 k.p.k. w zw. z art. 439 § 1 pkt 8 k.p.k."
- SN, III KK 100/20: Powaga rzeczy osądzonej wyklucza ponowne orzekanie o tych samych karach jednostkowych.

**Wzorzec argumentacyjny:**
> Grzegorz X. został już prawomocnie skazany za czyn, który jest przedmiotem niniejszego postępowania.
> Z treści wyroku Sądu [X] z dnia [data], sygn. akt [sygnatura] jasno wynika, że [opis czynu z poprzedniego wyroku].
> Tymczasem zarzut stawiany oskarżonemu w niniejszym postępowaniu dotyczy identycznych działań
> podejmowanych w tym samym czasie [opis]. Opis zachowań zarzucanych w obu postępowaniach
> jest tożsamy — w obu przypadkach chodzi o [wspólny rdzeń zachowania].
> Rozdzielenie potencjalnego zamiaru sprawcy w takiej sytuacji jest obiektywnie niemożliwe.
> Odmienna kwalifikacja prawna czynu nie wyklucza tożsamości przedmiotowej
> (por. wyrok SN z 12 lutego 1975 r., I KR 226/74).

---

#### POZIOM 2 — Obraza przepisów postępowania (art. 438 pkt 2 k.p.k.)

Naruszenie przepisów proceduralnych, które MOGŁO MIEĆ WPŁYW na treść orzeczenia.

##### Wzorzec formułowania zarzutu obrazy przepisów postępowania

```
Na podstawie art. 427 § 1 i 2 k.p.k. w zw. z art. 438 pkt 2 k.p.k.
wyrokowi temu zarzucam, mającą wpływ na treść zaskarżonego wyroku,
obrazę przepisów postępowania, to jest art. [X] k.p.k.
[ewentualnie: w zw. z art. [Y] k.p.k.]
poprzez [opis naruszenia],

wyrażające się [szczegółowy opis przejawiania się naruszenia]:
- [konkretny przejaw 1]
- [konkretny przejaw 2]
```

##### Art. 7 k.p.k. — naruszenie swobodnej oceny dowodów

Najczęściej stawiany zarzut apelacyjny. Aby był skuteczny, NIE WYSTARCZY przedstawić własnej oceny dowodów — trzeba wykazać KONKRETNE błędy logiczne lub sprzeczność z doświadczeniem życiowym.

**Pięć sposobów wykazania naruszenia art. 7 k.p.k.:**

1. **Pominięcie dowodu** — sąd nie odniósł się do istotnego dowodu w uzasadnieniu
2. **Wewnętrzna sprzeczność** — sąd zaakceptował dowody wzajemnie sprzeczne bez wyjaśnienia
3. **Sprzeczność z logiką** — wnioski sądu nie wynikają z przesłanek
4. **Sprzeczność z doświadczeniem życiowym** — ustalenia są nieprawdopodobne
5. **Wybiórczość** — sąd uwzględnił tylko dowody obciążające, pomijając odciążające

**Kluczowe orzecznictwo:**
- SN, V KK 437/22: „Zarzut naruszenia art. 7 k.p.k. wymaga wykazania, że ocena dowodów przez sąd jest sprzeczna z zasadami wiedzy i doświadczenia życiowego, nie została poprzedzona ujawnieniem całokształtu okoliczności sprawy lub argumentacja sądu pozostaje w sprzeczności z logiką."
- SA, II AKa 147/12: Uchylenie wyroku uzasadnione jest, gdy sąd dokonał fragmentarycznej i dowolnej oceny dowodów, nie dostrzegając istotnych rozbieżności.

**Wzorzec argumentacyjny:**
> Sąd Rejonowy dokonał dowolnej, a nie swobodnej oceny materiału dowodowego, co wyrażało się:
>
> Po pierwsze, pominięciem dowodów świadczących o niewinności oskarżonego,
> w szczególności zeznań świadka [X], który na rozprawie w dniu [data] zeznał, że [treść].
> Sąd I instancji do zeznań tych w ogóle nie odniósł się w uzasadnieniu wyroku.
>
> Po drugie, uchybieniem zasadom logicznego rozumowania poprzez [opis].
> Z jednej strony Sąd ustala, że [ustalenie A], z drugiej zaś przyjmuje, że [ustalenie B],
> co pozostaje ze sobą w oczywistej sprzeczności.

##### Art. 4 k.p.k. — naruszenie zasady obiektywizmu

Zarzut stawia się, gdy sąd jednostronnie ocenił materiał dowodowy na niekorzyść oskarżonego, pomijając dowody i okoliczności przemawiające na jego korzyść. Zarzut ten wzmacnia inne zarzuty procesowe (szczególnie art. 7 i art. 410 k.p.k.).

##### Art. 5 § 2 k.p.k. — in dubio pro reo

UWAGA: Zarzut naruszenia art. 5 § 2 k.p.k. ma charakter ROZŁĄCZNY od art. 7 k.p.k. Stosuje się go, gdy MIMO prawidłowej oceny dowodów pozostają niedające się usunąć wątpliwości, które sąd rozstrzygnął na niekorzyść oskarżonego. Nie wolno łączyć w jednym zarzucie naruszenia obu tych przepisów jako alternatywy.

##### Art. 410 k.p.k. — nieuwzględnienie całokształtu okoliczności

**Mechanizm argumentacji:**
- Wskaż KONKRETNY dowód ujawniony na rozprawie, który sąd pominął
- Wykaż, że dowód ten ma istotne znaczenie dla rozstrzygnięcia
- Nie chodzi o to, że sąd nie oparł się na tym dowodzie, ale że go w ogóle nie rozważył

##### Art. 424 § 1 k.p.k. — braki uzasadnienia

**Mechanizm argumentacji:**
- Wskaż, jakich elementów brakuje w uzasadnieniu (np. brak odniesienia do konkretnego dowodu, brak wyjaśnienia podstawy prawnej)
- Powiąż braki z niemożnością kontroli instancyjnej
- Ewentualnie wnioskuj o uzupełnienie uzasadnienia na podstawie art. 449a k.p.k.

##### Art. 170 § 1 k.p.k. — bezpodstawne oddalenie wniosku dowodowego

**Mechanizm argumentacji:**
- Wskaż wniosek dowodowy, który został oddalony
- Podaj tezę dowodową
- Wykaż, że podstawa oddalenia była wadliwa (np. dowód nie zmierzał do przedłużenia postępowania)
- Podkreśl art. 170 § 1a k.p.k. — nie można oddalić wniosku na podst. pkt 5 lub 6, jeśli okoliczność ma istotne znaczenie dla ustalenia, czy popełniono czyn zabroniony

##### Art. 6 k.p.k. — naruszenie prawa do obrony

**Mechanizm argumentacji:**
- Uniemożliwienie złożenia wyjaśnień
- Ograniczenie dostępu do akt
- Uniemożliwienie przygotowania się do głosów końcowych
- Nieuzasadnione przyspieszanie postępowania kosztem uprawnień obrony

---

#### POZIOM 3 — Błąd w ustaleniach faktycznych (art. 438 pkt 3 k.p.k.)

Błędne ustalenie faktów przyjętych za podstawę wyroku, który mógł mieć wpływ na treść orzeczenia.

##### Wzorzec formułowania zarzutu błędu w ustaleniach faktycznych

```
Na podstawie art. 427 § 1 i 2 k.p.k. w zw. z art. 438 pkt 3 k.p.k.
wyrokowi temu zarzucam, mający wpływ na treść wyroku,
błąd w ustaleniach faktycznych przyjętych za jego podstawę poprzez:

[wariant A — pominięcie istotnych okoliczności:]
pominięcie istotnych dla sprawy okoliczności wynikających
z przeprowadzonych dowodów, a w szczególności: [wyliczenie]

[wariant B — ustalenie faktów niewynikających z dowodów:]
ustalenie faktów, które nie wynikają z pozyskanych dowodów,
a w szczególności, iż [ustalenie sądu], podczas gdy w rzeczywistości
[stan rzeczywisty wynikający z dowodów]
```

##### Błąd „braku" — pominięcie istotnych okoliczności

**Struktura argumentacji:**
1. Wskaż ustalenie sądu
2. Wskaż KONKRETNY dowód, z którego wynika inna okoliczność
3. Wykaż, że okoliczność ta jest istotna dla rozstrzygnięcia
4. Pokaż, do jakiego prawidłowego ustalenia prowadziłoby uwzględnienie tego dowodu

##### Błąd „dowolności" — ustalenia sprzeczne z dowodami

**Struktura argumentacji z techniką „podczas gdy w rzeczywistości":**

> Sąd I instancji błędnie ustalił, że [ustalenie sądu],
> **podczas gdy w rzeczywistości** z [dowodu X] jednoznacznie wynika, że [stan rzeczywisty].

Technikę tę stosuj systematycznie, punkt po punkcie, dla KAŻDEGO kwestionowanego ustalenia. Tworzy to obraz systematycznej wadliwości ustaleń sądu.

##### Rozróżnienie strony przedmiotowej i podmiotowej

W sprawach o przestępstwa umyślne szczególnie ważne jest rozróżnienie:
- Ustalenia co do **strony przedmiotowej** (czy dany czyn obiektywnie nastąpił) — wynikają z dowodów rzeczowych, dokumentów, zeznań
- Ustalenia co do **strony podmiotowej** (zamiar, świadomość, wina) — NIE MOGĄ być automatycznie wywodzone z samego faktu zaistnienia znamion przedmiotowych

**Kluczowe orzecznictwo:**
- SN, V KKN 426/00 (postanowienie z 23.05.2002): „Wymagana jako warunek odpowiedzialności karnej umyślność zachowania się sprawcy nie może być wywodzona z samego faktu zaistnienia znamion strony przedmiotowej danego czynu skarbowego. Nie można jej domniemywać, lecz należy ją udowodnić."

---

#### POZIOM 4 — Obraza prawa materialnego (art. 438 pkt 1 i 1a k.p.k.)

Wadliwa kwalifikacja prawna czynu przy NIEKWESTIONOWANYCH ustaleniach faktycznych.

##### Zasady formułowania

Zarzut obrazy prawa materialnego można stawiać WYŁĄCZNIE, gdy:
- Akceptujesz ustalenia faktyczne sądu I instancji
- Kwestionujesz jedynie subsumpcję (przyporządkowanie prawne) ustalonych faktów

NIE stawiaj zarzutu obrazy prawa materialnego jednocześnie z zarzutem błędu w ustaleniach faktycznych co do tych samych okoliczności — to błąd konstrukcyjny apelacji.

---

#### POZIOM 5 — Rażąca niewspółmierność kary (art. 438 pkt 4 k.p.k.)

Kara rażąco surowa lub rażąco łagodna — stosować jako zarzut ewentualny lub uzupełniający.

##### Wzorzec formułowania zarzutu rażącej niewspółmierności kary

```
Na podstawie art. 427 § 1 i 2 k.p.k. w zw. z art. 438 pkt 4 k.p.k.
wyrokowi temu zarzucam rażącą niewspółmierność orzeczonej kary
[pozbawienia wolności / grzywny / ograniczenia wolności]
poprzez wymierzenie kary [X], podczas gdy prawidłowa ocena
okoliczności sprawy, w tym [okoliczności łagodzące],
uzasadnia wymierzenie kary [Y] / zastosowanie [warunkowego zawieszenia
wykonania kary / kary wolnościowej].
```

##### Mechanizm argumentacji dotyczącej kary

1. Wskaż okoliczności łagodzące pominięte lub niedostatecznie uwzględnione przez sąd
2. Odnieś się do dyrektyw wymiaru kary z art. 53 k.k.
3. Porównaj z wymiarem kary w podobnych sprawach (orzecznictwo)
4. Wykaż, że kara jest rażąco (nie zaledwie) niewspółmierna
5. Jeśli kara jest bez warunkowego zawieszenia — argumentuj za pozytywną prognozą kryminologiczną

**Wzorzec argumentacyjny:**
> Przy prawidłowym ustaleniu [okoliczności], społeczna szkodliwość czynu jest istotnie niższa,
> co powinno wpłynąć na wymiar kary. Wartość naprawionej szkody w proporcji do uszczuplenia
> jest znacząca, co powinno wpłynąć na prognozę kryminologiczną i rozstrzygnięcie
> co do środków probacyjnych.

---

## KROK 3 — Napisz apelację

### Struktura dokumentu

Apelacja musi zawierać następujące elementy, w tej kolejności:

```
1. NAGŁÓWEK
   - Miejscowość i data
   - Oznaczenie sądu odwoławczego (adresat)
   - „za pośrednictwem" + oznaczenie sądu I instancji
   - Sygnatura akt I instancji
   - Dane skarżącego (oskarżony/obrońca/oskarżyciel)

2. TYTUŁ
   „APELACJA" + wskazanie od jakiego wyroku, czyja, w czyim imieniu

3. PETITUM — ZASKARŻENIE
   Formuła: „Działając jako [obrońca/oskarżony], na podstawie art. 444 k.p.k.
   oraz art. 447 § 1 [i 2] k.p.k. — zaskarżam powyższy wyrok
   [w całości / w części dotyczącej ...] [na korzyść oskarżonego]."

4. ZARZUTY
   Każdy zarzut z PRECYZYJNĄ podstawą prawną:
   „Na podstawie art. 427 § 1 i 2 k.p.k. w zw. z art. 438 pkt [X] k.p.k.
   wyrokowi temu zarzucam: [treść zarzutu]"

5. WNIOSKI APELACYJNE
   Na podstawie art. 427 § 1 k.p.k. w zw. z art. 437 § 1 [i 2] k.p.k.
   — graduowane od najdalej idącego do ewentualnego:
   a) umorzenie postępowania (jeśli jest przesłanka z art. 17 § 1 k.p.k.)
   b) zmiana wyroku i uniewinnienie
   c) uchylenie wyroku i przekazanie do ponownego rozpoznania
   d) zmiana wyroku co do kary

6. WNIOSKI DOWODOWE (jeśli są)
   Na podstawie art. 427 § 3 k.p.k. — nowe fakty lub dowody

7. WNIOSEK O UZUPEŁNIENIE UZASADNIENIA (jeśli potrzebny)
   Na podstawie art. 449a k.p.k.

8. UZASADNIENIE
   Rozbudowane, ze strukturą odpowiadającą kolejności zarzutów

9. ZAŁĄCZNIKI
```

---

### Wnioski apelacyjne i dowodowe — szczegółowo

#### Graduacja wniosków

Wnioski apelacyjne ZAWSZE graduuj od najdalej idącego do ewentualnego:

1. **Umorzenie** (jeśli zachodzi przesłanka z art. 17 § 1 k.p.k.)
2. **Zmiana wyroku i uniewinnienie** — na podst. art. 437 § 2 k.p.k. (orzeczenie odmienne co do istoty)
3. **Uchylenie wyroku i przekazanie do ponownego rozpoznania** — możliwe wyłącznie w wypadkach z art. 439 § 1, art. 454 lub konieczności przeprowadzenia na nowo przewodu w całości
4. **Zmiana wyroku co do kary** — jeśli zarzut dotyczy wyłącznie wymiaru kary

Każdy wniosek „niższy" wprowadzaj formułą:
> „ewentualnie, z najdalej idącej ostrożności procesowej wnoszę o..."

#### Wnioski dowodowe (art. 427 § 3 k.p.k.)

Nowe dowody w apelacji dopuszczalne są, jeśli skarżący nie mógł powołać ich w I instancji. Każdy wniosek dowodowy zawiera:
- Oznaczenie dowodu
- Tezę dowodową (formułka: „celem wykazania, że...")
- Uzasadnienie, dlaczego nie można było powołać go wcześniej (jeśli potrzebne)
- Ewentualny wniosek o uzyskanie dowodu (np. wystąpienie do instytucji o dokumenty)

---

### Mechanizmy argumentacji w uzasadnieniu

Uzasadnienie stanowi rdzeń apelacji. Stosuj następujące techniki argumentacyjne:

#### A. Kontrastowanie ustaleń sądu z rzeczywistością

Technika „podczas gdy w rzeczywistości" — zestawienie ustalenia sądu z materiałem dowodowym w formie bezpośredniego kontrastu:
- Przytocz ustalenie sądu I instancji (najlepiej cytatem z uzasadnienia)
- Przeciwstaw mu konkretny dowód lub fakt z akt sprawy
- Pokaż sprzeczność logiczną

Każdy punkt rozpoczynaj od ustalenia sądu, a następnie przeciwstaw mu dowód lub fakt.

Przykładowy wzorzec:
> „Sąd Rejonowy ustalił, że oskarżony [X], podczas gdy w rzeczywistości z [dowodu Y]
> jednoznacznie wynika, że [Z]. Sąd I instancji okoliczności tej nie dostrzegł /
> nie odniósł się do niej w uzasadnieniu, co stanowi naruszenie art. 410 k.p.k."

#### B. Obrócenie argumentu sądu przeciwko niemu

Wykorzystanie własnych ustaleń lub stwierdzeń sądu przeciwko jego konkluzji:
> „Jak podkreśla sam Sąd I instancji [cytat z uzasadnienia], co stoi
> w sprzeczności z ustaleniem, że [konkluzja sądu]."

#### C. Analiza systematyczna materiału dowodowego (technika „systematycznej dekonstrukcji")

Gdy kwestionujesz ocenę dowodów:
- Przeanalizuj KAŻDY istotny dowód z osobna
- Pokaż, które dowody sąd pominął
- Wskaż wewnętrzne sprzeczności w rozumowaniu sądu
- Użyj tabeli lub wyliczenia, jeśli dowodów jest wiele

Analiza KAŻDEGO elementu uzasadnienia sądu z osobna, wykazanie wadliwości w każdym z nich — tworzy obraz całościowej wadliwości rozstrzygnięcia.

#### D. Odwołanie do zasad procesowych z orzecznictwem

Dla każdego zarzutu procesowego:
- Zacytuj treść naruszonego przepisu
- Przytocz relewantne orzeczenie SN lub sądu apelacyjnego z tezą
- Pokaż, jak konkretnie sąd I instancji naruszył ten standard

Wzorzec:
> „Zgodnie z postanowieniem Sądu Najwyższego z dnia [data], sygn. akt [sygnatura]:
> «[teza]». Tymczasem Sąd I instancji [opis naruszenia]."

#### E. Argumentacja kaskadowa (od głównego do ewentualnego)

Zaczynaj od najsilniejszego argumentu. Słabsze wprowadzaj formułą:
> „W dalszej kolejności — wobec ewentualnie odmiennego poglądu Sądu Odwoławczego
> co do zarzutu określonego w punkcie [X] — wskazuję, że..."

lub:
> „Z najdalej posuniętej ostrożności procesowej..."

#### F. Dowodzenie przez eliminację

Wskazanie, że po wyeliminowaniu wadliwie ocenionych dowodów nie pozostaje materiał wystarczający do skazania:
> „Po wyeliminowaniu z podstawy dowodowej [dowodu X] ocenionego z naruszeniem art. 7 k.p.k.,
> nie istnieje żaden dowód pozwalający na ustalenie, że oskarżony [znamię czynu]."

#### G. Argumentacja dotycząca strony podmiotowej

W sprawach, w których kluczowa jest umyślność/zamiar:
- Rozróżnij ustalenia co do strony przedmiotowej (obiektywne fakty) od strony podmiotowej (zamiar, świadomość)
- Podkreśl, że umyślności nie można domniemywać z samego faktu zaistnienia znamion przedmiotowych
- Powołaj się na orzecznictwo SN w tym zakresie

#### H. Hierarchia postępowań

Rozróżnienie między reżimem postępowania administracyjnego/podatkowego a karnego:
> „Inny jest reżim postępowania podatkowego, inny karnego. Ustalenie w postępowaniu
> administracyjnym, że dana faktura jest nierzetelna, nie oznacza automatycznie
> w postępowaniu karnym, że wystawca faktury miał tego świadomość."

#### I. Argumentacja dotycząca wymiaru kary

Jeśli zarzut dotyczy rażącej niewspółmierności:
- Wskaż konkretne okoliczności łagodzące pominięte przez sąd
- Pokaż dysproporcję w stosunku do kar wymierzanych w podobnych sprawach
- Odnieś się do dyrektyw z art. 53 k.k.

#### J. Technika „ostrożności procesowej"

Wprowadzanie zarzutów ewentualnych formułą:
> „Z najdalej posuniętej ostrożności procesowej wskazać należy, iż jeśli Sąd Odwoławczy
> z wnioskiem tym nie zgodzi się, jedyną możliwością do uzyskania stanu zgodności
> z prawem będzie [żądanie alternatywne]."

---

### Styl i język

- Pisz w trzeciej osobie: „skarżący wskazuje", „obrońca podnosi"
- Używaj formalnego języka prawniczego, ale pisz klarownie
- Każde twierdzenie podpieraj przepisem lub dowodem
- Nie powtarzaj tych samych argumentów w różnych częściach
- Cytaty z uzasadnienia wyroku lub zeznań wyodrębniaj kursywą
- Stosuj podkreślenia dla kluczowych fragmentów argumentacji
- NIE OGRANICZAJ długości uzasadnienia — pisz tak obszernie, jak wymaga tego kompleksowość sprawy

### Wymogi formalne

- Jeśli apelację od wyroku sądu okręgowego składa ktoś inny niż prokurator — musi być sporządzona i podpisana przez adwokata lub radcę prawnego (art. 446 § 1 k.p.k.)
- Termin: 14 dni od doręczenia wyroku z uzasadnieniem (art. 445 § 1 k.p.k.)
- Apelację wnosi się do sądu, który wydał wyrok (art. 428 § 1 k.p.k.)
- Dołączyć odpisy dla stron przeciwnych (art. 446 § 2 k.p.k.)

---

## KROK 4 — Wygeneruj dokument .docx

Przeczytaj SKILL.md dotyczący tworzenia dokumentów .docx i wygeneruj profesjonalny dokument Word z:
- Nagłówkiem kancelarii/danych skarżącego
- Poprawnym formatowaniem prawniczym (numeracja punktów, wcięcia, kursywa dla cytatów)
- Stronicowaniem i marginesami zgodnymi z praktyką sądową

---

## KROK 5 — Weryfikacja

Po wygenerowaniu apelacji zweryfikuj:
1. Czy każdy zarzut ma prawidłową podstawę prawną (art. 438 pkt X w zw. z konkretnym przepisem)
2. Czy wnioski korespondują z zarzutami
3. Czy uzasadnienie odnosi się do KAŻDEGO postawionego zarzutu
4. Czy powołane orzecznictwo jest relewantne (sygnatury, daty)
5. Czy zastosowano prawidłową hierarchię zarzutów
6. Czy wymogi formalne są spełnione (adresat, termin, pełnomocnictwo)

---

## Kluczowe przepisy k.p.k. — zestawienie referencyjne

### Przepisy o zaskarżeniu
- **Art. 425 § 1-3 k.p.k.** — prawo do zaskarżenia, zakres
- **Art. 427 § 1-3 k.p.k.** — wymogi formalne środka odwoławczego
- **Art. 444 § 1 k.p.k.** — prawo do apelacji od wyroku I instancji
- **Art. 445 § 1 k.p.k.** — termin 14 dni
- **Art. 446 § 1 k.p.k.** — przymus adwokacko-radcowski przy apelacji od wyroku SO
- **Art. 447 § 1-3 k.p.k.** — zakres zaskarżenia (co do winy = cały wyrok)

### Podstawy uchylenia/zmiany
- **Art. 437 § 1-2 k.p.k.** — rodzaje rozstrzygnięć sądu odwoławczego
- **Art. 438 pkt 1-4 k.p.k.** — podstawy uchylenia lub zmiany
- **Art. 439 § 1 k.p.k.** — bezwzględne przyczyny odwoławcze

### Zasady procesowe (naruszane w zarzutach)
- **Art. 4 k.p.k.** — zasada obiektywizmu
- **Art. 5 § 1-2 k.p.k.** — domniemanie niewinności, in dubio pro reo
- **Art. 6 k.p.k.** — prawo do obrony
- **Art. 7 k.p.k.** — swobodna ocena dowodów
- **Art. 410 k.p.k.** — podstawa wyroku = całokształt okoliczności z rozprawy
- **Art. 424 § 1 k.p.k.** — wymogi uzasadnienia

### Przesłanki procesowe
- **Art. 17 § 1 k.p.k.** — negatywne przesłanki procesowe (katalog zamknięty)

---

## Orzecznictwo wzorcowe — zestawienie referencyjne

### Swobodna ocena dowodów (art. 7 k.p.k.)
- **SN, V KK 437/22 z 16.02.2023** — standard wykazania naruszenia art. 7 k.p.k.
- **SN, V KK 119/14 z 04.06.2014** — rozłączność art. 5 § 2 i art. 7 k.p.k.
- **SA, II AKa 92/13 z 06.06.2013** — ocena powierzchowna i wybiórcza jako naruszenie art. 7 k.p.k.
- **SA, XI Ka 1263/14 z 05.02.2015** — obowiązek wszechstronnej analizy i logicznego uzasadnienia

### Kontrola odwoławcza
- **SN, V KK 443/14 z 24.02.2015** — standard kontroli instancyjnej
- **SN, IV KK 408/13 z 19.02.2014** — wymogi uzasadnienia orzeczenia reformatoryjnego

### Res iudicata i ne bis in idem
- **SN, V KK 238/19 z 25.07.2019** — uchylenie wyroku i umorzenie z powodu res iudicata
- **SN, IV KK 425/21 z 02.06.2022** — tożsamość czynu w kontekście transgranicznym
- **SN, V KK 270/14 z 21.01.2015** — orzeczenie oparte na względnej przesłance procesowej nie tworzy res iudicata

### Strona podmiotowa / umyślność
- **SN, V KKN 426/00 z 23.05.2002** — umyślności nie można domniemywać z samego faktu zaistnienia znamion przedmiotowych

### Wymiar kary
- **SN, V KK 359/17 z 09.11.2017** — granice tożsamości czynu a kwalifikacja prawna
- Orzecznictwo sądów powszechnych w danej kategorii spraw — wyszukuj dynamicznie przez Search_SP

---

## Uwaga końcowa

Powyższe mechanizmy argumentacyjne, wzorce formułowań i orzecznictwo stanowią zestaw narzędzi referencyjnych. W konkretnej apelacji dobieraj je odpowiednio do stanu faktycznego i zarzutów. ZAWSZE wyszukuj aktualne orzecznictwo przez narzędzia MCP (Search_SN, Search_SP, Search_DU) — powyższe sygnatury stanowią punkt wyjścia, ale orzecznictwo ewoluuje i w konkretnej sprawie mogą być bardziej relewantne inne orzeczenia.
