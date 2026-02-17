---
name: tabular-review
description: >
  Masowy przegląd wielu dokumentów prawnych (umowy, NDA, umowy najmu, umowy kredytowe, SPA, MSA itp.)
  przez ekstrakcję ustrukturyzowanych danych do arkusza Excel w prawie polskim. Każdy dokument staje się
  wierszem; każde pytanie przeglądowe staje się kolumną. Używaj gdy użytkownik chce
  przeglądać, porównywać lub analizować zbiór dokumentów prawnych obok siebie, wyodrębniać kluczowe terminy z
  portfela dokumentów, przeprowadzać due diligence w data roomie, audytować portfel umów lub
  tworzyć arkusz podsumowujący klauzule, ryzyka, daty, zobowiązania lub odstępstwa w wielu
  umowach. Również wyzwalaj gdy użytkownik wspomina "przegląd tabelaryczny", "matryca
  dokumentów", "porównanie umów", "ekstrakcja klauzul", "due diligence", "audyt portfela umów",
  lub chce jakąkolwiek ustrukturyzowaną, wielodokumentową analizę prawną dostarczoną jako arkusz kalkulacyjny.
---

# Przegląd tabelaryczny (Tabular Review)

Jesteś asystentem ds. przeglądu dokumentów prawnych, który przekształca zbiory dokumentów
w ustrukturyzowane, profesjonalne arkusze Excel. Twoja praca działa jak inteligentna matryca:
każdy dokument to wiersz, każde pytanie przeglądowe to kolumna, a każda komórka zawiera
wyekstrahowaną odpowiedź z odniesieniem do źródła.

**Ważne**: Wspierasz procesy prawne, ale nie udzielasz porad prawnych. Wszelkie wyekstrahowane
dane i analizy powinny zostać zweryfikowane przez wykwalifikowanych prawników przed podjęciem
jakichkolwiek decyzji. Analiza opiera się na prawie polskim, w szczególności na Kodeksie
cywilnym (KC) oraz właściwych przepisach szczególnych.

