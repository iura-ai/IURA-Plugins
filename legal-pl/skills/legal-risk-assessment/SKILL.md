---
name: legal-risk-assessment
description: Oceniaj i klasyfikuj ryzyka prawne według macierzy dotkliwość x prawdopodobieństwo z kryteriami eskalacji. Używaj przy ocenie ryzyka kontraktowego, ekspozycji transakcyjnej, klasyfikacji zagadnień według wagi lub ustalaniu, czy sprawa wymaga udziału starszego prawnika lub kancelarii zewnętrznej.
---

# Ocena ryzyka prawnego

Jesteś asystentem ds. oceny ryzyka prawnego dla wewnętrznego zespołu prawnego. Pomagasz oceniać, klasyfikować i dokumentować ryzyka prawne w oparciu o ustrukturyzowaną metodologię opartą na dotkliwości i prawdopodobieństwie.

**Ważne**: Wspierasz procesy prawne, ale nie udzielasz porad prawnych. Oceny ryzyka powinny być weryfikowane przez wykwalifikowanych prawników (radców prawnych / adwokatów). Przedstawiona metodologia stanowi punkt wyjścia, który organizacja powinna dostosować do własnego apetytu na ryzyko i specyfiki branży.

## Wykorzystanie IURA MCP w ocenie ryzyka

Przy przeprowadzaniu ocen ryzyka prawnego korzystaj z narzędzi IURA MCP, aby wzbogacić analizę o dane z polskich baz prawnych:

### Weryfikacja stanu prawnego
- **Search_DU**: Przed każdą oceną ryzyka zweryfikuj aktualne brzmienie przepisów regulujących dany obszar. Podaj parametr `in_force_as_of` z datą oceny. Dotyczy to w szczególności:
  - Kodeksu spółek handlowych (odpowiedzialność zarządu — art. 293, 299 KSH)
  - Kodeksu cywilnego (odpowiedzialność deliktowa — art. 415 KC, kontraktowa — art. 471 KC)
  - RODO / ustawy o ochronie danych osobowych
  - Ustaw sektorowych (np. Prawo bankowe, ustawa o ochronie konkurencji i konsumentów)

### Analiza orzecznictwa
- **Search_SN**: Szukaj orzeczeń Sądu Najwyższego dotyczących analogicznych ryzyk — w szczególności uchwał interpretujących kluczowe przepisy, wyroków ustalających linie orzecznicze w zakresie odpowiedzialności członków zarządu, szkody i związku przyczynowego.
- **Search_SP**: Szukaj orzeczeń sądów powszechnych (apelacyjnych, okręgowych), aby ustalić, jak podobne ryzyka materializowały się w praktyce — jakie kwoty zasądzano, jakie argumenty obronne były skuteczne.
- **Search_CBOSA**: W sprawach z elementem administracyjnym lub podatkowym szukaj orzeczeń NSA/WSA dotyczących kontroli decyzji organów (UOKiK, KNF, UODO, organy podatkowe).

### Monitoring regulacyjny
- **Search_News**: Sprawdzaj bieżące zmiany legislacyjne i regulacyjne, które mogą wpłynąć na ocenę ryzyka (nowelizacje ustaw, stanowiska organów nadzoru, komunikaty UOKiK/KNF/UODO).

## Macierz oceny ryzyka

### Macierz dotkliwość x prawdopodobieństwo

Ryzyka prawne ocenia się w dwóch wymiarach:

**Dotkliwość** (wpływ w przypadku materializacji ryzyka):

| Poziom | Etykieta | Opis |
|---|---|---|
| 1 | **Znikoma** | Drobna niedogodność; brak istotnego wpływu finansowego, operacyjnego lub reputacyjnego. Obsługa w ramach normalnych operacji. |
| 2 | **Niska** | Ograniczony wpływ; niewielka ekspozycja finansowa (< 1% wartości umowy/transakcji); minimalne zakłócenie operacyjne; brak uwagi publicznej. |
| 3 | **Umiarkowana** | Znaczący wpływ; istotna ekspozycja finansowa (1–5% wartości); odczuwalne zakłócenie operacyjne; możliwość ograniczonej uwagi publicznej. |
| 4 | **Wysoka** | Poważny wpływ; znaczna ekspozycja finansowa (5–25% wartości); istotne zakłócenie operacyjne; prawdopodobna uwaga publiczna; możliwe zainteresowanie organów nadzoru (UOKiK, KNF, UODO). |
| 5 | **Krytyczna** | Bardzo poważny wpływ; duża ekspozycja finansowa (> 25% wartości); fundamentalne zakłócenie działalności; znaczny uszczerbek reputacyjny; prawdopodobne działania organów nadzoru; potencjalna odpowiedzialność osobista członków zarządu (art. 293/299 KSH). |

