# IURA Plugin (PL)

Plugin AI dla polskich zespołów prawnych, zaprojektowany dla [Cowork](https://claude.com/product/cowork) — działa również w Claude Code. Przegląd umów, triaż NDA, generowanie NDA, notatki prawne, masowy przegląd dokumentów — wszystko konfigurowalne pod playbook i tolerancję ryzyka Twojej organizacji.

Plugin działa samodzielnie — wszystkie skille i komendy są w pełni funkcjonalne bez dodatkowych usług. Każdy skill zawiera głęboką wiedzę dziedzinową o polskim prawie: playbooki negocjacyjne, klasyfikację ryzyka, standardy cytowania i profesjonalne formaty wyjściowe.

> **Zastrzeżenie:** Ten plugin wspiera workflow prawnicze, ale nie stanowi porady prawnej. Zawsze weryfikuj wnioski z wykwalifikowanymi prawnikami.

## Dlaczego IURA MCP?

Modele AI halucynują cytowania prawne — wymyślają sygnatury orzeczeń, cytują nieaktualne przepisy i fabrykują wyroki, które nie istnieją. W pracy prawniczej to jest niedopuszczalne.

[IURA MCP](https://iura.io) rozwiązuje ten problem, łącząc Claude z ponad 1,5 miliona zweryfikowanych polskich dokumentów prawnych w czasie rzeczywistym. Z podłączonym IURA MCP Twoja analiza zawiera:

- **Prawdziwe sygnatury orzeczeń** — zweryfikowane orzeczenia SN, sądów powszechnych, NSA/WSA, TK i KIO
- **Aktualne przepisy** — rzeczywisty tekst ustaw w brzmieniu obowiązującym dziś, nie z danych treningowych
- **Rozbieżne linie orzecznicze** — obie strony debaty prawnej z prawdziwymi sygnaturami
- **Interpretacje podatkowe** — oficjalne stanowiska organów skarbowych z pełnymi sygnaturami

Plugin jest świetny sam w sobie. Z IURA MCP jest kompletny.

## Instalacja

```
claude plugin install iura-pl@iura-plugins
```

## Komendy

### `/review-contract` — Przegląd umowy

Przegląd umowy względem playbooka negocjacyjnego. Flaguje odchylenia, generuje propozycje zmian, zapewnia analizę wpływu biznesowego.

### `/triage-nda` — Triaż NDA

Szybki triaż NDA: ZIELONY (standardowe zatwierdzenie), ŻÓŁTY (wymaga przeglądu), CZERWONY (istotne problemy).

### `/generate-nda` — Generowanie NDA

Generowanie kompletnego draftu NDA w formacie Word na podstawie danych stron i wybranych parametrów.

### `/legal-memo` — Notatka prawna

Sporządzenie profesjonalnej notatki prawnej (legal memo) z analizą IRAC, orzecznictwem, oceną ryzyka i rekomendacją. Wyjście w formacie Word, PDF, PowerPoint, draft e-maila lub bezpośrednio w rozmowie.

### `/tabular-review` — Przegląd tabelaryczny

Masowy przegląd wielu dokumentów prawnych z ekstrakcją ustrukturyzowanych danych do arkusza Excel.

## Skille

| Skill | Opis |
|-------|------|
| `iura` | Badania prawne z IURA MCP — strategia wyszukiwania, standardy cytowania, metodologia |
| `contract-review` | Analiza umów oparta o playbook, klasyfikacja odchyleń, generowanie propozycji zmian |
| `nda-triage` | Kryteria screeningu NDA, zasady klasyfikacji, rekomendacje procedowania |
| `nda-generation` | Generowanie draftów NDA w formacie Word z wyszukaniem danych podmiotów |
| `legal-memo` | Sporządzanie notatek prawnych — analiza IRAC, orzecznictwo, ocena ryzyka, rekomendacja |
| `tabular-review` | Masowy przegląd dokumentów do ustrukturyzowanych arkuszy Excel |

## Struktura plików

```
iura-pl/
├── .claude-plugin/plugin.json
├── .mcp.json
├── CONNECTORS.md
├── README.md
├── commands/
│   ├── review-contract.md
│   ├── triage-nda.md
│   ├── generate-nda.md
│   ├── legal-memo.md
│   └── tabular-review.md
└── skills/
    ├── iura/SKILL.md
    ├── contract-review/SKILL.md
    ├── nda-triage/SKILL.md
    ├── nda-generation/SKILL.md
    ├── legal-memo/SKILL.md
    └── tabular-review/SKILL.md
```

## Wsparcie

Jeśli podoba Ci się to co robimy, daj nam ⭐ na GitHubie — to pomaga innym odkryć ten projekt.

Myślisz o stworzeniu dedykowanych skilli pod Twoją kancelarię lub dział prawny? Chętnie pomożemy. Napisz do nas: [iura.io](https://iura.io)
