---
description: Check the status of existing agreements with a vendor across all connected systems (Polish law context with IURA MCP)
argument-hint: "[nazwa kontrahenta]"
---

# /vendor-check -- Sprawdzenie kontrahenta

> Jeśli widzisz nieznane symbole zastępcze lub chcesz sprawdzić podłączone narzędzia, zobacz [CONNECTORS.md](../CONNECTORS.md).

Sprawdzenie statusu istniejących umów z kontrahentem we wszystkich podłączonych systemach. Skonsolidowany widok relacji prawnej — z weryfikacją wymogów prawnych dotyczących wymaganych umów na podstawie polskiego prawa dzięki IURA MCP.

**Ważne**: To polecenie wspiera pracę prawnika, ale nie stanowi porady prawnej. Raporty o statusie umów powinny być zweryfikowane z oryginałami dokumentów przez wykwalifikowanego prawnika.

## Wywołanie

```
/vendor-check [nazwa kontrahenta]
```

Jeśli nazwa kontrahenta nie jest podana, poproś użytkownika o jej wskazanie.

## Przebieg pracy

### Krok 1: Identyfikacja kontrahenta

Przyjmij nazwę kontrahenta od użytkownika. Uwzględnij typowe warianty:
- Pełna nazwa prawna vs. nazwa handlowa (np. „Grupa Allegro sp. z o.o." vs. „Allegro")
- Skróty (np. „PKO BP" vs. „Powszechna Kasa Oszczędności Bank Polski S.A.")
- Relacje spółka matka / spółka zależna
- Numer KRS lub NIP (jeśli podany, użyj do jednoznacznej identyfikacji)

Poproś użytkownika o doprecyzowanie, jeśli nazwa kontrahenta jest niejednoznaczna.

### Krok 2: Przeszukanie podłączonych systemów

Wyszukaj kontrahenta we wszystkich dostępnych podłączonych systemach, w kolejności priorytetowej:

#### CLM (System zarządzania cyklem życia umów) -- Jeśli podłączony
Wyszukaj wszystkie umowy z udziałem kontrahenta:
- Aktywne umowy
- Umowy wygasłe (ostatnie 3 lata)
- Umowy w negocjacji lub oczekujące na podpis
- Aneksy i załączniki

#### CRM -- Jeśli podłączony
Wyszukaj rekord kontrahenta:
- Status konta i typ relacji
- Powiązane szanse biznesowe lub transakcje
- Dane kontaktowe zespołu prawnego/kontraktowego kontrahenta

#### E-mail -- Jeśli podłączony
Wyszukaj istotną korespondencję:
- E-maile dotyczące umów (ostatnie 6 miesięcy)
- NDA lub umowy w załącznikach
- Wątki negocjacyjne

#### Dokumenty (np. OneDrive, SharePoint, Google Drive) -- Jeśli podłączony
Wyszukaj:
- Podpisane umowy
- Redline'y i projekty
- Materiały due diligence

#### Czat (np. Slack, Teams) -- Jeśli podłączony
Wyszukaj ostatnie wzmianki:
- Zapytania o umowy z tym kontrahentem
- Pytania prawne dotyczące kontrahenta
- Istotne dyskusje zespołu (ostatnie 3 miesiące)

### Krok 3: Zestawienie statusu umów

Dla każdej znalezionej umowy raportuj:

| Pole | Szczegóły |
|------|-----------|
| **Typ umowy** | NDA/Umowa poufności, Umowa ramowa (MSA), Zlecenie (SOW), Umowa powierzenia danych (DPA), SLA, Umowa licencyjna, itp. |
| **Status** | Aktywna, Wygasła, W negocjacji, Oczekuje na podpis |
| **Data wejścia w życie** | Od kiedy obowiązuje |
| **Data wygaśnięcia** | Kiedy wygasa lub odnawia się |
| **Automatyczne odnowienie** | Tak/Nie, z okresem odnowienia i terminem wypowiedzenia |
| **Kluczowe warunki** | Limit odpowiedzialności, prawo właściwe, postanowienia o rozwiązaniu, kary umowne |
| **Aneksy** | Wszelkie aneksy lub zmiany w aktach |

### Krok 4: Analiza luk z weryfikacją prawną (IURA MCP)

Zidentyfikuj, jakie umowy istnieją i jakich może brakować. Wykorzystaj IURA MCP do weryfikacji, które umowy są prawnie wymagane:

1. **Obowiązkowe umowy** (Search_DU): Wyszukaj obowiązujące przepisy określające wymóg zawarcia konkretnych umów z parametrem `in_force_as_of` ustawionym na dzisiejszą datę:
   - **Umowa powierzenia przetwarzania danych osobowych** (art. 28 RODO): Wymagana, jeśli kontrahent przetwarza dane osobowe w imieniu administratora
   - **Umowa o zachowaniu poufności**: Standardowa praktyka, choć ochrona tajemnicy przedsiębiorstwa wynika też z art. 11 UZNK
   - **Umowa o podwykonawstwo** (art. 647¹ KC): Jeśli kontrahent jest podwykonawcą w robotach budowlanych
   - **Umowy wymagane przez prawo zamówień publicznych** (PZP): Jeśli relacja wynika z zamówienia publicznego

