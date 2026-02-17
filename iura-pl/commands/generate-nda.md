---
description: Generowanie draftu umowy NDA (umowy o zachowaniu poufności) w formacie Word na podstawie danych stron i parametrów — prawo polskie
argument-hint: "<strony umowy, np. 'między Firma X a Firma Y'>"
---

# /generate-nda -- Generowanie umowy NDA

Generowanie kompletnego draftu umowy o zachowaniu poufności (NDA) w formacie Word (.docx) na podstawie danych stron i wybranych parametrów. Umowa generowana jest zgodnie z polskim prawem cywilnym (art. 353¹ KC) i standardami rynkowymi.

**Ważne**: To polecenie wspiera pracę prawnika, ale nie stanowi porady prawnej. Wygenerowany draft powinien zostać zweryfikowany przez wykwalifikowanego prawnika przed podpisaniem.

## Wywołanie

```
/generate-nda
```

## Przebieg pracy

### Krok 1: Przyjęcie stron

Przyjmij dane stron umowy NDA. Użytkownik może podać:
- **Nazwy firm**: np. „między ABC sp. z o.o. a XYZ S.A."
- **Częściowe dane**: np. „NDA z firmą ABC" (druga strona = organizacja użytkownika)
- **Pełne dane**: nazwy, KRS, NIP, adresy, osoby reprezentujące

Jeśli strony nie zostały podane, poproś użytkownika o ich wskazanie.

### Krok 2: Wyszukanie danych podmiotów

Wyszukaj w internecie dane rejestrowe każdej strony:
- **Nazwa pełna** (firma) z KRS
- **Numer KRS** (jeśli spółka zarejestrowana w KRS)
- **NIP** i **REGON**
- **Adres siedziby**
- **Forma prawna** (sp. z o.o., S.A., sp.k., jednoosobowa działalność gospodarcza, itp.)
- **Osoby uprawnione do reprezentacji** (zarząd, prokurenci, wspólnicy) i sposób reprezentacji

Przedstaw znalezione dane użytkownikowi w formie tabeli do potwierdzenia:

```
## Dane stron

### Strona 1: Ujawniająca / Otrzymująca / Obie
| Pole | Wartość |
|------|---------|
| Firma | [pełna nazwa] |
| Forma prawna | [sp. z o.o. / S.A. / ...] |
| KRS | [numer] |
| NIP | [numer] |
| REGON | [numer] |
| Adres siedziby | [adres] |
| Reprezentacja | [imię i nazwisko, funkcja] |
| Sposób reprezentacji | [samodzielna / łączna / ...] |

### Strona 2: [analogicznie]
```

Poproś o potwierdzenie lub korektę danych.

### Krok 3: Parametry NDA

Zapytaj użytkownika o kluczowe parametry umowy:

1. **Typ NDA**: Wzajemna (obie strony ujawniają i otrzymują) czy jednostronna (jedna strona ujawnia, druga otrzymuje)?
2. **Cel ujawnienia**: W jakim celu informacje będą ujawniane? (np. „ocena możliwości współpracy handlowej", „due diligence przed transakcją M&A", „realizacja projektu IT")
3. **Okres obowiązywania umowy**: Jak długo umowa ma obowiązywać? (domyślnie: 2 lata)
4. **Okres przeżywalności obowiązku poufności**: Jak długo obowiązek poufności trwa po rozwiązaniu umowy? (domyślnie: 3 lata; tajemnice przedsiębiorstwa — czas nieokreślony w granicach art. 11 UZNK)
5. **Kary umowne**: Czy uwzględnić kary umowne za naruszenie? Jeśli tak, w jakiej wysokości? (domyślnie: brak; jeśli obecne — wzajemne)
6. **Prawo właściwe**: Prawo polskie (domyślnie) czy inne?
7. **Rozstrzyganie sporów**: Sąd powszechny (domyślnie) czy arbitraż?
8. **Szczególne wymagania**: Czy są dodatkowe postanowienia? (np. zakaz reverse engineering, szczególna definicja informacji poufnych, klauzula dotycząca danych osobowych)

Jeśli użytkownik podaje częściowe parametry, zastosuj wartości domyślne dla brakujących i wyraźnie je wskaż.

### Krok 4: Weryfikacja przepisów (jeśli IURA MCP dostępne)

Jeśli masz dostęp do IURA MCP (narzędzia `Search_DU`, `Search_SN` itp.), **przeczytaj SKILL.md skilla `iura`** i zweryfikuj aktualne brzmienie przepisów KC i UZNK powoływanych w umowie. Cytowanie przepisów z pamięci niesie ryzyko halucynacji. Jeśli IURA MCP nie jest dostępne, pomiń ten krok, ale zaznacz w drafcie, że przytoczone przepisy wymagają weryfikacji z aktualnym stanem prawnym.

### Krok 5: Generowanie draftu Word (.docx)

Wygeneruj kompletną umowę NDA w formacie Word (.docx) zawierającą:

**Struktura dokumentu:**

1. **Nagłówek**: „UMOWA O ZACHOWANIU POUFNOŚCI" (lub „UMOWA O WZAJEMNYM ZACHOWANIU POUFNOŚCI")
2. **Preambuła**: Data, miejsce zawarcia, dane stron z danymi rejestrowymi, osoby reprezentujące
3. **§ 1 Definicje**: Informacje Poufne, Strona Ujawniająca, Strona Otrzymująca, Cel, Przedstawiciele
4. **§ 2 Przedmiot umowy**: Zobowiązanie do zachowania poufności, określenie celu
5. **§ 3 Zakres informacji poufnych**: Definicja, wyłączenia (wiedza publiczna, wcześniejsze posiadanie, niezależne opracowanie, otrzymanie od osoby trzeciej, przymus prawny)
6. **§ 4 Obowiązki Strony Otrzymującej**: Standard staranności, ograniczenie celu, ograniczenie kręgu osób, obowiązek zabezpieczenia
7. **§ 5 Dozwolone ujawnienia**: Pracownicy, współpracownicy, doradcy (pod warunkiem objęcia obowiązkiem poufności), organy (na podstawie przepisów prawa)
8. **§ 6 Okres obowiązywania i rozwiązanie**: Czas trwania, wypowiedzenie, przeżywalność obowiązku poufności
9. **§ 7 Zwrot i zniszczenie**: Obowiązek zwrotu/zniszczenia po rozwiązaniu, wyjątek retencyjny (kopie wymagane przez prawo/compliance)
10. **§ 8 Odpowiedzialność i środki ochrony prawnej**: Odpowiedzialność za naruszenie (art. 471 KC), kary umowne (jeśli uzgodnione, art. 483 KC), zabezpieczenie roszczeń
11. **§ 9 Prawo właściwe i rozstrzyganie sporów**: Jurysdykcja, właściwość sądu
12. **§ 10 Postanowienia końcowe**: Forma pisemna zmian, cesja, klauzula salwatoryjna, liczba egzemplarzy
13. **Podpisy**: Miejsca na podpisy obu stron z oznaczeniem osób reprezentujących

