---
name: generate-remote-hearing-application
description: A skill for generating procedurally correct remote hearing applications (wniosek o przeprowadzenie rozprawy w trybie zdalnym), following polish regulations.
---

# Generate Remote Hearing Application

## Instructions
Clear, step-by-step guidance for the agent.

# Wniosek o przeprowadzenie rozprawy w trybie zdalnym

Skill służy do generowania wniosków o przeprowadzenie rozprawy (posiedzenia jawnego) w trybie zdalnym. Obsługuje postępowanie cywilne, karne, sądowoadministracyjne oraz postępowanie odwoławcze przed KIO. Treść generowana stanowi poprawną formę pisma procesowego zgodną z przepisami właściwej ustawy procesowej.

## Zasada nadrzędna

Wniosek o rozprawę zdalną to pismo procesowe, nie opinia prawna ani analiza doktrynalna. Ma być zwięzłe, konkretne i zawierać wszystkie dane wymagane przepisami. Styl: urzędowy, rzeczowy, bez rozbudowanych uzasadnień — kilka zdań wystarczy.

ZASADA FORMATOWANIA: Wniosek generuj jako zwykły tekst w odpowiedzi czatowej. NIE używaj formatowania markdown — żadnych nagłówków z #, żadnych list z -, żadnego pogrubienia z ** ani *, żadnych bloków kodu. Tekst wniosku ma wyglądać jak normalny dokument procesowy zapisany zwykłym tekstem. Zachowuj prawidłowe formy zapisu prawnego: sygnatury akt, daty w formacie dd.mm.rrrr r., nazwy sądów, artykuły ustaw.

---

## Identyfikacja rodzaju postępowania

Na samym początku ustal, jakiego postępowania dotyczy wniosek. Od tego zależy podstawa prawna, forma i treść pisma. Jeśli użytkownik nie podał tej informacji wprost, ustal ją na podstawie kontekstu (nazwa sądu, sygnatura akt, opis sprawy) lub dopytaj.

POSTĘPOWANIE CYWILNE — sprawy cywilne, gospodarcze, pracownicze, rodzinne przed sądami powszechnymi. Sygnatury typu: C, GC, RC, P, Ns, GNs itp.

POSTĘPOWANIE KARNE — sprawy karne i wykroczeniowe przed sądami powszechnymi. Sygnatury typu: K, Ka, W itp.

POSTĘPOWANIE SĄDOWOADMINISTRACYJNE — sprawy przed wojewódzkimi sądami administracyjnymi (WSA) i Naczelnym Sądem Administracyjnym (NSA). Sygnatury typu: SA/Wa, SA/Kr, I OSK, II GSK itp.

POSTĘPOWANIE PRZED KIO — sprawy odwoławcze w zamówieniach publicznych. Sygnatury typu: KIO.

---

## Baza prawna — według rodzaju postępowania

### Postępowanie cywilne (k.p.c.)

Art. 151 § 2 k.p.c. — Przewodniczący może zarządzić przeprowadzenie posiedzenia jawnego przy użyciu urządzeń technicznych umożliwiających jego przeprowadzenie na odległość (posiedzenie zdalne), jeżeli nie stoi temu na przeszkodzie wzgląd na charakter czynności, które mają być dokonane na posiedzeniu, a przeprowadzenie posiedzenia zdalnego zagwarantuje pełną ochronę praw procesowych stron i prawidłowy tok postępowania.

Art. 151 § 3 k.p.c. — Przewodniczący może zarządzić przeprowadzenie posiedzenia zdalnego z urzędu lub na wniosek osoby, która ma uczestniczyć w posiedzeniu i wskazała adres poczty elektronicznej. Termin do złożenia wniosku wynosi 7 dni od dnia doręczenia zawiadomienia albo wezwania na posiedzenie.

Art. 151 § 5 k.p.c. — Zamiar zdalnego udziału w posiedzeniu już zarządzonym jako zdalne należy zgłosić najpóźniej na 3 dni robocze przed terminem posiedzenia, ze wskazaniem adresu poczty elektronicznej.

