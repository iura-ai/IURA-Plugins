---
description: Sporządzenie notatki prawnej (legal memo) — obiektywna analiza zagadnienia prawnego z przepisami, orzecznictwem i rekomendacją
argument-hint: "<pytanie prawne lub opis zagadnienia>"
---

# /legal-memo -- Notatka prawna

Sporządzenie profesjonalnej notatki prawnej (legal memo / memorandum prawne) na podstawie pytania prawnego. Obiektywna analiza z przepisami, orzecznictwem, konkluzją i rekomendacją — gotowa do udostępnienia wewnętrznie.

**Ważne**: To polecenie wspiera pracę prawnika, ale nie stanowi porady prawnej. Notatka powinna być zweryfikowana przez wykwalifikowanego prawnika przed podjęciem decyzji.

## Wywołanie

```
/legal-memo
```

## Przebieg pracy

### Krok 1: Przyjęcie zagadnienia

Przyjmij pytanie prawne od użytkownika. Może to być:
- **Pytanie od biznesu**: np. "Czy możemy rozwiązać umowę z dostawcą X przed terminem?"
- **Zagadnienie prawne**: np. "Skuteczność klauzuli non-compete w umowie B2B"
- **Sytuacja do analizy**: np. "Kontrahent naruszył NDA — jakie mamy opcje?"
- **Dokument + pytanie**: np. plik umowy + "Czy klauzula 7.3 jest wykonalna?"

Jeśli pytanie nie zostało podane, poproś użytkownika o sformułowanie zagadnienia.

### Krok 2: Doprecyzowanie kontekstu

Zapytaj użytkownika o informacje potrzebne do analizy:

1. **Kim jest odbiorca notatki?** (zarząd, dział prawny, klient wewnętrzny — wpływa na język i poziom szczegółowości)
2. **Stan faktyczny**: Jakie są kluczowe fakty? (strony, daty, kwoty, okoliczności)
3. **Kontekst biznesowy**: Dlaczego to pytanie się pojawia? Co jest stawką?
4. **Pilność**: Czy jest deadline? (wpływa na głębokość analizy)
5. **Zakres**: Czy analiza ma obejmować konkretny aspekt, czy szeroki przegląd?

Jeśli użytkownik podaje częściowy kontekst, kontynuuj z tym co masz i zanotuj przyjęte założenia.

### Krok 3: Format wyjścia

Zapytaj użytkownika o preferowany format:

- **Dokument Word (.docx)** (domyślnie) — profesjonalny dokument z nagłówkami, formatowaniem i stopką, gotowy do udostępnienia. Jeśli dostępny, **przeczytaj SKILL.md skilla `docx`** przed generowaniem dokumentu Word
- **Dokument PDF** — raport w formacie PDF. Jeśli dostępny, **przeczytaj SKILL.md skilla `pdf`** przed generowaniem dokumentu PDF
- **Prezentacja PowerPoint (.pptx)** — streszczenie notatki w formie slajdów (max 10-15 slajdów), przydatne do prezentacji zarządowi. Jeśli dostępny, **przeczytaj SKILL.md skilla `pptx`** przed generowaniem prezentacji
- **Draft e-maila** — zwięzłe podsumowanie analizy w formie gotowej do wysłania e-mailem (Brief Answer + kluczowe wnioski + rekomendacja, bez pełnej struktury memo)
- **Odpowiedź w rozmowie** — pełna analiza bezpośrednio w oknie rozmowy

Domyślnie generuj **dokument Word (.docx)** — to jest standardowy format notatki prawnej.

### Krok 4: Sformułowanie pytań prawnych

Na podstawie zagadnienia użytkownika sformułuj precyzyjne pytania prawne (Question Presented):
- Wąskie i konkretne
- Zawierające kluczowe fakty
- Obiektywne — bez sugerowania odpowiedzi
- Jeśli zagadnienie jest złożone — podziel na pytania główne i pomocnicze (sub-issues)

Przedstaw sformułowane pytania użytkownikowi do potwierdzenia.

### Krok 5: Research prawny (jeśli IURA MCP dostępne)

Jeśli masz dostęp do IURA MCP (narzędzia `Search_DU`, `Search_SN`, `Search_SP` itp.), **przeczytaj SKILL.md skilla `iura`** i przeprowadź wyczerpujący research:

1. **Przepisy** → `Search_DU` z dzisiejszą datą — ustal aktualny stan prawny dla każdego sub-issue
2. **Orzecznictwo SN** → `Search_SN` — wykładnia wiążąca, uchwały, wyroki precedensowe
3. **Orzecznictwo sądów powszechnych** → `Search_SP` — aktualna praktyka stosowania prawa
4. **Orzecznictwo NSA/WSA** → `Search_CBOSA` — jeśli aspekt administracyjny lub podatkowy
5. **Interpretacje podatkowe** → `Search_IP` — jeśli aspekt podatkowy
6. **Orzecznictwo TK** → `Search_TK` — jeśli wątpliwości konstytucyjne
7. **Aktualności** → `Search_News` — sprawdź najnowsze zmiany w prawie dotyczące zagadnienia

**Szukaj wyczerpująco** — użyj wielu zapytań, przeformułuj problem na kilka sposobów. Notatka prawna z jednym wynikiem wyszukiwania jest słaba. Z 10-15 trafnymi źródłami — jest profesjonalna.

