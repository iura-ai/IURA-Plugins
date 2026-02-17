---
description: Masowy przegląd wielu dokumentów prawnych — ekstrakcja ustrukturyzowanych danych do arkusza Excel, każdy dokument to wiersz, każde pytanie to kolumna (prawo polskie)
argument-hint: "<pliki dokumentów lub ścieżka folderu>"
---

# /tabular-review -- Przegląd tabelaryczny dokumentów

Masowy przegląd wielu dokumentów prawnych (umowy, NDA, umowy najmu, umowy kredytowe, SPA, MSA itp.) przez ekstrakcję ustrukturyzowanych danych do arkusza Excel. Każdy dokument to wiersz, każde pytanie przeglądowe to kolumna, a każda komórka zawiera wyekstrahowaną odpowiedź z odniesieniem do źródła.

**Ważne**: To polecenie wspiera procesy prawne, ale nie udziela porad prawnych. Wszelkie wyekstrahowane dane i analizy powinny zostać zweryfikowane przez wykwalifikowanych prawników przed podjęciem jakichkolwiek decyzji.

## Wywołanie

```
/tabular-review
```

## Przebieg pracy

### Krok 1: Przyjęcie dokumentów

Przyjmij dokumenty w dowolnym formacie:
- **Pliki**: PDF, DOCX lub inne formaty dokumentów (wiele plików jednocześnie)
- **Ścieżka folderu**: Katalog zawierający dokumenty do przeglądu
- **URL**: Link do folderu w chmurze, DMS lub wirtualnym data roomie (VDR)

Jeśli dokumenty nie zostały dostarczone, poproś użytkownika o ich przekazanie.

Jeśli dostarczono mniej niż 2 dokumenty, zaproponuj skorzystanie z `/review-contract` do przeglądu pojedynczego dokumentu.

### Krok 2: Inwentaryzacja

Przeczytaj każdy dokument i utwórz inwentarz:
- Nazwa pliku
- Typ dokumentu (umowa, aneks, NDA, pełnomocnictwo, itp.)
- Zidentyfikowane strony
- Data zawarcia lub wejścia w życie

Przedstaw inwentarz użytkownikowi do potwierdzenia przed kontynuacją.

### Krok 3: Zdefiniowanie kolumn ekstrakcji

Ustal kolumny przeglądowe we współpracy z użytkownikiem:

**Jeśli użytkownik podaje konkretne pytania**: Użyj ich bezpośrednio jako kolumny.

