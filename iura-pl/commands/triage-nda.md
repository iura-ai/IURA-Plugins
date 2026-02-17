---
description: Szybki triaż przychodzących umów NDA — klasyfikacja jako standardowe zatwierdzenie, przegląd prawnika lub pełna analiza prawna (prawo polskie)
argument-hint: "<plik NDA lub tekst>"
---

# /triage-nda -- Triaż umowy o zachowaniu poufności (NDA)

Szybki triaż przychodzących umów NDA (umów o zachowaniu poufności) według standardowych kryteriów przesiewowych. Klasyfikacja NDA do odpowiedniej ścieżki: standardowe zatwierdzenie, przegląd prawnika lub pełna analiza prawna — z uwzględnieniem polskich przepisów o tajemnicy przedsiębiorstwa (UZNK) i prawa cywilnego.

**Ważne**: To polecenie wspiera pracę prawnika, ale nie stanowi porady prawnej. Wyniki triażu powinny być zweryfikowane przez wykwalifikowanego prawnika.

## Wywołanie

```
/triage-nda
```

## Przebieg pracy

### Krok 1: Przyjęcie NDA

Przyjmij umowę NDA w dowolnym formacie:
- **Plik**: PDF, DOCX lub inny format dokumentu
- **URL**: Link do NDA w systemie dokumentów
- **Wklejony tekst**: Tekst NDA wklejony bezpośrednio

Jeśli NDA nie zostało dostarczone, poproś użytkownika o jego przekazanie.

### Krok 2: Format wyjścia

Zapytaj użytkownika o preferowany format wyniku:
- **Odpowiedź w rozmowie** (domyślnie) — pełny raport triażu bezpośrednio w oknie rozmowy
- **Dokument Word (.docx)** — profesjonalny raport gotowy do udostępnienia
- **Dokument PDF** — raport w formacie PDF

### Krok 3: Załadowanie playbooka NDA

Poszukaj kryteriów przesiewowych NDA w ustawieniach lokalnych (np. `iura.local.md`).

Playbook NDA powinien definiować:
- Wymagania co do wzajemności vs. jednostronności zobowiązań
- Dopuszczalne okresy obowiązywania
- Wymagane wyłączenia (carveouts)
- Zakazane postanowienia
- Wymagania specyficzne dla organizacji

**Jeśli playbook NDA nie jest skonfigurowany:**
- Kontynuuj z rozsądnymi domyślnymi standardami rynkowymi
- Wyraźnie zaznacz, że stosowane są wartości domyślne
- Wartości domyślne:
  - Wzajemne zobowiązania wymagane (chyba że organizacja jest wyłącznie stroną ujawniającą)
  - Okres: 2–3 lata standardowo, do 5 lat dla tajemnic przedsiębiorstwa
  - Wymagane standardowe wyłączenia: niezależnie opracowane, publicznie dostępne, prawidłowo otrzymane od osoby trzeciej, wymagane prawem
  - Brak postanowień o zakazie pozyskiwania pracowników (non-solicitation)
  - Brak postanowień o zakazie konkurencji (non-compete)
  - Brak klauzuli residuals (lub wąsko zakrojona, jeśli obecna)
  - Prawo właściwe: prawo polskie lub inna rozsądna jurysdykcja handlowa

### Krok 4: Weryfikacja przepisów (jeśli IURA MCP dostępne)

Jeśli masz dostęp do IURA MCP (narzędzia `Search_DU`, `Search_SN` itp.), **przeczytaj SKILL.md skilla `iura`** i zweryfikuj aktualne brzmienie kluczowych przepisów: swoboda umów (KC), tajemnica przedsiębiorstwa (UZNK), kary umowne (KC). Cytowanie przepisów z pamięci niesie ryzyko halucynacji. Dzięki IURA MCP możesz też wyszukać orzecznictwo dot. NDA i cytować konkretne sygnatury w raporcie triażu. Jeśli IURA MCP nie jest dostępne, pomiń ten krok, ale zaznacz w raporcie, że przytoczone przepisy wymagają weryfikacji.

### Krok 5: Szybki przesiew

Oceń NDA wobec każdego kryterium przesiewowego:

| Kryterium | Weryfikacja |
|-----------|-------------|
| **Wzajemna vs. jednostronna** | Czy zobowiązania są wzajemne? Jeśli jednostronne — czy to odpowiednie dla relacji? |
| **Definicja informacji poufnych** | Rozsądny zakres? Nie nadmiernie szeroka (np. „wszelkie informacje dowolnego rodzaju")? Zgodność z definicją tajemnicy przedsiębiorstwa z art. 11 UZNK? |
| **Okres obowiązywania** | W dopuszczalnym zakresie? Rozsądny dla typu informacji? |
| **Standardowe wyłączenia** | Wszystkie wymagane wyłączenia obecne? (niezależne opracowanie, wiedza publiczna, otrzymanie od osoby trzeciej, nakaz prawny) |
| **Dozwolone ujawnienia** | Możliwość udostępnienia pracownikom, doradcom, podwykonawcom, którzy muszą wiedzieć? |
| **Zwrot/zniszczenie** | Rozsądne zobowiązania po rozwiązaniu? Pozwala na zachowanie kopii dla celów prawnych/compliance? |
| **Klauzula residuals** | Jeśli obecna — wąsko zakrojona do niezapisanej pamięci? |
| **Zakaz pozyskiwania pracowników** | Czy zawiera postanowienia non-solicit? |
| **Zakaz konkurencji** | Czy zawiera postanowienia non-compete? (Uwaga: mogą wymagać odrębnej regulacji i odpłatności wg prawa polskiego) |
| **Zabezpieczenie roszczeń** | Rozsądne czy jednostronne? Kary umowne — proporcjonalne? Możliwość miarkowania (art. 484 § 2 KC)? |
| **Prawo właściwe** | Akceptowalna jurysdykcja? Preferowane prawo polskie? |
| **Cesja** | Rozsądne postanowienia o przeniesieniu praw? |
| **Nietypowe postanowienia** | Klauzule niestandardowe, które nie powinny znajdować się w NDA? |

### Krok 6: Klasyfikacja

Na podstawie wyników przesiewu przypisz klasyfikację:

#### ZIELONY -- Standardowe zatwierdzenie
Wszystkie kryteria spełnione. NDA jest zgodne ze standardem rynkowym i polskim prawem, bez nietypowych postanowień.
- **Ścieżka**: Zatwierdzenie i podpisanie w standardowym trybie
- **Działanie**: Przejście do podpisu zgodnie ze standardową delegacją uprawnień

#### ŻÓŁTY -- Wymagany przegląd prawnika
Jedno lub więcej kryteriów wykazuje drobne odchylenia wymagające przeglądu, ale potencjalnie akceptowalne:
- Definicja informacji poufnych szersza niż idealna, ale nie nieuzasadniona
- Okres dłuższy niż standardowy, ale w zakresie rynkowym
- Klauzula residuals obecna, ale wąsko zakrojona
- Drobne preferencje co do jurysdykcji
- Brak jednego standardowego wyłączenia, które można dodać
- Kary umowne wymagające weryfikacji proporcjonalności
- **Ścieżka**: Oznacz konkretne zagadnienia do przeglądu prawnika
- **Działanie**: Prawnik może rozwiązać w jednym przeglądzie

#### CZERWONY -- Istotne problemy
Jedno lub więcej kryteriów wykazuje istotne odchylenia stanowiące ryzyko:
- Jednostronne zobowiązania, gdy wymagane są wzajemne
- Brak krytycznych wyłączeń (np. brak wyłączenia niezależnego opracowania)
- Postanowienia non-solicitation lub non-compete wbudowane w NDA (mogą wymagać odrębnej umowy i odpłatności wg art. 101¹ KP)
- Nieuzasadniony okres (10+ lat) bez uzasadnienia
- Nadmiernie szeroka definicja wykraczająca poza tajemnicę przedsiębiorstwa w rozumieniu UZNK
- Nietypowe postanowienia (wyłączność, prawo audytu, przeniesienie IP)
- Wysoce niekorzystna jurysdykcja bez pola do negocjacji
- Klauzule potencjalnie sprzeczne z przepisami bezwzględnie obowiązującymi KC
- **Ścieżka**: Wymagany pełny przegląd prawny
- **Działanie**: Nie podpisywać; wymaga negocjacji lub kontroferty

### Krok 7: Generowanie raportu triażu

Wygeneruj ustrukturyzowany raport:

```
## Raport triażu NDA

**Klasyfikacja**: [ZIELONY / ŻÓŁTY / CZERWONY]
**Strony**: [nazwy stron]
**Typ**: [Wzajemna / Jednostronna (strona ujawniająca) / Jednostronna (strona otrzymująca)]
**Okres obowiązywania**: [czas trwania]
**Prawo właściwe**: [jurysdykcja]
**Podstawa przeglądu**: [Playbook / Standardy domyślne + prawo polskie]

## Wyniki przesiewu

| Kryterium | Status | Uwagi |
|-----------|--------|-------|
| Wzajemność zobowiązań | [OK/UWAGA/PROBLEM] | [szczegóły] |
| Zakres definicji | [OK/UWAGA/PROBLEM] | [szczegóły] |
| Okres obowiązywania | [OK/UWAGA/PROBLEM] | [szczegóły] |
| Standardowe wyłączenia | [OK/UWAGA/PROBLEM] | [szczegóły] |
| [itd.] | | |

## Wykryte problemy

### [Problem 1 -- ŻÓŁTY/CZERWONY]
**Co**: [opis]
**Ryzyko**: [co może pójść nie tak]
**Podstawa prawna**: [przepis KC/UZNK]
**Proponowane rozwiązanie**: [konkretne brzmienie lub podejście]

[Powtórz dla każdego problemu]

## Rekomendacja

[Konkretny następny krok: zatwierdzić, skierować do przeglądu ze wskazówkami, lub odrzucić/kontrować]

## Kolejne kroki

1. [Działanie 1]
2. [Działanie 2]
```

### Krok 8: Sugestia routingu

Na podstawie klasyfikacji:
- **ZIELONY**: Zasugeruj przejście do podpisu w ramach standardowej delegacji uprawnień
- **ŻÓŁTY**: Wskaż konkretne zagadnienia wymagające uwagi prawnika i zasugeruj skierowanie do właściwego recenzenta
- **CZERWONY**: Rekomenduj zaangażowanie prawnika w pełny przegląd; zaproponuj wzór NDA organizacji jako kontrpropozycję, jeśli jest dostępny

## Uwagi

- Jeśli dokument nie jest w rzeczywistości NDA (np. jest oznaczony jako NDA, ale zawiera istotne warunki handlowe), natychmiast oznacz jako CZERWONY i rekomenduj pełny przegląd umowy
- Dla NDA będących częścią większej umowy (np. sekcja poufności w umowie ramowej), zanotuj, że szerszy kontekst umowy może wpływać na analizę
- Zawsze zaznaczaj, że to narzędzie przesiewowe — prawnik powinien przejrzeć wszelkie kwestie, co do których użytkownik ma wątpliwości
- Przy powoływaniu się na tajemnicę przedsiębiorstwa, stosuj aktualną definicję z art. 11 UZNK