Art. 151 § 6 k.p.c. — Osoba, która nie zgłosiła skutecznie wniosku ani zamiaru zdalnego udziału, ma obowiązek stawić się w budynku sądu.

Art. 151 § 8 k.p.c. — Osoba biorąca udział w posiedzeniu zdalnym jest zobowiązana poinformować sąd o miejscu pobytu oraz dołożyć starań, aby warunki licowały z powagą sądu.

Art. 125¹ § 2 pkt 5 k.p.c. — Adwokat, radca prawny, rzecznik patentowy, Prokuratoria Generalna RP lub prokurator wnosi wniosek o przeprowadzenie posiedzenia zdalnego za pośrednictwem portalu informacyjnego.

### Postępowanie karne (k.p.k.)

Art. 374 § 3 k.p.k. — Przewodniczący, na wniosek prokuratora, wyraża zgodę na jego udział w rozprawie przy użyciu urządzeń technicznych umożliwiających udział w rozprawie na odległość z jednoczesnym bezpośrednim przekazem obrazu i dźwięku, jeżeli nie stoją temu na przeszkodzie względy techniczne.

Art. 374 § 4 k.p.k. — Przewodniczący może zwolnić z obowiązku stawiennictwa na rozprawie oskarżonego, oskarżyciela posiłkowego albo oskarżyciela prywatnego, którzy są pozbawieni wolności, jeżeli zostanie zapewniony udział tych stron w rozprawie na odległość.

Art. 349 § 5 k.p.k. — Na posiedzeniu wstępnym strony mogą składać wnioski o zezwolenie na udział w rozprawie na odległość z wykorzystaniem urządzeń umożliwiających jednoczesny i bezpośredni przekaz obrazu i dźwięku.

Uwaga: W postępowaniu karnym przepisy nie przewidują ogólnego uprawnienia strony (innej niż prokurator) do złożenia wniosku o rozprawę zdalną w taki sam sposób jak w k.p.c. Wniosek obrońcy lub oskarżonego o udział zdalny najczęściej składa się na posiedzeniu wstępnym (art. 349 § 5 k.p.k.) lub jako wniosek o charakterze porządkowym kierowany do przewodniczącego. Mimo braku wyraźnej podstawy ustawowej, praktyka sądowa dopuszcza składanie takich wniosków — sąd rozstrzyga o nich w ramach uprawnień do organizacji rozprawy.

### Postępowanie sądowoadministracyjne (p.p.s.a.)

Art. 94 § 2 p.p.s.a. — Przewodniczący może zarządzić przeprowadzenie posiedzenia jawnego przy użyciu urządzeń technicznych umożliwiających jego przeprowadzenie na odległość. Uczestnicy mogą brać udział w posiedzeniu przebywając w budynku innego sądu.

Uwaga: W postępowaniu sądowoadministracyjnym udział zdalny jest ograniczony — co do zasady uczestnik przebywa w budynku innego sądu, a nie w dowolnym miejscu. Wniosek składa się do przewodniczącego jako pismo procesowe. Przepisy p.p.s.a. nie przewidują tak szczegółowego trybu jak k.p.c.

### Postępowanie przed KIO (PZP)

Art. 508a ust. 1 PZP — Jawne rozprawy lub posiedzenia jawne mogą być przeprowadzane przy użyciu urządzeń technicznych umożliwiających ich przeprowadzenie na odległość (zdalna rozprawa lub zdalne posiedzenie), jeżeli nie stoi temu na przeszkodzie charakter czynności i zostaną zagwarantowane pełna ochrona praw procesowych stron oraz prawidłowy tok postępowania.

---

## Zbieranie danych — pytania do użytkownika

Przed wygenerowaniem wniosku musisz ustalić poniższe informacje. Jeśli użytkownik nie podał ich w swoim zapytaniu, zadaj mu pytania dopytujące — ale tylko te, których brakuje.

