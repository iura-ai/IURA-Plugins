---
description: Generate contextual briefings for legal work — daily summary, topic research, or incident response (Polish law context with IURA MCP)
argument-hint: "[dzienny | tematyczny <zapytanie> | incydent]"
---

# /brief -- Briefing dla zespołu prawnego

> Jeśli widzisz nieznane symbole zastępcze lub chcesz sprawdzić podłączone narzędzia, zobacz [CONNECTORS.md](../CONNECTORS.md).

Generowanie kontekstowych briefingów dla pracy prawnej. Obsługuje trzy tryby: briefing dzienny, briefing tematyczny i briefing incydentowy — z możliwością wzbogacenia o analizę polskiego prawa i orzecznictwa dzięki IURA MCP.

**Ważne**: To polecenie wspiera pracę prawnika, ale nie stanowi porady prawnej. Briefingi powinny być zweryfikowane przez wykwalifikowanych prawników przed podjęciem decyzji.

## Wywołanie

```
/brief dzienny                    # Poranny briefing z podsumowaniem
/brief tematyczny [zapytanie]     # Briefing badawczy na konkretny temat prawny
/brief incydent [temat]           # Szybki briefing o rozwijającej się sytuacji
```

Jeśli tryb nie jest podany, zapytaj użytkownika, jakiego briefingu potrzebuje.

## Tryby

---

### Briefing dzienny

Poranne podsumowanie wszystkiego, co członek zespołu prawnego powinien wiedzieć, aby rozpocząć dzień.

#### Źródła do przeskanowania

Sprawdź każde podłączone źródło pod kątem elementów istotnych prawnie:

**E-mail (jeśli podłączony):**
- Nowe prośby o przegląd umów
- Pytania i raporty z zakresu compliance
- Odpowiedzi kontrahentów w aktywnych negocjacjach
- Pilne elementy ze skrzynki zespołu prawnego
- Komunikacja z kancelarią zewnętrzną
- Newslettery z aktualizacjami prawnymi i regulacyjnymi

**Kalendarz (jeśli podłączony):**
- Dzisiejsze spotkania wymagające przygotowania prawnego (posiedzenia zarządu, przeglądy transakcji, rozmowy z kontrahentami)
- Nadchodzące terminy w tym tygodniu (wygaśnięcia umów, terminy procesowe, terminy odpowiedzi)
- Cykliczne spotkania zespołu prawnego

**Czat (jeśli podłączony):**
- Wiadomości z kanałów zespołu prawnego od ostatniego briefingu
- Bezpośrednie wiadomości z prośbami o opinię prawną
- Wzmianki o tematach prawnych (umowa, compliance, RODO, NDA, regulamin)
- Eskalacje lub pilne zapytania

**CLM (jeśli podłączony):**
- Umowy oczekujące na przegląd lub podpis
- Zbliżające się daty wygaśnięcia (najbliższe 30 dni)
- Nowo podpisane umowy

**CRM (jeśli podłączony):**
- Transakcje przechodzące do etapów wymagających zaangażowania prawnego
- Nowe szanse biznesowe oznaczone do przeglądu prawnego

#### Format wyjściowy

```
## Dzienny briefing prawny -- [Data]

### Pilne / Wymaga działania
[Elementy wymagające natychmiastowej uwagi, posortowane wg pilności]

### Pipeline umów
- **Oczekujące na Twój przegląd**: [liczba i lista]
- **Oczekujące na odpowiedź kontrahenta**: [liczba i lista]
- **Zbliżające się terminy**: [elementy na ten tydzień]

### Nowe zapytania
[Prośby o przegląd umów, prośby o NDA, pytania compliance otrzymane od ostatniego briefingu]

### Kalendarz na dziś
[Spotkania z aspektem prawnym i potrzebne przygotowanie]

### Aktywność zespołu
[Kluczowe wiadomości lub aktualizacje z kanałów zespołu prawnego]

### Terminy w tym tygodniu
[Nadchodzące terminy i daty ważnych czynności]

### Niedostępne źródła
[Źródła, które nie zostały podłączone lub zwróciły błędy]
```