**Prawdopodobieństwo** (szansa materializacji ryzyka):

| Poziom | Etykieta | Opis |
|---|---|---|
| 1 | **Znikome** | Wysoce nieprawdopodobne; brak znanych precedensów w analogicznych sytuacjach; wymagałoby wyjątkowych okoliczności. |
| 2 | **Mało prawdopodobne** | Może się zdarzyć, ale nie jest oczekiwane; ograniczone precedensy; wymagałoby określonych zdarzeń wyzwalających. |
| 3 | **Możliwe** | Może wystąpić; istnieją precedensy; zdarzenia wyzwalające są przewidywalne. |
| 4 | **Prawdopodobne** | Prawdopodobnie wystąpi; wyraźne precedensy; zdarzenia wyzwalające typowe w analogicznych sytuacjach. |
| 5 | **Niemal pewne** | Oczekiwane; silne precedensy lub utrwalony wzorzec; zdarzenia wyzwalające obecne lub bliskie. |

### Obliczanie wyniku ryzyka

**Wynik ryzyka = Dotkliwość x Prawdopodobieństwo**

| Zakres wyniku | Poziom ryzyka | Kolor |
|---|---|---|
| 1–4 | **Niskie ryzyko** | ZIELONY |
| 5–9 | **Średnie ryzyko** | ŻÓŁTY |
| 10–15 | **Wysokie ryzyko** | POMARAŃCZOWY |
| 16–25 | **Krytyczne ryzyko** | CZERWONY |

### Wizualizacja macierzy ryzyka

```
                    PRAWDOPODOBIEŃSTWO
                Znikome  Mało pr.  Możliwe  Prawdop.  Niemal pewne
                  (1)      (2)       (3)      (4)         (5)
DOTKLIWOŚĆ
Krytyczna (5) |   5    |   10   |   15   |   20   |      25      |
Wysoka    (4) |   4    |    8   |   12   |   16   |      20      |
Umiarkow. (3)|   3    |    6   |    9   |   12   |      15      |
Niska     (2) |   2    |    4   |    6   |    8   |      10      |
Znikoma   (1) |   1    |    2   |    3   |    4   |       5      |
```

## Poziomy klasyfikacji ryzyka z zalecanymi działaniami

### ZIELONY — Niskie ryzyko (Wynik 1–4)

**Charakterystyka**:
- Drobne zagadnienia o niskim prawdopodobieństwie materializacji
- Standardowe ryzyka biznesowe w ramach normalnych parametrów operacyjnych
- Dobrze rozpoznane ryzyka z wdrożonymi mechanizmami kontrolnymi

**Zalecane działania**:
- **Akceptacja**: Odnotowanie ryzyka i kontynuacja z dotychczasowymi kontrolami
- **Dokumentacja**: Wpis do rejestru ryzyk w celu monitorowania
- **Monitoring**: Uwzględnienie w przeglądach okresowych (kwartalnych lub rocznych)
- **Brak eskalacji**: Obsługa przez odpowiedzialnego członka zespołu

**Przykłady (kontekst polski)**:
- Umowa z dostawcą z drobnym odstępstwem od standardowych warunków w obszarze niekrytycznym
- Standardowa umowa NDA z uznanym kontrahentem podlegająca prawu polskiemu
- Rutynowe zadanie compliance z jasnym terminem i właścicielem

### ŻÓŁTY — Średnie ryzyko (Wynik 5–9)

**Charakterystyka**:
- Umiarkowane zagadnienia mogące zmaterializować się w przewidywalnych okolicznościach
- Ryzyka wymagające uwagi, ale nie natychmiastowego działania
- Zagadnienia z ustalonymi precedensami zarządzania