**Jeśli użytkownik opisuje ogólny cel** (np. „due diligence tych umów najmu"): Zaproponuj zestaw kolumn na podstawie typu dokumentów i przedstaw do potwierdzenia.

**Jeśli użytkownik ma playbook**: Wyprowadź kolumny ze standardowych pozycji playbooka.

Dostępne typy kolumn:

| Typ | Opis | Przykład |
|-----|------|---------|
| **Tekst** | Ekstrakcja tekstowa | „Prawo właściwe" → „Prawo polskie" |
| **Data** | Data znormalizowana | „Data wejścia w życie" → „2024-01-15" |
| **Strona/Podmiot** | Nazwa podmiotu | „Kontrahent" → „ABC sp. z o.o." |
| **Waluta** | Wartość pieniężna | „Limit odpowiedzialności" → „500 000 PLN" |
| **Okres** | Okres czasu | „Okres obowiązywania" → „36 miesięcy" |
| **Tak/Nie** | Ustalenie binarne | „Zawiera zakaz konkurencji?" → „Tak" |
| **Lista** | Wiele elementów | „Wyłączenia spod limitu" → „Naruszenie IP; Wina umyślna" |
| **Ryzyko** | Flaga GREEN/YELLOW/RED | „Kary umowne" → „YELLOW — brak limitu łącznego" |

### Krok 4: Weryfikacja przepisów (jeśli IURA MCP dostępne)

Jeśli masz dostęp do IURA MCP (narzędzie `Search_DU` itp.), **przeczytaj SKILL.md skilla `iura`** i zweryfikuj aktualne brzmienie przepisów KC/KSH powoływanych w kolumnach ekstrakcji. Cytowanie przepisów z pamięci niesie ryzyko halucynacji. Jeśli IURA MCP nie jest dostępne, pomiń ten krok, ale zaznacz w arkuszu, że oceny oparte o przepisy wymagają weryfikacji.

### Krok 5: Ekstrakcja danych

Dla każdego dokumentu systematycznie wyodrębnij odpowiedź na każde pytanie kolumnowe.

**Zasady ekstrakcji:**
- **Bądź zwięzły**: Wartość powinna być kompaktowa i porównywalna między wierszami
- **Bądź precyzyjny**: Wyodrębniaj faktyczne warunki, nie interpretację
- **Odnotuj brak**: Wpisz „Brak regulacji" lub „Umowa milczy" zamiast pustej komórki
- **Sygnalizuj niejednoznaczność**: Np. „Niejasne — § 8.2 odwołuje się do ‚rozsądnych starań' bez definiowania standardu"
- **Dołącz źródła**: Zanotuj sekcję/klauzulę/stronę dla każdej wartości
- **Powołuj się na przepisy**: Wskaż przepis KC/KSH przy instytucjach prawnych

**Dla kolumn typu Ryzyko:**
- **GREEN**: Zgodne ze standardami rynkowymi i przepisami bezwzględnie obowiązującymi
- **YELLOW**: Poza preferowaną pozycją, ale negocjowalne; spotykane na rynku
- **RED**: Poza akceptowalnym zakresem; wymaga eskalacji

### Krok 6: Budowa arkusza Excel

Wygeneruj plik Excel z następującymi arkuszami:

**Arkusz 1: „Podsumowanie"**
- Wiersz tytułowy z nazwą przeglądu, datą i liczbą dokumentów
- Statystyki: rozkład ryzyka (GREEN/YELLOW/RED)
- Legenda kolorowania

**Arkusz 2: „Przegląd tabelaryczny" (główny)**
- Nagłówki: pogrubione, autofiltr, ciemnoniebieskie tło (1F4E79), biały tekst
- Zamrożony panel, naprzemienne cieniowanie wierszy, auto-szerokość, zawijanie tekstu
- Kolumny Ryzyko: GREEN → jasnozielone (C6EFCE), YELLOW → jasnożółte (FFEB9C), RED → jasnoczerwone (FFC7CE)

**Arkusz 3: „Źródła"** (rekomendowany)
- Odniesienia do źródeł dla każdej komórki z arkusza głównego

**Arkusz 4: „Parametry ekstrakcji"** (metadane)
- Lista kolumn z pytaniami ekstrakcji

### Krok 7: Weryfikacja i dostarczenie

1. **Kompletność**: Każdy dokument przetworzony, każda kolumna wypełniona
2. **Spójność**: Normalizuj analogiczne postanowienia w całym zbiorze

Zapisz plik Excel i przedstaw użytkownikowi wraz ze zwięzłym podsumowaniem:

```
## Przegląd tabelaryczny — Podsumowanie

**Przejrzano dokumentów**: [liczba]
**Data przeglądu**: [data]
**Podstawa przeglądu**: [Playbook / Ogólne standardy + prawo polskie]

### Kluczowe ustalenia

- **RED**: [liczba] — [krótki opis najpoważniejszych problemów]
- **YELLOW**: [liczba] — [krótki opis głównych obszarów do negocjacji]
- **GREEN**: [liczba] — [potwierdzenie zgodności]

### Kolejne kroki

[Rekomendacje: pogłębienie analizy wybranych dokumentów, korekta progów ryzyka, dodanie kolumn]
```

## Obsługa dużych zbiorów

- **10+ dokumentów**: Przetwarzaj partiami, informuj o postępach
- **50+ dokumentów**: Rekomenduj priorytetyzację podzbioru, iteracyjne przetworzenie reszty
- **Mieszane typy**: Pogrupuj według typu dokumentu, zastosuj właściwe zestawy kolumn

## Integracja z innymi poleceniami

- Dokumenty oflagowane jako RED mogą być pogłębione przez `/review-contract`
- NDA w zbiorze można wstępnie przetriażować przez `/triage-nda`

## Uwagi

- Dla zbiorów zawierających różne typy dokumentów, zaproponuj osobne arkusze per typ lub nadrzędny zestaw kolumn z „N/D"
- Jeśli playbook jest skonfigurowany w `iura.local.md`, użyj jego progów ryzyka; w przeciwnym razie stosuj ogólne standardy rynkowe
- Zawsze przypominaj, że wyekstrahowane dane powinny być zweryfikowane przez wykwalifikowanego prawnika