---

### Briefing tematyczny

Badanie i przygotowanie briefingu na konkretne pytanie lub temat prawny z wykorzystaniem dostępnych źródeł — wzbogacone o analizę polskiego prawa z IURA MCP.

#### Przebieg pracy

1. Przyjmij zapytanie tematyczne od użytkownika
2. Przeszukaj podłączone źródła wewnętrzne:
   - **Dokumenty**: Wewnętrzne notatki, wcześniejsze analizy, playbooki, precedensy
   - **E-mail**: Wcześniejsza korespondencja na temat
   - **Czat**: Dyskusje zespołu na temat
   - **CLM**: Powiązane umowy lub klauzule
3. **Analiza prawna z IURA MCP**:
   - **Przepisy prawa** (Search_DU): Wyszukaj obowiązujące przepisy dotyczące tematu z parametrem `in_force_as_of` ustawionym na dzisiejszą datę
   - **Orzecznictwo SN** (Search_SN): Wyszukaj kluczowe orzeczenia Sądu Najwyższego na ten temat
   - **Orzecznictwo sądów powszechnych** (Search_SP): Wyszukaj precedensy w sądach powszechnych
   - **Aktualności prawne** (Search_News): Wyszukaj bieżące informacje o zmianach w prawie lub projektach ustaw dotyczących tematu
   - **Orzecznictwo NSA/WSA** (Search_CBOSA): Jeśli temat dotyczy prawa administracyjnego lub podatkowego
   - **Interpretacje podatkowe** (Search_IP): Jeśli temat ma aspekty podatkowe
4. Zsyntetyzuj wyniki w ustrukturyzowany briefing

#### Format wyjściowy

```
## Briefing tematyczny: [Temat]

### Podsumowanie
[2-3 zdania streszczenia głównych ustaleń]

### Kontekst
[Kontekst i historia ze źródeł wewnętrznych]

### Stan prawny (IURA MCP)

#### Obowiązujące przepisy
[Kluczowe przepisy znalezione przez Search_DU z sygnaturami aktów prawnych]

#### Orzecznictwo
[Najistotniejsze orzeczenia SN i sądów powszechnych z sygnaturami]

#### Najnowsze zmiany
[Bieżące nowelizacje lub projekty ustaw znalezione przez Search_News]

### Aktualna pozycja organizacji
[Jakie jest obecne stanowisko lub podejście organizacji na podstawie dostępnych dokumentów]

### Kluczowe zagadnienia
[Istotne czynniki, ryzyka lub otwarte pytania]

### Precedens wewnętrzny
[Wcześniejsze decyzje, notatki lub stanowiska znalezione w źródłach wewnętrznych]

### Luki
[Jakich informacji brakuje lub jakie źródła nie były dostępne]

### Rekomendowane następne kroki
[Co użytkownik powinien zrobić z tą informacją]
```

#### Ważne uwagi
- Briefingi tematyczne syntetyzują dostępne źródła wewnętrzne i wyniki z IURA MCP; nie zastępują formalnej opinii prawnej
- IURA MCP zapewnia dostęp do aktualnych przepisów, orzecznictwa i interpretacji — wyniki te powinny być jednak zweryfikowane przez prawnika
- Zawsze zaznaczaj ograniczenia przeszukanych źródeł

---

### Briefing incydentowy

Szybki briefing dla rozwijających się sytuacji wymagających natychmiastowej uwagi prawnej (naruszenia danych osobowych, groźby procesowe, zapytania regulatorów, spory o IP, itp.).

#### Przebieg pracy

1. Przyjmij temat lub opis incydentu
2. Szybko przeskanuj wszystkie podłączone źródła w poszukiwaniu kontekstu:
   - **E-mail**: Korespondencja dotycząca incydentu
   - **Czat**: Dyskusje i eskalacje w czasie rzeczywistym
   - **Dokumenty**: Stosowne polityki, plany reagowania, ochrona ubezpieczeniowa
   - **Kalendarz**: Zaplanowane spotkania kryzysowe
   - **CLM**: Dotknięte umowy, postanowienia indemnifikacyjne, wymogi ubezpieczeniowe