**Formatowanie Word:**
- Czcionka: Times New Roman 11pt lub Arial 10pt
- Interlinea: 1.15
- Marginesy: 2.5 cm (standardowe)
- Nagłówki paragrafów: pogrubione
- Numeracja: § 1, § 2, ... z numeracją ustępów (1, 2, 3...)
- Stopka: „Strona X z Y"

### Krok 6: Prezentacja draftu

Przedstaw użytkownikowi wygenerowany draft wraz z podsumowaniem kluczowych decyzji:

```
## Draft NDA — Podsumowanie

**Strony**: [Strona 1] ↔ [Strona 2]
**Typ**: [Wzajemna / Jednostronna]
**Cel**: [cel ujawnienia]
**Okres obowiązywania**: [X lat]
**Przeżywalność poufności**: [Y lat]
**Kary umowne**: [Brak / Kwota]
**Prawo właściwe**: [prawo polskie]
**Rozstrzyganie sporów**: [sąd powszechny / arbitraż]

### Kluczowe postanowienia

1. **Definicja informacji poufnych**: [krótki opis zakresu]
2. **Standardowe wyłączenia**: [lista obecnych wyłączeń]
3. **Dozwolone ujawnienia**: [komu można ujawnić]
4. **Zwrot/zniszczenie**: [warunki]
5. **Odpowiedzialność**: [mechanizm]

### Uwagi do weryfikacji

- [Ewentualne punkty wymagające uwagi prawnika]
- [Postanowienia, które mogą wymagać dostosowania do specyfiki branży]

Plik: [nazwa_pliku.docx]
```

Zapytaj, czy użytkownik chce wprowadzić zmiany w drafcie.

## Playbook NDA

Jeśli w ustawieniach lokalnych (np. `iura.local.md`) skonfigurowany jest playbook NDA organizacji, użyj go jako podstawy do generowania — uwzględnij standardowe pozycje organizacji, preferowane brzmienia klauzul i wymagania specyficzne.

Jeśli playbook nie jest dostępny, generuj na podstawie ogólnych standardów rynkowych i polskich przepisów prawa cywilnego. Wyraźnie zaznacz, że draft bazuje na standardach ogólnych.

## Integracja z innymi poleceniami

- Wygenerowany draft można zweryfikować przez `/triage-nda` (ocena ryzyka)
- Dla NDA z niestandardowymi klauzulami, rekomenduj `/review-contract` do pogłębionej analizy

## Uwagi

- Draft jest punktem wyjścia do negocjacji — nie gotowym dokumentem do podpisu
- Zawsze przypominaj, że draft powinien być zweryfikowany przez wykwalifikowanego prawnika
- Dla umów międzynarodowych (strona zagraniczna), zaznacz potencjalne kwestie kolizyjnoprawne (Rozporządzenie Rzym I)
- Przy jednoosobowej działalności gospodarczej, weryfikuj czy nie zachodzą przesłanki do stosowania przepisów o ochronie konsumenta (art. 385⁵ KC)
