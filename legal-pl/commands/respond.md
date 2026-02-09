---
description: Generate a response to a common legal inquiry using configured templates (Polish law context with IURA MCP)
argument-hint: "[typ-zapytania]"
---

# /respond -- Generowanie odpowiedzi z szablonów

> Jeśli widzisz nieznane symbole zastępcze lub chcesz sprawdzić podłączone narzędzia, zobacz [CONNECTORS.md](../CONNECTORS.md).

Generowanie odpowiedzi na typowe zapytania prawne z wykorzystaniem skonfigurowanych szablonów. Personalizacja odpowiedzi konkretnymi danymi oraz weryfikacja kryteriów eskalacji dla sytuacji, które nie powinny korzystać z szablonu — z weryfikacją aktualnych przepisów polskiego prawa dzięki IURA MCP.

**Ważne**: To polecenie wspiera pracę prawnika, ale nie stanowi porady prawnej. Wygenerowane odpowiedzi powinny być zweryfikowane przez wykwalifikowanego prawnika przed wysłaniem.

## Wywołanie

```
/respond [typ-zapytania]
```

Dostępne typy zapytań:
- `wniosek-rodo` lub `dsr` -- Wnioski osób, których dane dotyczą (dostęp, usunięcie, sprostowanie, przenoszenie)
- `zabezpieczenie-dowodow` lub `hold` -- Zarządzenia dotyczące zabezpieczenia dowodów (litigation hold)
- `zapytanie-kontrahenta` lub `vendor` -- Pytania prawne od/do kontrahentów
- `wniosek-nda` lub `nda` -- Prośby o NDA od zespołów biznesowych
- `prywatnosc` lub `privacy` -- Pytania dotyczące prywatności i ochrony danych
- `wezwanie-sadowe` lub `subpoena` -- Odpowiedzi na wezwania sądowe i pisma procesowe
- `ubezpieczenie` lub `insurance` -- Zgłoszenia szkód ubezpieczeniowych
- `zapytanie-regulacyjne` lub `regulatory` -- Odpowiedzi na zapytania organów regulacyjnych (UODO, UOKiK, KNF)
- `wlasny` lub `custom` -- Użycie własnego szablonu

Jeśli typ zapytania nie jest podany, zapytaj użytkownika o rodzaj odpowiedzi i pokaż dostępne kategorie.

## Przebieg pracy

### Krok 1: Identyfikacja typu zapytania

Przyjmij typ zapytania od użytkownika. Jeśli typ jest niejednoznaczny, pokaż dostępne kategorie i poproś o doprecyzowanie.

### Krok 2: Załadowanie szablonu

Poszukaj szablonów w ustawieniach lokalnych (np. `legal.local.md` lub katalog szablonów).

**Jeśli szablony są skonfigurowane:**
- Załaduj odpowiedni szablon dla typu zapytania
- Zidentyfikuj wymagane zmienne (nazwa adresata, daty, szczegóły)

**Jeśli szablony nie są skonfigurowane:**
- Poinformuj użytkownika, że nie znaleziono szablonów dla tego typu zapytania
- Zaproponuj pomoc w stworzeniu szablonu (patrz Krok 7)
- Przygotuj rozsądną domyślną strukturę odpowiedzi na podstawie typu zapytania

### Krok 3: Weryfikacja przepisów z IURA MCP

Przed wygenerowaniem odpowiedzi, zweryfikuj aktualne przepisy prawa polskiego za pomocą IURA MCP:

1. **Aktualne przepisy** (Search_DU): Wyszukaj obowiązujące przepisy istotne dla typu zapytania z parametrem `in_force_as_of` ustawionym na dzisiejszą datę:
   - Wniosek RODO: art. 15–22 RODO, ustawa o ochronie danych osobowych
   - Zabezpieczenie dowodów: przepisy KPC o zabezpieczeniu dowodów
   - Wezwanie sądowe: stosowne przepisy KPC/KPK
   - Zapytanie regulacyjne: przepisy ustawy właściwej dla danego organu

2. **Orzecznictwo** (Search_SN, Search_SP, Search_CBOSA): Wyszukaj istotne orzeczenia dotyczące:
   - Terminów i procedur odpowiedzi
   - Zakresu obowiązków
   - Konsekwencji braku odpowiedzi lub niewłaściwej odpowiedzi

3. **Decyzje organów** (Search_News): Dla zapytań regulacyjnych, wyszukaj najnowsze decyzje odpowiedniego organu (UODO, UOKiK, KNF).