2. **Wymogi branżowe** (Search_DU, Search_News): Sprawdź regulacje sektorowe:
   - Sektor finansowy: wymogi KNF, outsourcing bankowy (Prawo bankowe)
   - Sektor telekomunikacyjny: wymogi UKE
   - Sektor energetyczny: wymogi URE
   - Sektor ochrony zdrowia: umowy z NFZ, wymogi dotyczące dokumentacji medycznej

3. **Orzecznictwo** (Search_SN, Search_SP): Wyszukaj orzeczenia dotyczące konsekwencji braku wymaganych umów (np. odpowiedzialność administratora za brak umowy powierzenia danych).

```
## Pokrycie umowne

[✓] NDA / Umowa poufności -- [status]
[✓/✗] Umowa ramowa (MSA) -- [status lub „Nie znaleziono"]
[✓/✗] Umowa powierzenia danych (DPA) -- [status lub „Nie znaleziono"] [WYMAGANA PRAWNIE jeśli kontrahent przetwarza dane osobowe — art. 28 RODO]
[✓/✗] Zlecenie / Zamówienie (SOW) -- [status lub „Nie znaleziono"]
[✓/✗] SLA -- [status lub „Nie znaleziono"]
[✓/✗] Certyfikat ubezpieczenia -- [status lub „Nie znaleziono"]
[✓/✗] Umowa podwykonawcza -- [status lub „Nie znaleziono"] [WYMAGANA jeśli dotyczy robót budowlanych — art. 647¹ KC]
```

Oznacz wszelkie luki, które mogą być wymagane na podstawie typu relacji i przepisów prawa (np. brak umowy powierzenia danych, gdy kontrahent ma dostęp do danych osobowych).

### Krok 5: Wygenerowanie raportu

Przygotuj skonsolidowany raport:

```
## Status umów z kontrahentem: [Nazwa kontrahenta]

**Data przeglądu**: [dzisiejsza data]
**Sprawdzone źródła**: [lista przeszukanych systemów]
**Niedostępne źródła**: [lista niepodłączonych systemów, jeśli dotyczy]

## Przegląd relacji

**Kontrahent**: [pełna nazwa prawna]
**KRS/NIP**: [jeśli znany]
**Typ relacji**: [dostawca/partner/klient/itp.]
**Status CRM**: [jeśli dostępny]

## Podsumowanie umów

### [Typ umowy 1] -- [Status]
- **Obowiązuje od**: [data]
- **Wygasa**: [data] ([automatycznie się odnawia / nie odnawia się automatycznie])
- **Kluczowe warunki**: [podsumowanie istotnych warunków]
- **Lokalizacja**: [gdzie przechowywany jest podpisany egzemplarz]

### [Typ umowy 2] -- [Status]
[itd.]

## Analiza luk

### Wymogi prawne (IURA MCP)
[Umowy wymagane przepisami prawa polskiego na podstawie typu relacji — z powołaniem na konkretne artykuły]

### Brakujące umowy
[Co jest na miejscu vs. czego może brakować, ze wskazaniem czy brak jest naruszeniem przepisów]

## Nadchodzące działania

- [Zbliżające się daty wygaśnięcia lub terminy odnowienia]
- [Wymagane umowy jeszcze nie zawarte — ze wskazaniem podstawy prawnej]
- [Aneksy lub aktualizacje, które mogą być potrzebne]
- [Terminy wynikające z przepisów prawa (np. aktualizacja umowy powierzenia danych)]

## Uwagi

[Istotny kontekst z przeszukania e-mail/czat]
```

### Krok 6: Obsługa brakujących źródeł

Jeśli kluczowe systemy nie są podłączone przez MCP:

- **Brak CLM**: Zanotuj brak podłączenia CLM. Zasugeruj ręczne sprawdzenie CLM. Podaj wyniki z innych systemów.
- **Brak CRM**: Pomiń kontekst CRM. Zanotuj lukę.
- **Brak e-mail**: Zanotuj, że e-mail nie został przeszukany. Zasugeruj przeszukanie skrzynki pod kątem „[nazwa kontrahenta] umowa" lub „[nazwa kontrahenta] NDA".
- **Brak dokumentów**: Zanotuj, że repozytorium dokumentów nie zostało przeszukane.

Zawsze jasno wskaż, które źródła zostały sprawdzone, a które nie, aby użytkownik wiedział, jak kompletny jest raport.

## Uwagi

- Jeśli nie znaleziono żadnych umów w żadnym podłączonym systemie, wyraźnie to zaraportuj i zapytaj użytkownika, czy umowy są przechowywane w innym miejscu
- Dla grup kapitałowych (np. kontrahent z wieloma spółkami zależnymi), zapytaj czy użytkownik chce sprawdzić konkretny podmiot czy całą grupę
- Oznacz umowy wygasłe, które mogą nadal mieć obowiązujące postanowienia (poufność, indemnifikacja, itp.) — tzw. klauzule przeżywające (surviving clauses)
- Jeśli umowa zbliża się do wygaśnięcia (w ciągu 90 dni), wyraźnie to podkreśl
- Wyniki weryfikacji prawnej z IURA MCP podawaj z sygnaturami aktów prawnych i orzeczeń
- Dla kontrahentów przetwarzających dane osobowe, zawsze sprawdź istnienie aktualnej umowy powierzenia danych (art. 28 RODO)
- Zwróć uwagę na klauzule waloryzacyjne w długoterminowych umowach (art. 358¹ § 3 KC)