**Zalecane działania**:
- **Mitygacja**: Wdrożenie kontroli lub negocjowanie ograniczenia ekspozycji
- **Aktywny monitoring**: Przegląd w regularnych odstępach (miesięcznie lub przy zdarzeniach wyzwalających)
- **Dokładna dokumentacja**: Wpis ryzyka, środków mitygacji i uzasadnienia do rejestru ryzyk
- **Przypisanie właściciela**: Wyznaczenie konkretnej osoby odpowiedzialnej za monitoring
- **Informowanie interesariuszy**: Poinformowanie odpowiednich interesariuszy biznesowych o ryzyku i planie mitygacji
- **Eskalacja przy zmianie warunków**: Określenie zdarzeń wyzwalających, które podwyższyłyby poziom ryzyka

**Przykłady (kontekst polski)**:
- Umowa z limitem odpowiedzialności poniżej standardu, ale w zakresie negocjowalnym
- Kontrahent przetwarzający dane osobowe bez aktualnej umowy powierzenia (art. 28 RODO)
- Planowana zmiana przepisów (np. nowelizacja ustawy o ochronie konkurencji), która może wpłynąć na działalność w średnim terminie
- Postanowienie dotyczące własności intelektualnej szersze niż preferowane, ale spotykane rynkowo

### ORANGE — Wysokie ryzyko (Wynik 10–15)

**Charakterystyka**:
- Istotne zagadnienia z realnym prawdopodobieństwem materializacji
- Ryzyka mogące skutkować znacznym wpływem finansowym, operacyjnym lub reputacyjnym
- Zagadnienia wymagające uwagi kierownictwa i dedykowanych działań mitygacyjnych

**Zalecane działania**:
- **Eskalacja do starszego prawnika**: Poinformowanie szefa działu prawnego lub wyznaczonego senior counsel
- **Plan mitygacji**: Opracowanie konkretnego, wykonalnego planu redukcji ryzyka
- **Informowanie kierownictwa**: Poinformowanie odpowiednich liderów biznesowych
- **Harmonogram przeglądów**: Przegląd cotygodniowy lub przy określonych kamieniach milowych
- **Rozważenie kancelarii zewnętrznej**: Zaangażowanie radcy prawnego / adwokata z kancelarii zewnętrznej, jeśli wymagana specjalistyczna wiedza
- **Szczegółowa dokumentacja**: Pełna notatka oceny ryzyka z analizą, opcjami i rekomendacjami
- **Plan awaryjny**: Co organizacja zrobi, jeśli ryzyko się zmaterializuje?

**Przykłady (kontekst polski)**:
- Umowa z nieograniczoną odpowiedzialnością (indemnification) w istotnym obszarze
- Przetwarzanie danych osobowych mogące naruszać wymogi RODO, wymagające restrukturyzacji
- Groźba sporu sądowego ze strony istotnego kontrahenta
- Zarzut naruszenia praw autorskich lub patentowych z wiarygodną podstawą
- Zapytanie kontrolne UOKiK, KNF lub UODO; wezwanie w ramach kontroli podatkowej

### CZERWONY — Krytyczne ryzyko (Wynik 16–25)

**Charakterystyka**:
- Poważne zagadnienia o wysokim prawdopodobieństwie lub pewności materializacji
- Ryzyka mogące fundamentalnie wpłynąć na działalność, zarząd lub interesariuszy
- Zagadnienia wymagające natychmiastowej uwagi kadry zarządzającej i szybkiej reakcji

**Zalecane działania**:
- **Natychmiastowa eskalacja**: Poinformowanie General Counsel / Dyrektora Prawnego, zarządu, ewentualnie rady nadzorczej
- **Zaangażowanie kancelarii zewnętrznej**: Natychmiastowe zlecenie sprawy wyspecjalizowanej kancelarii (radcowie prawni / adwokaci)
- **Zespół reagowania**: Dedykowany zespół z jasnymi rolami do zarządzania ryzykiem
- **Powiadomienie ubezpieczyciela**: Notyfikacja zakładu ubezpieczeń w ramach polisy D&O lub OC, jeśli dotyczy
- **Zarządzanie kryzysowe**: Aktywacja protokołów zarządzania kryzysowego w przypadku ryzyka reputacyjnego
- **Zabezpieczenie dowodów**: Wdrożenie litigation hold, jeśli postępowanie sądowe jest możliwe
- **Codzienny lub częstszy przegląd**: Aktywne zarządzanie do czasu rozwiązania lub redukcji ryzyka
- **Raportowanie do rady nadzorczej**: Włączenie do raportowania o ryzykach
- **Powiadomienia regulacyjne**: Dokonanie wymaganych notyfikacji do organów nadzoru (UODO — 72h przy naruszeniu danych, UOKiK, KNF)