Uwzględnij znalezione przepisy i orzeczenia w treści odpowiedzi — powołuj się na konkretne artykuły i sygnatury.

### Krok 4: Sprawdzenie kryteriów eskalacji

Przed wygenerowaniem odpowiedzi, oceń czy sytuacja ma cechy, które NIE powinny korzystać z szablonowej odpowiedzi:

#### Kryteria eskalacji — Wniosek RODO (DSR)
- Wniosek dotyczy danych osoby małoletniej
- Wniosek pochodzi od organu nadzorczego (UODO), nie od osoby fizycznej
- Wniosek dotyczy danych objętych zabezpieczeniem dowodów
- Wnioskodawca jest obecnym lub byłym pracownikiem w aktywnym sporze
- Zakres wniosku jest nadzwyczaj szeroki lub sprawia wrażenie zbierania informacji
- Wniosek dotyczy danych przetwarzanych w jurysdykcji o szczególnych wymaganiach
- Wniosek dotyczy danych wrażliwych (art. 9 RODO)

#### Kryteria eskalacji — Zabezpieczenie dowodów
- Sprawa obejmuje potencjalną odpowiedzialność karną
- Zakres zabezpieczenia jest niejasny lub potencjalnie zbyt szeroki
- Istnieją wątpliwości, czy określone dane są w zakresie
- Istnieją wcześniejsze zarządzenia o zabezpieczeniu w tej samej lub powiązanej sprawie
- Zabezpieczenie może istotnie wpłynąć na bieżącą działalność

#### Kryteria eskalacji — Zapytanie kontrahenta
- Pytanie dotyczy sporu lub potencjalnego naruszenia umowy
- Kontrahent grozi procesem lub rozwiązaniem umowy
- Pytanie dotyczy zgodności regulacyjnej (nie tylko warunków umownych)
- Odpowiedź mogłaby stworzyć wiążące zobowiązanie lub zrzeczenie się praw

#### Kryteria eskalacji — Wniosek NDA
- Kontrahent jest konkurentem
- NDA dotyczy informacji niejawnych lub zastrzeżonych
- Kontekst biznesowy sugeruje transakcję M&A
- Wniosek obejmuje nietypową materię (dane treningowe AI, dane biometryczne, itp.)

#### Kryteria eskalacji — Zapytanie regulacyjne
- Zapytanie pochodzi z postępowania kontrolnego lub wyjaśniającego
- Zapytanie sugeruje nałożenie kary administracyjnej
- Dotyczy więcej niż jednego organu regulacyjnego
- Wymaga ujawnienia informacji objętych tajemnicą przedsiębiorstwa

**Jeśli wykryto kryterium eskalacji:**
- Ostrzeż użytkownika, że ta sytuacja może nie nadawać się do szablonowej odpowiedzi
- Wyjaśnij, które kryterium zostało wykryte i dlaczego ma znaczenie
- Rekomenduj konsultację ze starszym prawnikiem lub kancelarią zewnętrzną
- Zaproponuj przygotowanie wstępnej odpowiedzi do przeglądu prawnika, a nie odpowiedzi finalnej

### Krok 5: Zebranie szczegółów

Poproś użytkownika o dane potrzebne do personalizacji odpowiedzi:

**Wniosek RODO (DSR):**
- Imię i nazwisko wnioskodawcy oraz dane kontaktowe
- Typ wniosku (dostęp, usunięcie, sprostowanie, przenoszenie, sprzeciw, ograniczenie przetwarzania)
- Jakie dane są objęte wnioskiem
- Podstawa prawna (RODO art. 15–22, ustawa o ochronie danych osobowych)
- Termin odpowiedzi (co do zasady 1 miesiąc od otrzymania wniosku — art. 12 ust. 3 RODO)

**Zabezpieczenie dowodów:**
- Nazwa sprawy i sygnatura
- Depozytariusze (kto musi zabezpieczyć materiały)
- Zakres zabezpieczenia (zakres dat, typy danych, systemy)
- Kontakt do kancelarii zewnętrznej
- Data wejścia w życie

**Zapytanie kontrahenta:**
- Nazwa kontrahenta
- Umowa referencyjna (jeśli dotyczy)
- Konkretne pytanie
- Istotne postanowienia umowne

**Wniosek NDA:**
- Zespół biznesowy wnioskujący i osoba kontaktowa
- Nazwa kontrahenta
- Cel NDA
- Wzajemna czy jednostronna
- Szczególne wymagania