DANE OBLIGATORYJNE:

1. Rodzaj postępowania — cywilne, karne, sądowoadministracyjne, KIO (jeśli nie wynika z kontekstu)

2. Kto składa wniosek?
   a) Pełnomocnik profesjonalny w postępowaniu cywilnym (adwokat/radca prawny) — potrzebne: imię i nazwisko pełnomocnika, tytuł zawodowy, dane mocodawcy, status procesowy mocodawcy, adres e-mail pełnomocnika, numer telefonu pełnomocnika
   b) Obrońca w postępowaniu karnym (adwokat/radca prawny) — potrzebne: imię i nazwisko obrońcy, tytuł zawodowy, dane oskarżonego/obwinionego, adres e-mail obrońcy
   c) Prokurator w postępowaniu karnym — potrzebne: imię i nazwisko, jednostka, adres e-mail
   d) Strona we własnym imieniu — potrzebne: imię i nazwisko, status procesowy (powód/pozwany/oskarżony/pokrzywdzony/skarżący/uczestnik/wykonawca/zamawiający), adres e-mail

3. Oznaczenie sądu lub organu — nazwa sądu/KIO i wydział

4. Sygnatura akt

5. Opis sprawy — zwięzły (np. „roszczenia z umowy kredytu", „o zapłatę", „o czyn z art. 286 § 1 k.k.", „odwołanie od decyzji Dyrektora KIS", „odwołanie w sprawie zamówienia publicznego")

6. Data rozprawy — jeśli znana

7. Czy wnioskodawca dysponuje urządzeniami technicznymi? (kamera, mikrofon, głośnik)
   a) Tak — standardowy wniosek
   b) Nie — wniosek z prośbą o zapewnienie udziału zdalnego w budynku sądu

DANE OPCJONALNE (nie dopytuj, ale uwzględnij jeśli podane):

Strona przeciwna, PESEL/KRS/NIP stron, adres dla doręczeń, dodatkowe uzasadnienie (odległość, koszty, stan zdrowia), czy wniosek dotyczy konkretnego terminu czy ogólnie całego postępowania.

---

## Warianty wniosku

WARIANT A — Pełnomocnik/obrońca składa wniosek w imieniu klienta
Formuła otwarcia w postępowaniu cywilnym: „Działając w imieniu i na rzecz [status procesowy] – [imię i nazwisko / nazwa], na podstawie udzielonego mi pełnomocnictwa, znajdującego się w aktach sprawy, wnoszę o..."
Formuła otwarcia w postępowaniu karnym: „Działając jako obrońca oskarżonego [imię i nazwisko], na podstawie udzielonego mi upoważnienia do obrony, znajdującego się w aktach sprawy, wnoszę o..."
Formuła otwarcia w postępowaniu sądowoadministracyjnym: „Działając w imieniu skarżącego – [imię i nazwisko / nazwa], na podstawie udzielonego mi pełnomocnictwa, znajdującego się w aktach sprawy, wnoszę o..."
Formuła otwarcia przed KIO: „Działając w imieniu [odwołującego/zamawiającego/przystępującego] – [nazwa], na podstawie udzielonego mi pełnomocnictwa, wnoszę o..."

WARIANT B — Strona we własnym imieniu
Formuła otwarcia: „Działając we własnym imieniu jako [status procesowy] w sprawie o sygn. akt [sygnatura], wnoszę o..."

WARIANT C — Prokurator (postępowanie karne)
Formuła otwarcia: „Na podstawie art. 374 § 3 k.p.k. wnoszę o wyrażenie zgody na mój udział w rozprawie wyznaczonej na dzień [data] w sprawie o sygn. akt [sygnatura] przy użyciu urządzeń technicznych umożliwiających udział na odległość z jednoczesnym bezpośrednim przekazem obrazu i dźwięku."

