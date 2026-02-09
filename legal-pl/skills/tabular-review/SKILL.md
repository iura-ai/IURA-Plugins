---
name: tabular-review
description: >
  Bulk-review multiple legal documents (contracts, leases, NDAs, loan agreements, SPAs, MSAs, etc.)
  by extracting structured data into an Excel spreadsheet under Polish law. Each document becomes a
  row; each review question becomes a column. Enhanced with IURA MCP for real-time Polish case law
  lookup, statutory verification, and precedent-backed risk classification. Use when the user wants
  to review, compare, or analyze a set of legal documents side by side, extract key terms from a
  document portfolio, perform due diligence across a data room, audit a contract portfolio, or
  produce a spreadsheet summarizing clauses, risks, dates, obligations, or deviations across
  multiple agreements. Also trigger when the user mentions "przegląd tabelaryczny", "matryca
  dokumentów", "porównanie umów", "ekstrakcja klauzul", "due diligence", "audyt portfela umów",
  or wants any kind of structured, multi-document legal analysis delivered as a spreadsheet.
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

## Dlaczego to ma znaczenie

Zespoły prawne regularnie muszą przeglądać dziesiątki lub setki dokumentów podczas due diligence,
audytów portfeli umów czy przeglądów compliance. Ręczne czytanie każdego dokumentu i śledzenie
ustaleń w arkuszach zajmuje dni lub tygodnie. Ten skill kompresuje tę pracę do ustrukturyzowanego
procesu ekstrakcji generującego profesjonalny, opatrzony źródłami arkusz Excel — wzbogacony
o aktualne orzecznictwo i przepisy prawa polskiego dzięki IURA MCP.

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

## Integracja z IURA MCP

Przed rozpoczęciem i w trakcie każdego przeglądu tabelarycznego **obowiązkowo** korzystaj
z narzędzi IURA MCP w celu zapewnienia aktualności i trafności analizy prawnej.

### Na starcie przeglądu: weryfikacja stanu prawnego

1. **Search_DU** — sprawdź aktualne brzmienie przepisów właściwych dla typu przeglądanych
   dokumentów (parametr `in_force_as_of` = dzisiejsza data):
   - Umowy handlowe → art. 353¹, 471-497, 483-485 KC
   - Umowy najmu → art. 659-692 KC
   - Umowy kredytowe → Prawo bankowe (art. 69 i nast.)
   - NDA → Ustawa o zwalczaniu nieuczciwej konkurencji (art. 11 — tajemnica przedsiębiorstwa)
   - SPA → KSH, w szczególności art. 180-188 (sp. z o.o.) i art. 337-341 (S.A.)
   - Umowy IT → Ustawa o prawie autorskim (art. 41, 74)
2. **Search_DU** — zweryfikuj przepisy bezwzględnie obowiązujące (ius cogens): art. 58 KC,
   art. 473 § 2 KC, art. 483 § 1 KC.
3. **Search_News** — sprawdź najnowsze zmiany prawne mogące wpływać na przeglądane dokumenty.

### Dla kolumn typu Ryzyko: analiza orzecznictwa

1. **Search_SN** — wyszukaj orzeczenia SN interpretujące klauzule analogiczne do przeglądanych
   (np. „miarkowanie kary umownej", „ograniczenie odpowiedzialności kontraktowej").
2. **Search_SP** — wyszukaj najnowsze orzeczenia sądów powszechnych ukazujące aktualne trendy
   (np. „rażąco wygórowana kara umowna", „niedozwolone postanowienia umowne B2B").
3. Cytuj znalezione orzeczenia w komórkach ryzyka, podając **sygnaturę** i datę wydania.

### Opcjonalna kolumna „Analiza orzecznictwa"

Dla każdego dokumentu możesz dodać kolumnę **„Analiza orzecznictwa"**:
- Użyj **Search_SN** i **Search_SP** aby wyszukać precedensy dot. kluczowych klauzul dokumentu
- Podsumuj 2-3 najistotniejsze orzeczenia z sygnaturami
- Wskaż, czy linia orzecznicza jest stabilna czy ewoluuje
- Dla kwestii administracyjnych/podatkowych użyj **Search_CBOSA** lub **Search_IP**