**Zapytanie regulacyjne:**
- Organ regulacyjny (UODO, UOKiK, KNF, URE, UKE, itp.)
- Sygnatura sprawy / numer postępowania
- Termin odpowiedzi
- Zakres zapytania
- Wcześniejsza korespondencja z organem

### Krok 6: Wygenerowanie odpowiedzi

Uzupełnij szablon zebranymi danymi. Upewnij się, że odpowiedź:
- Używa odpowiedniego tonu (profesjonalny, jasny, nie nadmiernie formalistyczny dla odbiorców biznesowych)
- Zawiera wszystkie wymagane elementy prawne dla danego typu odpowiedzi
- Powołuje się na konkretne przepisy prawa polskiego (zweryfikowane przez IURA MCP)
- Wskazuje konkretne daty, terminy i obowiązki
- Zawiera jasne następne kroki dla adresata
- Zawiera odpowiednie zastrzeżenia i klauzule
- Jest zgodna z wymogami formalnymi (jeśli odpowiedź jest pismem procesowym lub urzędowym)

Przedstaw projekt odpowiedzi użytkownikowi do przeglądu przed wysłaniem.

### Krok 7: Tworzenie szablonu (jeśli brak szablonu)

Jeśli użytkownik chce utworzyć nowy szablon:

1. Zapytaj, dla jakiego typu zapytania jest szablon
2. Zapytaj o kluczowe elementy do uwzględnienia
3. Zapytaj o ton i odbiorcę (wewnętrzny vs. zewnętrzny, biznesowy vs. prawny)
4. Przygotuj projekt szablonu ze zmiennymi (np. `{{imie_nazwisko}}`, `{{termin}}`, `{{sygnatura_sprawy}}`)
5. Dodaj kryteria eskalacji odpowiednie dla kategorii
6. Uwzględnij standardowe powołania na przepisy prawa polskiego (zweryfikowane przez IURA MCP)
7. Przedstaw szablon do przeglądu
8. Zasugeruj zapisanie zatwierdzonego szablonu w ustawieniach lokalnych

#### Format szablonu

```markdown
## Szablon: [Nazwa kategorii]

### Kryteria eskalacji
- [Kryterium 1]
- [Kryterium 2]

### Zmienne
- {{zmienna_1}}: [opis]
- {{zmienna_2}}: [opis]

### Podstawy prawne
- [Artykuł 1 — krótki opis]
- [Artykuł 2 — krótki opis]

### Temat
[Szablon tematu]

### Treść
[Treść odpowiedzi z {{zmiennymi}}]

### Załączniki
[Standardowe załączniki do dołączenia]

### Dalsze działania
[Standardowe czynności po wysłaniu]
```

## Format wyjściowy

```
## Wygenerowana odpowiedź: [Typ zapytania]

**Do**: [adresat]
**Temat**: [temat]

---

[Treść odpowiedzi]

---

### Podstawy prawne (IURA MCP)
[Lista przepisów i orzeczeń, na których oparta jest odpowiedź, z sygnaturami]

### Weryfikacja eskalacji
[Potwierdzenie braku kryteriów eskalacji, LUB oznaczone kryteria z rekomendacjami]

### Dalsze działania
1. [Czynności po wysłaniu]
2. [Przypomnienia kalendarzowe do ustawienia]
3. [Wymagania dotyczące śledzenia lub rejestracji]
```

## Uwagi

- Zawsze przedstawiaj projekt odpowiedzi użytkownikowi do przeglądu przed zasugerowaniem wysyłki
- Jeśli e-mail jest podłączony przez MCP, zaproponuj utworzenie wersji roboczej e-maila z odpowiedzią
- Śledź terminy odpowiedzi i proponuj ustawienie przypomnień kalendarzowych
- Dla odpowiedzi regulowanych (wnioski RODO, wezwania sądowe, zapytania organów), zawsze podawaj obowiązujący termin i wymogi regulacyjne — zweryfikowane przez IURA MCP
- Szablony powinny być dokumentami żywymi; sugeruj aktualizacje, gdy użytkownik modyfikuje odpowiedź szablonową
- Powołania na przepisy prawa podawaj z pełnymi sygnaturami aktów prawnych (np. „art. 15 ust. 1 Rozporządzenia PE i Rady (UE) 2016/679 z dnia 27 kwietnia 2016 r.")
