---
description: Review a contract against your organization's negotiation playbook — flag deviations, generate redlines, provide business impact analysis (Polish law context with IURA MCP)
argument-hint: "<plik umowy lub tekst>"
---

# /review-contract -- Przegląd umowy według playbooka

> Jeśli widzisz nieznane symbole zastępcze lub chcesz sprawdzić podłączone narzędzia, zobacz [CONNECTORS.md](../CONNECTORS.md).

Przegląd umowy na podstawie playbooka negocjacyjnego organizacji. Analiza każdej klauzuli, oznaczanie odchyleń, sugerowanie zmian (redline) oraz ocena wpływu biznesowego — z uwzględnieniem polskiego prawa cywilnego i handlowego dzięki integracji z IURA MCP.

**Ważne**: To polecenie wspiera pracę prawnika, ale nie stanowi porady prawnej. Wyniki analizy powinny być zweryfikowane przez wykwalifikowanego prawnika przed podjęciem decyzji.

## Wywołanie

```
/review-contract
```

## Przebieg pracy

### Krok 1: Przyjęcie umowy

Przyjmij umowę w dowolnym formacie:
- **Plik**: PDF, DOCX lub inny format dokumentu
- **URL**: Link do umowy w systemie CLM, chmurze (np. OneDrive, SharePoint, Google Drive) lub innym repozytorium dokumentów
- **Wklejony tekst**: Treść umowy wklejona bezpośrednio do rozmowy

Jeśli umowa nie została przekazana, poproś użytkownika o jej dostarczenie.

### Krok 2: Zebranie kontekstu

Zapytaj użytkownika o kontekst przed rozpoczęciem przeglądu:

1. **Po której stronie jesteś?** (dostawca/usługodawca, zamawiający/kupujący, licencjodawca, licencjobiorca, partner — lub inna rola)
2. **Termin**: Kiedy umowa powinna być sfinalizowana? (Wpływa na priorytetyzację zagadnień)
3. **Obszary fokusowe**: Czy są konkretne obawy? (np. „ochrona danych jest kluczowa", „potrzebujemy elastyczności w zakresie okresu obowiązywania", „kwestia własności IP jest najważniejsza")
4. **Kontekst transakcji**: Istotne informacje biznesowe? (np. wartość transakcji, strategiczne znaczenie, dotychczasowa relacja z kontrahentem)

Jeśli użytkownik poda częściowy kontekst, kontynuuj z tym, co masz, i zanotuj przyjęte założenia.

### Krok 3: Załadowanie playbooka

Poszukaj playbooka negocjacyjnego organizacji w ustawieniach lokalnych (np. `legal.local.md` lub podobnych plikach konfiguracyjnych).

Playbook powinien definiować:
- **Standardowe pozycje**: Preferowane warunki organizacji dla każdego istotnego typu klauzuli
- **Dopuszczalne zakresy**: Warunki akceptowalne bez eskalacji
- **Kryteria eskalacji**: Warunki wymagające przeglądu przez starszego prawnika lub kancelarię zewnętrzną

**Jeśli playbook nie jest skonfigurowany:**
- Poinformuj użytkownika, że playbook nie został znaleziony
- Zaproponuj dwie opcje:
  1. Pomoc w stworzeniu playbooka (przeprowadzenie użytkownika przez definiowanie pozycji dla kluczowych klauzul)
  2. Przegląd na podstawie ogólnych standardów rynkowych i polskich przepisów prawa cywilnego
- Jeśli kontynuujesz bez playbooka, wyraźnie zaznacz, że przegląd bazuje na ogólnych standardach, a nie na konkretnych pozycjach organizacji

### Krok 4: Analiza prawna z IURA MCP

Przed przystąpieniem do szczegółowej analizy klauzul, wykorzystaj IURA MCP do zebrania kontekstu prawnego:

1. **Przepisy prawa** (Search_DU): Wyszukaj obowiązujące przepisy KC, KSH lub innych ustaw istotnych dla typu umowy. Na przykład:
   - Dla umów o świadczenie usług — przepisy KC o umowie zlecenia lub o dzieło
   - Dla umów sprzedaży — przepisy KC o rękojmi, gwarancji i sprzedaży
   - Dla umów licencyjnych — przepisy ustawy o prawie autorskim
   - Dla umów z kontrahentami zagranicznymi — przepisy ustawy Prawo prywatne międzynarodowe
   - Użyj parametru `in_force_as_of` z dzisiejszą datą, aby uzyskać aktualny stan prawny

2. **Orzecznictwo** (Search_SN, Search_SP): Dla klauzul budzących wątpliwości, wyszukaj precedensy dotyczące:
   - Klauzul abuzywnych (art. 385¹–385³ KC)
   - Ograniczenia odpowiedzialności i kar umownych
   - Klauzul poufności i zakazu konkurencji
   - Rozwiązania umowy i odstąpienia od umowy

3. **Interpretacje** (Search_IP): Jeśli umowa ma aspekty podatkowe (np. transfer pricing, VAT), wyszukaj interpretacje podatkowe.

Włącz wyniki wyszukiwania do analizy poszczególnych klauzul — powołuj się na konkretne artykuły ustaw i sygnatury orzeczeń.

### Krok 5: Analiza klauzula po klauzuli

Przeanalizuj umowę systematycznie, obejmując co najmniej:

| Kategoria klauzuli | Kluczowe punkty analizy |
|---------------------|-------------------------|
| **Ograniczenie odpowiedzialności** | Limit kwotowy, wyłączenia, wzajemne vs. jednostronne, szkody pośrednie, zgodność z art. 473 KC |
| **Kary umowne** | Wysokość, podstawa naliczenia, miarkowanie (art. 484 § 2 KC), kumulacja z odszkodowaniem |
| **Odszkodowanie i indemnifikacja** | Zakres, wzajemność, limit, naruszenie IP, naruszenie danych |
| **Własność intelektualna** | IP zastane, IP wytworzone, utwór pracowniczy, licencje, przeniesienie praw, pola eksploatacji |
| **Ochrona danych osobowych** | Umowa powierzenia (art. 28 RODO), warunki przetwarzania, podprzetwarzcy, notyfikacja naruszeń, transfer międzynarodowy |
| **Poufność** | Zakres, okres obowiązywania, wyłączenia, zwrot/zniszczenie informacji |
| **Oświadczenia i gwarancje** | Zakres, zastrzeżenia, okres obowiązywania po wygaśnięciu umowy |
| **Okres obowiązywania i rozwiązanie** | Czas trwania, automatyczne odnowienie, wypowiedzenie bez przyczyny, wypowiedzenie z ważnych powodów, okres przejściowy |
| **Prawo właściwe i rozstrzyganie sporów** | Jurysdykcja, właściwość sądu, arbitraż vs. sąd powszechny, mediacja |
| **Ubezpieczenie** | Wymagane ubezpieczenia, sumy minimalne, potwierdzenie ochrony |
| **Cesja** | Zgoda na przeniesienie praw, zmiana kontroli, wyjątki |
| **Siła wyższa** | Zakres, powiadomienie, prawo do rozwiązania, zgodność z art. 471 i 475 KC |
| **Warunki płatności** | Terminy płatności (ustawa o przeciwdziałaniu nadmiernym opóźnieniom), odsetki, podatki, waloryzacja |

Dla każdej klauzuli oceń zgodność z playbookiem (lub ogólnymi standardami) i obowiązującym prawem polskim. Zanotuj, czy klauzula jest obecna, brakująca, niestandardowa lub sprzeczna z przepisami bezwzględnie obowiązującymi.

### Krok 6: Oznaczenie odchyleń

Sklasyfikuj każde odchylenie od playbooka w trójstopniowym systemie:

#### ZIELONY -- Akceptowalne
- Zgodne ze standardową pozycją organizacji lub korzystniejsze
- Drobne różnice, które są komercyjnie uzasadnione
- Brak konieczności działania; notatka informacyjna

#### ŻÓŁTY -- Do negocjacji
- Poza standardową pozycją, ale w zakresie negocjowalnym
- Powszechne na rynku, ale nie odpowiadające preferencjom organizacji
- Wymaga uwagi, ale nie eskalacji
- **Zawrzyj**: Konkretną propozycję zmiany brzmienia klauzuli
- **Zawrzyj**: Pozycję zapasową w razie odmowy kontrahenta
- **Zawrzyj**: Wpływ biznesowy akceptacji vs. negocjacji
- **Zawrzyj**: Powołanie na odpowiedni przepis KC/KSH lub orzeczenie (jeśli znalezione przez IURA)

#### CZERWONY -- Eskalacja
- Poza dopuszczalnym zakresem lub spełnia kryterium eskalacji
- Nietypowe lub agresywne warunki stanowiące istotne ryzyko
- Klauzula potencjalnie sprzeczna z przepisami bezwzględnie obowiązującymi (np. klauzule abuzywne)
- Wymaga przeglądu przez starszego prawnika, kancelarię zewnętrzną lub akceptacji decydenta biznesowego
- **Zawrzyj**: Dlaczego to jest CZERWONA flaga (konkretne ryzyko)
- **Zawrzyj**: Jak wygląda standardowa pozycja rynkowa
- **Zawrzyj**: Wpływ biznesowy i potencjalne narażenie
- **Zawrzyj**: Rekomendowaną ścieżkę eskalacji
- **Zawrzyj**: Podstawę prawną (artykuł ustawy, orzeczenie SN/SP znalezione przez IURA)

### Krok 7: Generowanie propozycji zmian (redline)

Dla każdego odchylenia ŻÓŁTEGO i CZERWONEGO podaj:
- **Obecne brzmienie**: Cytuj odpowiedni fragment umowy
- **Proponowana zmiana**: Konkretne alternatywne brzmienie
- **Uzasadnienie**: Krótkie wyjaśnienie odpowiednie do przekazania kontrahentowi, z powołaniem na przepisy prawa polskiego
- **Priorytet**: Czy to konieczność (must-have) czy bonus (nice-to-have) w negocjacjach

### Krok 8: Podsumowanie wpływu biznesowego

Przygotuj podsumowanie obejmujące:
- **Ogólna ocena ryzyka**: Syntetyczny obraz profilu ryzyka umowy
- **Top 3 zagadnienia**: Najważniejsze kwestie do rozwiązania
- **Strategia negocjacyjna**: Rekomendowane podejście (z czym iść na początek, co ewentualnie ustąpić)
- **Czynniki czasowe**: Czy istnieją elementy pilności wpływające na podejście negocjacyjne
- **Zgodność z prawem polskim**: Podsumowanie kluczowych ryzyk wynikających z przepisów bezwzględnie obowiązujących

### Krok 9: Kierowanie w CLM (jeśli podłączony)

Jeśli system CLM jest podłączony przez MCP:
- Zaproponuj odpowiednią ścieżkę zatwierdzania na podstawie typu umowy i poziomu ryzyka
- Zasugeruj prawidłowy routing (np. standardowe zatwierdzenie, starszy prawnik, kancelaria zewnętrzna)
- Zanotuj wymagane zgody na podstawie wartości umowy lub flag ryzyka

Jeśli CLM nie jest podłączony, pomiń ten krok.

## Format wyjściowy

Ustrukturyzuj wynik następująco:

```
## Podsumowanie przeglądu umowy

**Dokument**: [nazwa/identyfikator umowy]
**Strony**: [nazwy stron i ich role]
**Twoja strona**: [dostawca/zamawiający/itp.]
**Termin**: [jeśli podany]
**Podstawa przeglądu**: [Playbook / Ogólne standardy + prawo polskie]

## Kluczowe ustalenia

[Top 3-5 zagadnień z flagami ważności]

## Kontekst prawny (IURA MCP)

[Podsumowanie kluczowych przepisów i orzeczeń znalezionych przez IURA, istotnych dla tej umowy]

## Analiza klauzula po klauzuli

### [Kategoria klauzuli] -- [ZIELONY/ŻÓŁTY/CZERWONY]
**Umowa stanowi**: [podsumowanie postanowienia]
**Pozycja playbooka**: [standard organizacji]
**Przepis prawa**: [odpowiedni artykuł KC/KSH/innej ustawy]
**Odchylenie**: [opis rozbieżności]
**Wpływ biznesowy**: [co to oznacza w praktyce]
**Propozycja zmiany**: [konkretne brzmienie, jeśli ŻÓŁTY lub CZERWONY]

[Powtórz dla każdej istotnej klauzuli]

## Strategia negocjacyjna

[Rekomendowane podejście, priorytety, kandydaci na ustępstwa]

## Kolejne kroki

[Konkretne działania do podjęcia]
```

## Uwagi

- Umowy w języku innym niż polski analizuj w języku oryginału, ale raport przygotuj po polsku
- Dla bardzo długich umów (50+ stron) zaproponuj skupienie się na najistotniejszych częściach, a następnie pełny przegląd
- Zawsze przypominaj, że analiza powinna być zweryfikowana przez wykwalifikowanego prawnika przed podjęciem wiążących decyzji
- Powołania na przepisy prawa (znalezione przez IURA MCP) podawaj z sygnaturami aktów prawnych i orzeczeń
- Przy klauzulach dotyczących danych osobowych, weryfikuj zgodność z RODO i polską ustawą o ochronie danych osobowych