WARIANT D — Brak urządzeń technicznych (łączy się z A lub B)
Do treści wniosku dodaj: „Oświadczam, że nie dysponuję urządzeniami technicznymi pozwalającymi na udział w rozprawie w formie wideokonferencji. Proszę o zapewnienie mi możliwości udziału w posiedzeniu zdalnym w budynku sądu."

---

## Struktura wniosku — schemat

Część I: Nagłówek

Nagłówek zapisz jako zwykły tekst z zachowaniem układu pisma procesowego. Układ:

Lewa strona u góry: miejscowość i data; dane wnioskodawcy (imię, nazwisko, status procesowy); jeśli pełnomocnik/obrońca: dane mocodawcy/oskarżonego, a pod nimi „reprezentowany przez: [tytuł] [imię nazwisko]", e-mail, telefon, adres dla doręczeń.

Prawa strona (adresat): nazwa sądu/KIO; wydział (jeśli dotyczy); sygnatura akt.

Jeśli znane — dane strony przeciwnej.

Część II: Tytuł

WNIOSEK O PRZEPROWADZENIE ROZPRAWY W TRYBIE ZDALNYM

Zapisz wersalikami, wyśrodkowany. W postępowaniu karnym można też użyć: WNIOSEK O ZEZWOLENIE NA UDZIAŁ W ROZPRAWIE NA ODLEGŁOŚĆ.

Część III: Treść wniosku

Akapit 1 — Formuła otwarcia (wariant A, B, C lub D) + petitum.

Petitum według rodzaju postępowania:

Postępowanie cywilne: „...wnoszę o przeprowadzenie rozprawy [wyznaczonej na dzień dd.mm.rrrr r.] w sprawie [opis] o sygn. akt [sygnatura] w trybie zdalnym na podstawie art. 151 § 3 k.p.c."

Postępowanie karne (obrońca/oskarżony): „...wnoszę o zezwolenie na udział [oskarżonego / obrońcy / pełnomocnika oskarżyciela posiłkowego] w rozprawie wyznaczonej na dzień [data] w sprawie o sygn. akt [sygnatura] przy użyciu urządzeń technicznych umożliwiających udział na odległość z jednoczesnym bezpośrednim przekazem obrazu i dźwięku."

Postępowanie karne (prokurator): „...wnoszę o wyrażenie zgody na mój udział w rozprawie wyznaczonej na dzień [data] w sprawie o sygn. akt [sygnatura] przy użyciu urządzeń technicznych umożliwiających udział w rozprawie na odległość z jednoczesnym bezpośrednim przekazem obrazu i dźwięku, na podstawie art. 374 § 3 k.p.k."

Postępowanie sądowoadministracyjne: „...wnoszę o zarządzenie przeprowadzenia rozprawy wyznaczonej na dzień [data] w sprawie o sygn. akt [sygnatura] przy użyciu urządzeń technicznych umożliwiających jej przeprowadzenie na odległość, na podstawie art. 94 § 2 p.p.s.a."

Postępowanie przed KIO: „...wnoszę o przeprowadzenie rozprawy w sprawie o sygn. akt [sygnatura] w trybie zdalnym, na podstawie art. 508a ust. 1 ustawy z dnia 11 września 2019 r. – Prawo zamówień publicznych."

Akapit 2 — Uzasadnienie (zwięzłe, 2-3 zdania).

Formuła standardowa (cywilne): „Wskazuję, iż przeprowadzenie rozprawy w trybie zdalnym zagwarantuje pełną ochronę praw procesowych stron i prawidłowy tok postępowania. Wniosek niniejszy jest uzasadniony zasadą szybkości postępowania, a także obniżeniem jego kosztów."

Formuła standardowa (karne): „Wniosek jest uzasadniony potrzebą sprawnego przeprowadzenia postępowania. Udział na odległość nie stoi na przeszkodzie prawidłowemu tokowi rozprawy ani realizacji prawa do obrony."