3. **Analiza regulacyjna z IURA MCP**:
   - **Przepisy prawa** (Search_DU): Wyszukaj obowiązujące przepisy regulujące obowiązki notyfikacyjne i procedury reakcji na incydent (np. RODO, ustawa o ochronie danych osobowych, KSH, prawo telekomunikacyjne) z parametrem `in_force_as_of` ustawionym na dzisiejszą datę
   - **Orzecznictwo** (Search_SN, Search_SP, Search_CBOSA): Wyszukaj precedensy dotyczące podobnych incydentów i ich konsekwencji prawnych
   - **Decyzje UODO** (Search_News): Wyszukaj decyzje Prezesa UODO w podobnych sprawach, jeśli incydent dotyczy danych osobowych
4. Skompiluj w briefing do natychmiastowego działania

#### Format wyjściowy

```
## Briefing incydentowy: [Temat]
**Przygotowano**: [znacznik czasu]
**Klasyfikacja**: [ocena ważności, jeśli możliwa do określenia]

### Opis sytuacji
[Co jest wiadome o incydencie]

### Chronologia
[Chronologiczne podsumowanie zdarzeń na podstawie dostępnych źródeł]

### Wymogi regulacyjne (IURA MCP)

#### Obowiązki notyfikacyjne
[Terminy i adresaci zgłoszeń wynikające z przepisów znalezionych przez Search_DU — np. 72h na zgłoszenie do UODO wg art. 33 RODO]

#### Podstawy prawne
[Kluczowe przepisy i orzeczenia dotyczące tego typu incydentów]

### Bezpośrednie aspekty prawne
[Wymogi notyfikacyjne, obowiązki zabezpieczenia dowodów, kwestie tajemnicy adwokackiej]

### Dotknięte umowy
[Umowy, polisy ubezpieczeniowe lub inne porozumienia, których dotyczy incydent]

### Wewnętrzna reakcja
[Jakie działania podjęto dotychczas na podstawie e-mail/czat]

### Kluczowe kontakty
[Istotne kontakty wewnętrzne i zewnętrzne zidentyfikowane ze źródeł]

### Rekomendowane natychmiastowe działania
1. [Najpilniejsze działanie]
2. [Drugi priorytet]
3. [itd.]

### Luki informacyjne
[Czego jeszcze nie wiadomo i co należy ustalić]

### Sprawdzone źródła
[Co przeszukano i co nie było dostępne]
```

#### Ważne uwagi dla briefingów incydentowych
- Szybkość jest kluczowa. Przygotuj briefing szybko z dostępnymi informacjami, zamiast czekać na kompletne dane
- Natychmiast oznacz wszelkie obowiązki zabezpieczenia dowodów (litigation hold)
- Zanotuj kwestie tajemnicy zawodowej (oznacz briefing jako objęty tajemnicą adwokacką / materiał roboczy, jeśli to właściwe)
- Jeśli incydent może obejmować naruszenie danych osobowych, oznacz obowiązujące terminy zgłoszeń (72 godziny na zgłoszenie do Prezesa UODO wg art. 33 RODO) — zweryfikowane przez IURA MCP
- W przypadku incydentów z potencjalną odpowiedzialnością karną, wskaż odpowiednie przepisy KK/KKS (Search_DU)
- Rekomenduj zaangażowanie kancelarii zewnętrznej, jeśli sprawa jest znacząca

## Uwagi ogólne

- Jeśli źródła są niedostępne, wyraźnie zaznacz luki, aby użytkownik wiedział, czego nie sprawdzono
- Dla briefingów dziennych — ucz się preferencji użytkownika (co uznaje za przydatne, co chce filtrować)
- Briefingi powinny być praktyczne: każdy element powinien mieć jasny następny krok lub powód włączenia
- Utrzymuj briefingi zwięzłe. Linkuj do materiałów źródłowych zamiast reprodukować je w całości
- Wyniki z IURA MCP podawaj z sygnaturami (orzeczeń, aktów prawnych, interpretacji) dla łatwej weryfikacji