### Weryfikacja klauzul wobec prawa polskiego

Gdy umowy podlegają prawu polskiemu, dla każdego dokumentu:
- Zweryfikuj kluczowe klauzule pod kątem zgodności z przepisami bezwzględnie obowiązującymi
- Oznacz postanowienia potencjalnie nieważne (art. 58 KC) lub sprzeczne z naturą stosunku
  zobowiązaniowego (art. 353¹ KC)
- Sprawdź zachowanie wymaganych elementów formalnych (np. forma pisemna pod rygorem
  nieważności, wskazanie pól eksploatacji przy przeniesieniu praw autorskich)

**Zasada ogólna**: Żadna klasyfikacja RED nie powinna być przedstawiana bez uprzedniego
przeszukania baz IURA pod kątem aktualnego orzecznictwa i stanu prawnego.

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

**Jeśli użytkownik ma playbook**: Wyprowadź kolumny ze standardowych pozycji playbooka.

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
| **Ryzyko** | Flaga GREEN/YELLOW/RED | „Kary umowne" | „YELLOW — brak limitu łącznego" |

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
14. Ogólna klasyfikacja ryzyka (GREEN/YELLOW/RED)

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
  (np. „Kara umowna — art. 483 KC"). Użyj **Search_DU** do weryfikacji aktualnego brzmienia.

**Dla kolumn typu Ryzyko:**
- **GREEN**: Zgodne ze standardami rynkowymi i przepisami bezwzględnie obowiązującymi.
- **YELLOW**: Poza preferowaną pozycją, ale negocjowalne; spotykane na rynku.
- **RED**: Poza akceptowalnym zakresem; wymaga eskalacji. Obejmuje klauzule potencjalnie
  nieważne na gruncie prawa polskiego.

Jeśli playbook jest dostępny, oceniaj względem jego pozycji. W przeciwnym razie stosuj ogólne
standardy rynkowe. **Obowiązkowo** przeszukaj IURA (Search_SN, Search_SP) dla wsparcia
klasyfikacji orzecznictwem.

### Krok 4: Budowa arkusza Excel

Użyj wzorców ze skilla `xlsx` i biblioteki openpyxl. **Przeczytaj SKILL.md skilla xlsx** przed
napisaniem kodu Excel.

#### Struktura arkuszy

**Arkusz 1: „Podsumowanie"**
- Wiersz tytułowy z nazwą przeglądu, datą i liczbą dokumentów
- Statystyki: łączna liczba dokumentów, rozkład ryzyka (GREEN/YELLOW/RED)
- Legenda kolorowania
- Kluczowe ustalenia IURA (najistotniejsze przepisy i orzeczenia przywołane w przeglądzie)

**Arkusz 2: „Przegląd tabelaryczny" (główny)**
- Wiersz 1: Nagłówki, pogrubione, autofiltr · Kolumna A: Nr · Kolumna B: Nazwa dokumentu
- Formatowanie: biały tekst na ciemnoniebieskim tle nagłówka (RGB: 1F4E79), zamrożony panel,
  naprzemienne cieniowanie wierszy, auto-szerokość (min 15, max 50), zawijanie tekstu
- Kolumny Ryzyko: GREEN → jasnozielone tło (C6EFCE), YELLOW → jasnożółte (FFEB9C),
  RED → jasnoczerwone (FFC7CE)

**Arkusz 3: „Źródła"** (rekomendowany)
- Jeden wiersz na dokument, każda komórka zawiera odniesienie do źródła odpowiadające komórce
  w arkuszu głównym. Dla kolumn wspieranych przez IURA: sygnatury orzeczeń i przepisy
  (np. „art. 483 § 1 KC; wyrok SN z 15.09.2022, II CSKP 411/22").

**Arkusz 4: „Parametry ekstrakcji"** (metadane)
- Lista kolumn z pytaniami ekstrakcji oraz narzędzi IURA MCP użytych w analizie

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
5. **Weryfikacja IURA**: Sprawdź aktualność i poprawność powołanych przepisów i sygnatur.

### Krok 6: Dostarczenie

Zapisz plik Excel i przedstaw użytkownikowi:
- Zwięzłe podsumowanie (np. „Przejrzano 15 umów. 3 z RED dot. odpowiedzialności, 7 z YELLOW
  dot. kar umownych. 2 klauzule potencjalnie nieważne na gruncie art. 483 § 1 KC.")
- Link do pliku
- Kluczowe orzeczenia i przepisy przywołane w analizie
- Zaproszenie: „Czy chcesz dodać kolumny, skorygować progi ryzyka lub pogłębić analizę?"

## Obsługa dużych zbiorów dokumentów

Dla zbiorów 10+ dokumentów:
- Przetwarzaj dokumenty partiami, aby utrzymać jakość ekstrakcji
- Po każdej partii weryfikuj spójność przed kontynuacją
- Informuj użytkownika o postępach
- Dla każdej partii wykonuj osobne zapytania IURA MCP

Dla zbiorów 50+ dokumentów:
- Rekomenduj priorytetyzację podzbioru (np. „Zacznijmy od 10 umów o najwyższej wartości")
- Zaproponuj iteracyjne przetworzenie reszty
- Rozważ, czy wszystkie kolumny są potrzebne dla wszystkich dokumentów

## Obsługa mieszanych typów dokumentów

Jeśli zbiór zawiera różne typy (NDA, MSA, aneksy, pełnomocnictwa):
- Pogrupuj według typu (kolumna „Typ dokumentu")
- Zastosuj zestawy kolumn właściwe dla typu lub nadrzędny zestaw z „N/D"
- Rozważ osobne arkusze per typ, jeśli pokrywanie kolumn jest niskie
- Dostosuj zapytania IURA MCP do każdego typu (inne przepisy KC dla różnych umów nazwanych)

## Integracja z innymi skillami

Ten skill współpracuje z:
- **contract-review**: Pogłębiona analiza dokumentów oflagowanych w przeglądzie tabelarycznym
- **legal-risk-assessment**: Formalna ocena ryzyk zidentyfikowanych podczas ekstrakcji
- **nda-triage**: Zestawy kolumn NDA mogą odzwierciedlać listę kontrolną triażowania
- **compliance**: Kolumny dot. ochrony danych zasilone kryteriami DPA ze skilla compliance

Gdy użytkownik prosi o „pogłębienie" konkretnego dokumentu, przekaż sterowanie do
odpowiedniego skilla wraz z kontekstem i wynikami wyszukiwań IURA MCP.

## Integracja z playbookiem

Jeśli organizacja ma skonfigurowany playbook (w `legal.local.md` lub analogicznym):
- Wyprowadź domyślne zestawy kolumn z pozycji playbooka
- Używaj progów playbooka do klasyfikacji GREEN/YELLOW/RED
- Dołącz kolumnę „Odstępstwo od playbooka" flagującą postanowienia poza zakresem
- Odwołuj się do kryteriów eskalacji przy flagowaniu RED
- Uzupełnij pozycje playbooka o aktualne orzecznictwo z IURA MCP — pozycja playbooka
  może się zdezaktualizować, jeśli linia orzecznicza uległa zmianie

Jeśli playbook nie jest skonfigurowany:
- Zaznacz, że oceny opierają się na ogólnych standardach rynkowych i polskim ius cogens
- Zaproponuj pomoc w stworzeniu playbooka na podstawie wzorców z dokumentów (np. „Zauważam,
  że Państwa umowy stosują 12-miesięczny limit odpowiedzialności — skodyfikować jako standard?")
- Użyj **Search_SN** aby zaproponować pozycje oparte na dominującej linii orzeczniczej SN