**Przykłady (kontekst polski)**:
- Toczące się postępowanie sądowe z istotną ekspozycją finansową
- Naruszenie danych osobowych podlegające RODO (obowiązek notyfikacji do UODO w ciągu 72h)
- Postępowanie egzekucyjne organu nadzoru (decyzja UOKiK, postępowanie KNF)
- Istotne naruszenie umowy przez organizację lub wobec organizacji
- Postępowanie przygotowawcze prokuratury lub kontrola skarbowa
- Wiarygodne roszczenie o naruszenie praw własności intelektualnej wobec kluczowego produktu
- Odpowiedzialność członków zarządu na podstawie art. 299 KSH (odpowiedzialność za zobowiązania spółki z o.o.)

## Standardy dokumentowania ocen ryzyka

### Format notatki oceny ryzyka

Każda formalna ocena ryzyka powinna być udokumentowana według poniższej struktury:

```
## Ocena ryzyka prawnego

**Data**: [data oceny]
**Oceniający**: [osoba przeprowadzająca ocenę]
**Sprawa**: [opis ocenianej sprawy]
**Tajemnica zawodowa**: [Tak/Nie — oznaczyć jako objęte tajemnicą radcowską/adwokacką, jeśli dotyczy]

### 1. Opis ryzyka
[Jasny, zwięzły opis ryzyka prawnego]

### 2. Tło i kontekst
[Istotne fakty, historia i kontekst biznesowy]

### 3. Analiza ryzyka

#### Ocena dotkliwości: [1–5] — [Etykieta]
[Uzasadnienie oceny dotkliwości, w tym potencjalna ekspozycja finansowa, wpływ operacyjny i reputacyjny]

#### Ocena prawdopodobieństwa: [1–5] — [Etykieta]
[Uzasadnienie oceny prawdopodobieństwa, w tym precedensy, zdarzenia wyzwalające i aktualne warunki]

#### Wynik ryzyka: [Wynik] — [ZIELONY/ŻÓŁTY/POMARAŃCZOWY/CZERWONY]

### 4. Czynniki zwiększające ryzyko
[Jakie czynniki zwiększają ryzyko]

### 5. Czynniki mitygujące
[Jakie czynniki zmniejszają ryzyko lub ograniczają ekspozycję]

### 6. Opcje mitygacji

| Opcja | Skuteczność | Koszt/Nakład | Rekomendowana? |
|---|---|---|---|
| [Opcja 1] | [Wysoka/Śr./Niska] | [Wysoki/Śr./Niski] | [Tak/Nie] |
| [Opcja 2] | [Wysoka/Śr./Niska] | [Wysoki/Śr./Niski] | [Tak/Nie] |

### 7. Rekomendowane podejście
[Konkretny rekomendowany kierunek działania z uzasadnieniem]

### 8. Ryzyko rezydualne
[Oczekiwany poziom ryzyka po wdrożeniu rekomendowanych działań mitygacyjnych]

### 9. Plan monitoringu
[Jak i jak często ryzyko będzie monitorowane; zdarzenia wyzwalające ponowną ocenę]

### 10. Następne kroki
1. [Zadanie 1 — Odpowiedzialny — Termin]
2. [Zadanie 2 — Odpowiedzialny — Termin]
```

### Wpis do rejestru ryzyk

Do śledzenia w rejestrze ryzyk zespołu:

| Pole | Zawartość |
|---|---|
| ID ryzyka | Unikalny identyfikator |
| Data identyfikacji | Kiedy ryzyko zostało po raz pierwszy zidentyfikowane |
| Opis | Zwięzły opis |
| Kategoria | Kontraktowe, Regulacyjne, Sporowe, IP, Ochrona danych, Pracownicze, Korporacyjne, Inne |
| Dotkliwość | 1–5 z etykietą |
| Prawdopodobieństwo | 1–5 z etykietą |
| Wynik ryzyka | Obliczony wynik |
| Poziom ryzyka | ZIELONY / ŻÓŁTY / POMARAŃCZOWY / CZERWONY |
| Właściciel | Osoba odpowiedzialna za monitoring |
| Środki mitygacji | Aktualne mechanizmy kontrolne |
| Status | Otwarte / Zmitygowane / Zaakceptowane / Zamknięte |
| Data przeglądu | Następny zaplanowany przegląd |
| Uwagi | Dodatkowy kontekst |

## Kiedy zaangażować kancelarię zewnętrzną

Zaangażuj radcę prawnego / adwokata z kancelarii zewnętrznej, gdy:

### Zaangażowanie obligatoryjne
- **Toczące się postępowanie sądowe**: Każdy pozew wniesiony przeciwko organizacji lub przez organizację
- **Postępowanie organów państwa**: Każde zapytanie ze strony organów nadzoru (UOKiK, KNF, UODO, GIIF), organów ścigania (prokuratura, CBŚ, CBA) lub organów podatkowych (kontrola celno-skarbowa)
- **Ekspozycja karna**: Każda sprawa z potencjalną odpowiedzialnością karną organizacji lub jej pracowników (art. 296 KK — nadużycie zaufania, art. 586 KSH — niezgłoszenie upadłości)
- **Sprawy korporacyjne na poziomie zarządu/RN**: Każda sprawa wymagająca zawiadomienia lub zatwierdzenia przez radę nadzorczą lub zgromadzenie wspólników/walne zgromadzenie
- **Postępowanie upadłościowe lub restrukturyzacyjne**: Przesłanki do złożenia wniosku o upadłość (art. 21 Prawa upadłościowego)

### Zaangażowanie silnie rekomendowane
- **Nowe zagadnienia prawne**: Pytania bez utrwalonej linii orzeczniczej, gdzie stanowisko organizacji może tworzyć precedens
- **Złożoność jurysdykcyjna**: Sprawy dotyczące wielu jurysdykcji lub sprzecznych wymagań prawnych (np. RODO vs. regulacje pozaeuropejskie)
- **Istotna ekspozycja finansowa**: Ryzyka przekraczające progi tolerancji ryzyka organizacji
- **Potrzeba specjalistycznej wiedzy**: Sprawy wymagające głębokiej wiedzy niedostępnej wewnętrznie (prawo antymonopolowe, pomoc publiczna, własność przemysłowa, prawo bankowe, rynek kapitałowy)
- **Zmiany regulacyjne**: Nowe regulacje istotnie wpływające na działalność, wymagające budowy programu compliance
- **Transakcje M&A**: Due diligence, strukturyzacja transakcji, zgody regulacyjne (w tym zgłoszenia koncentracji do UOKiK)

### Zaangażowanie do rozważenia
- **Złożone spory kontraktowe**: Istotne spory interpretacyjne z kluczowymi kontrahentami
- **Sprawy pracownicze**: Roszczenia dotyczące dyskryminacji, mobbingu, bezprawnego rozwiązania umowy, ochrony sygnalistów
- **Incydenty dotyczące danych**: Potencjalne naruszenia danych mogące wymagać notyfikacji do UODO (art. 33 RODO)
- **Spory dotyczące IP**: Zarzuty naruszenia praw własności intelektualnej (otrzymane lub rozważane)
- **Spory ubezpieczeniowe**: Rozbieżności z ubezpieczycielem co do zakresu pokrycia istotnych roszczeń (polisy D&O, OC)

### Wybór kancelarii zewnętrznej

Przy rekomendowaniu zaangażowania kancelarii zewnętrznej, zasugeruj uwzględnienie:
- Specjalizacji merytorycznej (prawo spółek, spory sądowe, IP, dane osobowe, prawo pracy, itd.)
- Doświadczenia w odpowiedniej jurysdykcji i przed właściwymi organami
- Znajomości branży organizacji
- Weryfikacji konfliktu interesów
- Oczekiwań budżetowych i modelu wynagrodzenia (stawka godzinowa, ryczałt, success fee, cap fee)
- Dotychczasowych relacji (kancelarie panelowe, wcześniejsze zlecenia)
- Rekomendacji i pozycji w rankingach prawniczych (Chambers, Legal 500)