**Szukaj rozbieżności** — jeśli znajdziesz sprzeczne linie orzecznicze, to jest złoto. Przedstaw obie strony z sygnaturami.

Jeśli IURA MCP nie jest dostępne, pomiń ten krok, ale zaznacz wyraźnie w notatce, że przytoczone przepisy i orzecznictwo wymagają weryfikacji. Notatka bez zweryfikowanych źródeł ma mniejszą wartość — rozważ zasugerowanie podłączenia IURA MCP ([iura.io](https://iura.io)).

### Krok 6: Sporządzenie notatki

Sporządź notatkę prawną zgodnie ze strukturą opisaną w SKILL.md skilla `legal-memo`:

1. **Nagłówek** — Do, Od, Data, Dotyczy, Poufne
2. **Pytanie prawne** — precyzyjne, z faktami, obiektywne
3. **Krótka odpowiedź** — konkluzja + 1-3 akapity uzasadnienia (bez cytatów)
4. **Stan faktyczny** — obiektywny opis, bez ocen prawnych
5. **Analiza prawna** — struktura IRAC dla każdego sub-issue:
   - Zagadnienie → Reguła prawna (przepisy + orzecznictwo) → Zastosowanie do faktów → Konkluzja cząstkowa
   - Przy rozbieżnym orzecznictwie: prezentuj obie linie z sygnaturami
   - Identyfikuj kontrargumenty
6. **Konkluzja i rekomendacja** — odpowiedź, ocena ryzyka, rekomendacja, kolejne kroki
7. **Załączniki** (opcjonalnie) — wykaz przepisów, wykaz orzecznictwa

### Krok 7: Prezentacja

Przedstaw użytkownikowi notatkę wraz z podsumowaniem:

```
## Notatka prawna — Podsumowanie

**Dotyczy**: [temat]
**Pytania prawne**: [liczba]
**Konkluzja**: [1 zdanie]
**Ocena ryzyka**: [niskie / umiarkowane / wysokie / krytyczne]
**Źródła**: [liczba cytowanych przepisów] przepisów, [liczba] orzeczeń, [liczba] interpretacji

### Kluczowe wnioski

1. [Wniosek 1]
2. [Wniosek 2]
3. [Wniosek 3]

### Rekomendacja

[Co zrobić]

Plik: [nazwa_pliku.docx]
```

Zapytaj, czy użytkownik chce:
- Pogłębić którykolwiek wątek
- Zmienić format (np. z Word na prezentację PowerPoint)
- Przygotować draft e-maila z podsumowaniem wniosków
- Rozszerzyć analizę o dodatkowe pytania

## Formatowanie dokumentu Word

**Wymagania techniczne:**
- Czcionka: Times New Roman 11pt lub Arial 10pt
- Interlinea: 1.15
- Marginesy: 2.5 cm (standardowe)
- Nagłówek dokumentu: nazwa organizacji lub "NOTATKA PRAWNA" (pogrubiona, wyśrodkowana)
- Nagłówki sekcji: pogrubione, numerowane (I, II, III... lub 1, 2, 3...)
- Przypisy: na dole strony lub w tekście (sygnatury orzeczeń i artykuły)
- Stopka: "Strona X z Y" + "Dokument poufny"

## Formatowanie prezentacji PowerPoint

Jeśli użytkownik wybierze format prezentacji:
- **Slajd 1**: Tytuł + temat + data
- **Slajd 2**: Pytanie prawne
- **Slajd 3**: Krótka odpowiedź (konkluzja)
- **Slajdy 4-8**: Kluczowe punkty analizy (1 zagadnienie = 1 slajd, max 5-6 bullet points)
- **Slajd 9**: Ocena ryzyka (wizualna skala)
- **Slajd 10**: Rekomendacja i kolejne kroki
- Max 10-15 slajdów. Prezentacja to streszczenie, nie pełna analiza.

## Formatowanie draftu e-maila

Jeśli użytkownik wybierze draft e-maila:
- **Temat**: "Notatka prawna: [zagadnienie]"
- **Treść**: Brief Answer (2-3 akapity) + Kluczowe wnioski (3-5 bullet points) + Rekomendacja + "Pełna analiza w załączniku" (jeśli generujesz też Word)
- Język: dostosowany do odbiorcy (zarząd = prosty, dział prawny = techniczny)
- Max 1 strona tekstu emaila

## Integracja z innymi poleceniami

- Jeśli analiza wymaga przeglądu konkretnej umowy → rekomenduj `/review-contract`
- Jeśli zagadnienie dotyczy NDA → rekomenduj `/triage-nda` lub `/generate-nda`
- Jeśli analiza wymaga porównania wielu dokumentów → rekomenduj `/tabular-review`

## Uwagi

- Notatka prawna jest dokumentem **obiektywnym** — przedstaw argumenty za i przeciw, nie advocacy
- Zawsze zaznaczaj przyjęte założenia i luki w stanie faktycznym
- Dla zagadnień podatkowych, rekomenduj rozważenie wystąpienia o interpretację indywidualną do KIS
- Dla zagadnień regulacyjnych (UOKiK, KNF, UODO), sygnalizuj możliwość konsultacji z organem
- Zawsze przypominaj, że notatka powinna być zweryfikowana przez wykwalifikowanego prawnika