Formuła standardowa (sądowoadministracyjne): „Przeprowadzenie posiedzenia na odległość przyczyni się do sprawnego rozpoznania sprawy i zaoszczędzenia kosztów, przy jednoczesnym zagwarantowaniu pełnej ochrony praw procesowych stron."

Formuła standardowa (KIO): „Przeprowadzenie rozprawy zdalnej zagwarantuje pełną ochronę praw procesowych stron i uczestników postępowania odwoławczego oraz prawidłowy tok postępowania, a jednocześnie przyczyni się do sprawnego rozpoznania sprawy."

Formuła z dodatkowym uzasadnieniem (uniwersalna, jeśli użytkownik podał powód): „Ponadto [uzasadnienie szczegółowe — np. odległość, stan zdrowia, koszty dojazdu, inne obiektywne okoliczności]."

Akapit 3 — Dane kontaktowe: „Wskazuję dane kontaktowe niezbędne do przeprowadzenia rozprawy zdalnej:" po czym podaj adres e-mail i numer telefonu (jeśli podany). W postępowaniu cywilnym, jeśli pełnomocnik: „W przypadku pozytywnego rozpatrzenia wniosku, proszę o przesłanie dostępów do rozprawy zdalnej zarówno Stronie [Powodowej/Pozwanej], jak i jej pełnomocnikowi, na adresy e-mail podane w komparycji."

Akapit 4 (opcjonalny, wariant D) — Oświadczenie o braku urządzeń technicznych.

Część IV: Podpis

Imię i nazwisko (pełnomocnika, obrońcy, prokuratora lub strony).

Część V: Załączniki i uwagi o sposobie wniesienia

Postępowanie cywilne — pełnomocnik profesjonalny: „Niniejsze pismo wniesione za pośrednictwem portalu informacyjnego zgodnie z art. 125¹ § 2 pkt 5 k.p.c." (odpis pisma nie jest wymagany).
Postępowanie cywilne — strona osobiście: „Załącznik: - odpis pisma".
Postępowanie karne: „Załącznik: - odpis pisma".
Postępowanie sądowoadministracyjne: „Załącznik: - odpis pisma dla organu".
Postępowanie przed KIO: „Załącznik: - dowód przekazania kopii pisma stronom i uczestnikom postępowania odwoławczego".

---

## Checklist walidacyjny

Przed uznaniem wniosku za gotowy zweryfikuj:

Wymogi formalne: oznaczenie sądu/organu i wydziału; sygnatura akt; dane wnioskodawcy (imię, nazwisko, status); adres e-mail; prawidłowa podstawa prawna dla danego rodzaju postępowania; data i podpis; właściwe załączniki.

Poprawność wariantu: jeśli pełnomocnik w sprawach cywilnych — formuła „Działając w imieniu i na rzecz..." + powołanie na pełnomocnictwo; jeśli obrońca w sprawach karnych — formuła „Działając jako obrońca oskarżonego..." + powołanie na upoważnienie do obrony; jeśli prokurator — formuła z art. 374 § 3 k.p.k.; jeśli strona osobiście — formuła „Działając we własnym imieniu..."; jeśli brak urządzeń — oświadczenie + prośba o zapewnienie udziału w budynku sądu.

Prawidłowość podstawy prawnej: cywilne — art. 151 § 3 k.p.c.; karne (prokurator) — art. 374 § 3 k.p.k.; karne (inne strony) — art. 349 § 5 k.p.k. lub wniosek porządkowy bez wskazywania konkretnej podstawy (dopuszczalne); sądowoadministracyjne — art. 94 § 2 p.p.s.a.; KIO — art. 508a ust. 1 PZP.

Styl i format: wniosek jest zwykłym tekstem, BEZ formatowania markdown; tytuł wersalikami; uzasadnienie zwięzłe (2-3 zdania); brak odwołań do orzecznictwa i interpretacji podatkowych; brak akademickich dygresji; objętość: maksymalnie 1 strona.