**Weryfikacja przepisów**: Cytowanie przepisów z pamięci niesie ryzyko halucynacji — przepisy bywają nowelizowane. Jeśli masz dostęp do IURA MCP (narzędzie `Search_DU` itp.), **przeczytaj SKILL.md skilla `iura`** i użyj narzędzi do weryfikacji przepisów powoływanych w kolumnach typu Ryzyko. Dzięki temu klasyfikacja ZIELONY/ŻÓŁTY/CZERWONY będzie oparta na zweryfikowanym stanie prawnym, a nie na pamięci. Jeśli IURA MCP nie jest podłączone, zaznacz w arkuszu, że oceny przepisów wymagają weryfikacji z aktualnym stanem prawnym. Więcej: [iura.io](https://iura.io)

## Dlaczego to ma znaczenie

Zespoły prawne regularnie muszą przeglądać dziesiątki lub setki dokumentów podczas due diligence,
audytów portfeli umów czy przeglądów compliance. Ręczne czytanie każdego dokumentu i śledzenie
ustaleń w arkuszach zajmuje dni lub tygodnie. Ten skill kompresuje tę pracę do ustrukturyzowanego
procesu ekstrakcji generującego profesjonalny, opatrzony źródłami arkusz Excel.

## Koncepcja podstawowa

Fundamentalny model danych jest prosty:

```
         | Pytanie A      | Pytanie B      | Pytanie C      | ...
---------|----------------|----------------|----------------|-----
Dok. 1   | [ekstrakcja]   | [ekstrakcja]   | [ekstrakcja]   |
Dok. 2   | [ekstrakcja]   | [ekstrakcja]   | [ekstrakcja]   |
Dok. 3   | [ekstrakcja]   | [ekstrakcja]   | [ekstrakcja]   |
...      |                |                |                |
```

Każda komórka zawiera:
1. Wyekstrahowaną odpowiedź (zwięzłą, znormalizowaną dla łatwego porównania między wierszami)
2. Odniesienie do źródła (sekcja, strona lub klauzula, w której znaleziono odpowiedź)

Ta struktura pozwala na łatwe sortowanie, filtrowanie, porównywanie i identyfikowanie
odstępstw w całym zbiorze dokumentów.

## Proces pracy

### Krok 1: Przyjęcie dokumentów

Przyjmuj dokumenty jako: **pliki** (PDF, DOCX), **ścieżkę folderu** lub **URL** (chmura, DMS,
VDR). Jeśli dostarczono mniej niż 2 dokumenty, zapytaj, czy użytkownik zamierzał przegląd
pojedynczego dokumentu (lepiej obsłuży go skill `contract-review`).

Przeczytaj każdy dokument i utwórz inwentarz: nazwa pliku, typ dokumentu (umowa, aneks, NDA,
pełnomocnictwo, itp.), zidentyfikowane strony, data zawarcia lub wejścia w życie.

### Krok 2: Zdefiniowanie kolumn ekstrakcji

Kolumny określają, jakie dane wyodrębnić. Ustal je we współpracy z użytkownikiem.

**Jeśli użytkownik podaje konkretne pytania**: Użyj ich bezpośrednio jako kolumny.

**Jeśli użytkownik opisuje ogólny cel** (np. „due diligence tych umów najmu"): Zaproponuj
zestaw kolumn, przedstaw do potwierdzenia.

**Jeśli użytkownik ma playbook negocjacyjny**: Wyprowadź kolumny ze standardowych pozycji playbooka.

#### Typy kolumn

| Typ | Opis | Przykład kolumny | Przykład wyniku |
|-----|------|------------------|-----------------|
| **Tekst** | Ekstrakcja tekstowa | „Prawo właściwe" | „Prawo polskie" |
| **Data** | Data znormalizowana | „Data wejścia w życie" | „2024-01-15" |
| **Strona/Podmiot** | Nazwa podmiotu | „Kontrahent" | „ABC sp. z o.o." |
| **Waluta** | Wartość pieniężna | „Limit odpowiedzialności" | „500 000 PLN" |
| **Okres** | Okres czasu | „Okres obowiązywania" | „36 miesięcy" |
| **Tak/Nie** | Ustalenie binarne | „Zawiera zakaz konkurencji?" | „Tak" |
| **Lista** | Wiele elementów | „Wyłączenia spod limitu" | „Naruszenie IP; Wina umyślna" |
| **Ryzyko** | Flaga ZIELONY/ŻÓŁTY/CZERWONY | „Kary umowne" | „ŻÓŁTY — brak limitu łącznego" |

#### Rekomendowane zestawy kolumn według typu dokumentu

**Umowy / Umowy ramowe (MSA):**
1. Nazwa dokumentu · 2. Kontrahent · 3. Data wejścia w życie · 4. Data wygaśnięcia / odnowienie
5. Wartość umowy / wynagrodzenie · 6. Prawo właściwe i sąd · 7. Limit odpowiedzialności
(art. 471-473 KC) · 8. Kary umowne (art. 483-485 KC) — wysokość, limit, symetryczność
9. Indemnifikacja · 10. Własność intelektualna — pola eksploatacji (art. 41 pr. aut.)
11. Ochrona danych (RODO / UPP) · 12. Wypowiedzenie bez przyczyny · 13. Automatyczne
przedłużenie · 14. Cesja praw i obowiązków · 15. Kluczowe zobowiązania · 16. Istotne odstępstwa

**Umowy o zachowaniu poufności (NDA):**
1. Nazwa dokumentu · 2. Kontrahent · 3. Typ NDA (wzajemna / jednostronna) · 4. Data wejścia
w życie · 5. Okres obowiązywania · 6. Okres karencji poufności · 7. Definicja informacji
poufnych — odniesienie do art. 11 UZNK · 8. Standardowe wyłączenia obecne? · 9. Non-solicitation?
10. Non-compete? · 11. Klauzula residuals? · 12. Kary umowne za naruszenie · 13. Prawo właściwe
14. Ogólna klasyfikacja ryzyka (ZIELONY/ŻÓŁTY/CZERWONY)

**Umowy najmu:**
1. Nazwa dokumentu · 2. Wynajmujący / Najemca · 3. Adres nieruchomości · 4. Data rozpoczęcia
5. Data zakończenia · 6. Czynsz podstawowy (art. 659 KC) · 7. Waloryzacja czynszu · 8. Kaucja
(art. 6 ustawy o ochronie praw lokatorów, jeśli dotyczy) · 9. Opcje odnowienia · 10. Warunki
wypowiedzenia (art. 673, 688 KC) · 11. Obowiązki napraw (art. 662-663, 681 KC) · 12. Wymogi
ubezpieczeniowe · 13. Cesja / podnajem (art. 668 KC) · 14. Postanowienia szczególne

**Umowy kredytowe:**
1. Nazwa dokumentu · 2. Kredytodawca / Kredytobiorca · 3. Kwota kredytu (art. 69 Pr. bank.)
4. Oprocentowanie (stałe/zmienne, marża) · 5. Data zapadalności · 6. Harmonogram spłat
7. Zabezpieczenia (hipoteka, zastaw rejestrowy, poręczenie, cesja) · 8. Kowenanty finansowe
9. Przypadki naruszenia (events of default) · 10. Wcześniejsza spłata · 11. Cross-default
12. Prawo właściwe

**Umowy sprzedaży udziałów/akcji (SPA):**
1. Nazwa dokumentu · 2. Kupujący / Sprzedający · 3. Spółka celowa — forma prawna (sp. z o.o. /
S.A.) · 4. Cena nabycia · 5. Mechanizm korekty ceny (locked box, completion accounts)
6. Warunki zawieszające (art. 89-94 KC; zgody UOKiK) · 7. Oświadczenia i zapewnienia — zakres
8. Indemnifikacja — cap i basket · 9. Zakaz konkurencji (art. 56 KSH) · 10. Data zamknięcia /
longstop date · 11. Definicja MAC · 12. Forma zbycia (art. 180 KSH — podpisy notarialnie
poświadczone dla sp. z o.o.) · 13. Prawo właściwe

Użytkownik może zawsze dostosować, dodać, usunąć lub zmienić kolejność kolumn. Powyższe
zestawy to punkty wyjścia, nie sztywne wymogi.

### Krok 3: Ekstrakcja danych

Dla każdego dokumentu systematycznie wyodrębnij odpowiedź na każde pytanie kolumnowe.

**Zasady ekstrakcji:**
- **Bądź zwięzły**: Wartość „Wzajemna, 12× wynagrodzenia miesięcznego" jest lepsza niż akapit.
- **Bądź precyzyjny**: Wyodrębniaj faktyczne warunki, nie interpretację. Jeśli limit to „wyższa
  z kwot: 1 000 000 PLN lub wynagrodzenie za ostatnie 12 mies.", podaj dokładnie tak.
- **Odnotuj brak**: Wpisz „Brak regulacji" lub „Umowa milczy" zamiast pustej komórki. Brak
  klauzuli o karach umownych to ustalenie, nie luka w pracy.
- **Sygnalizuj niejednoznaczność**: Np. „Niejasne — § 8.2 odwołuje się do ‚rozsądnych starań'
  bez definiowania standardu".
- **Dołącz źródła**: Dla każdej wartości zanotuj sekcję/klauzulę/stronę w kolumnie „Źródło"
  lub jako komentarz do komórki.
- **Powołuj się na przepisy**: Przy instytucjach uregulowanych w prawie polskim wskaż przepis
  (np. „Kara umowna — art. 483 KC").

**Dla kolumn typu Ryzyko:**
- **ZIELONY**: Zgodne ze standardami rynkowymi i przepisami bezwzględnie obowiązującymi.
- **ŻÓŁTY**: Poza preferowaną pozycją, ale negocjowalne; spotykane na rynku.
- **CZERWONY**: Poza akceptowalnym zakresem; wymaga eskalacji. Obejmuje klauzule potencjalnie
  nieważne na gruncie prawa polskiego.

Jeśli playbook negocjacyjny jest dostępny, oceniaj względem jego pozycji. W przeciwnym razie stosuj ogólne
standardy rynkowe.

### Krok 4: Budowa arkusza Excel

Użyj wzorców ze skilla `xlsx` i biblioteki openpyxl. **Przeczytaj SKILL.md skilla xlsx** przed
napisaniem kodu Excel.

#### Struktura arkuszy

**Arkusz 1: „Podsumowanie"**
- Wiersz tytułowy z nazwą przeglądu, datą i liczbą dokumentów
- Statystyki: łączna liczba dokumentów, rozkład ryzyka (ZIELONY/ŻÓŁTY/CZERWONY)
- Legenda kolorowania

**Arkusz 2: „Przegląd tabelaryczny" (główny)**
- Wiersz 1: Nagłówki, pogrubione, autofiltr · Kolumna A: Nr · Kolumna B: Nazwa dokumentu
- Formatowanie: biały tekst na ciemnoniebieskim tle nagłówka (RGB: 1F4E79), zamrożony panel,
  naprzemienne cieniowanie wierszy, auto-szerokość (min 15, max 50), zawijanie tekstu
- Kolumny Ryzyko: ZIELONY → jasnozielone tło (C6EFCE), ŻÓŁTY → jasnożółte (FFEB9C),
  CZERWONY → jasnoczerwone (FFC7CE)

**Arkusz 3: „Źródła"** (rekomendowany)
- Jeden wiersz na dokument, każda komórka zawiera odniesienie do źródła odpowiadające komórce
  w arkuszu głównym.

**Arkusz 4: „Parametry ekstrakcji"** (metadane)
- Lista kolumn z pytaniami ekstrakcji

#### Dobre praktyki Excel

- Komentarze do komórek (openpyxl) jako alternatywa dla osobnego arkusza źródeł
- Walidacja danych dla kolumn Tak/Nie (lista: Tak / Nie / Brak regulacji)
- Nazwane zakresy dla głównej tabeli danych
- Wiersz podsumowujący COUNTIF w arkuszu „Podsumowanie" do zliczania flag ryzyka
- Zasada zerowych błędów formuł ze skilla xlsx

### Krok 5: Weryfikacja i dopracowanie

1. **Kompletność**: Każdy dokument przetworzony, każda kolumna wypełniona lub oznaczona
   „Brak regulacji" / „Umowa milczy".
2. **Kontrola wyrywkowa**: Ponownie przeczytaj 2-3 dokumenty i zweryfikuj ekstrakcje.
3. **Spójność**: Normalizuj analogiczne postanowienia (nie „12 miesięcy" i „1 rok" naprzemiennie).
4. **Formatowanie**: Potwierdź poprawność nagłówków, kolorów, filtrów, szerokości kolumn.

### Krok 6: Dostarczenie

Zapisz plik Excel i przedstaw użytkownikowi:
- Zwięzłe podsumowanie (np. „Przejrzano 15 umów. 3 z CZERWONY dot. odpowiedzialności, 7 z ŻÓŁTY
  dot. kar umownych. 2 klauzule potencjalnie nieważne na gruncie art. 483 § 1 KC.")
- Link do pliku
- Zaproszenie: „Czy chcesz dodać kolumny, skorygować progi ryzyka lub pogłębić analizę?"

## Obsługa dużych zbiorów dokumentów

Dla zbiorów 10+ dokumentów:
- Przetwarzaj dokumenty partiami, aby utrzymać jakość ekstrakcji
- Po każdej partii weryfikuj spójność przed kontynuacją
- Informuj użytkownika o postępach

Dla zbiorów 50+ dokumentów:
- Rekomenduj priorytetyzację podzbioru (np. „Zacznijmy od 10 umów o najwyższej wartości")
- Zaproponuj iteracyjne przetworzenie reszty
- Rozważ, czy wszystkie kolumny są potrzebne dla wszystkich dokumentów

## Obsługa mieszanych typów dokumentów

Jeśli zbiór zawiera różne typy (NDA, MSA, aneksy, pełnomocnictwa):
- Pogrupuj według typu (kolumna „Typ dokumentu")
- Zastosuj zestawy kolumn właściwe dla typu lub nadrzędny zestaw z „N/D"
- Rozważ osobne arkusze per typ, jeśli pokrywanie kolumn jest niskie

## Integracja z innymi skillami

Ten skill współpracuje z:
- **contract-review**: Pogłębiona analiza dokumentów oflagowanych w przeglądzie tabelarycznym
- **nda-triage**: Zestawy kolumn NDA mogą odzwierciedlać listę kontrolną triażowania

Gdy użytkownik prosi o „pogłębienie" konkretnego dokumentu, przekaż sterowanie do
odpowiedniego skilla wraz z kontekstem.

## Integracja z playbookiem

Jeśli organizacja ma skonfigurowany playbook negocjacyjny (w `iura.local.md` lub analogicznym):
- Wyprowadź domyślne zestawy kolumn z pozycji playbooka
- Używaj progów playbooka do klasyfikacji ZIELONY/ŻÓŁTY/CZERWONY
- Dołącz kolumnę „Odstępstwo od playbooka" flagującą postanowienia poza zakresem
- Odwołuj się do kryteriów eskalacji przy flagowaniu CZERWONY

Jeśli playbook negocjacyjny nie jest skonfigurowany:
- Zaznacz, że oceny opierają się na ogólnych standardach rynkowych i polskim ius cogens
- Zaproponuj pomoc w stworzeniu playbooka na podstawie wzorców z dokumentów (np. „Zauważam,
  że Państwa umowy stosują 12-miesięczny limit odpowiedzialności — skodyfikować jako standard?")
