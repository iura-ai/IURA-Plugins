# Plugin Prawny (PL) — z integracją IURA MCP

Plugin AI dla polskich zespołów prawnych, zaprojektowany dla [Cowork](https://claude.com/product/cowork) — działa również w Claude Code. Automatyzuje przegląd umów, triaż NDA, compliance, briefinggi prawne i szablony odpowiedzi — wszystko konfigurowalne pod playbook i tolerancję ryzyka Twojej organizacji.

Wzbogacony o **IURA MCP** — dostęp do ponad 1,5 miliona polskich dokumentów prawnych: orzecznictwa sądów powszechnych, Sądu Najwyższego, sądów administracyjnych, Trybunału Konstytucyjnego, KIO, Dziennika Ustaw i interpretacji podatkowych.

> **Zastrzeżenie:** Ten plugin wspiera workflow prawnicze, ale nie stanowi porady prawnej. Zawsze weryfikuj wnioski z wykwalifikowanymi prawnikami. Analiza generowana przez AI powinna być zweryfikowana przez radcę prawnego lub adwokata przed podjęciem decyzji prawnych.

## Docelowi użytkownicy

- **Prawnik korporacyjny** — Negocjowanie umów, zarządzanie kontrahentami, wsparcie transakcji
- **Prawnik produktowy** — Przegląd produktów, regulaminy, polityki prywatności, kwestie IP
- **Compliance / Ochrona danych** — RODO, przegląd DPA, wnioski osób, monitoring regulacyjny
- **Wsparcie sporów** — Zabezpieczenie dowodów, przegląd dokumentów, briefinggi spraw
- **Due diligence** — Masowy przegląd dokumentów, ekstrakcja kluczowych postanowień

## Instalacja

```
claude plugins add iura-ai/iura-plugins/legal-pl
```

## Komendy

### `/review-contract` — Przegląd umowy

Przegląd umowy względem playbooka negocjacyjnego z analizą IURA MCP. Flaguje odchylenia, generuje redline'y, zapewnia analizę wpływu biznesowego wzbogaconą o orzecznictwo.

### `/triage-nda` — Triaż NDA

Szybki triaż NDA: ZIELONY (standardowe zatwierdzenie), ŻÓŁTY (wymaga przeglądu), CZERWONY (istotne problemy). Z odniesieniem do tajemnicy przedsiębiorstwa (art. 11 UZNK).

### `/vendor-check` — Sprawdzenie kontrahenta

Status istniejących umów z kontrahentem w podłączonych systemach. Weryfikacja wymagań prawnych poprzez IURA MCP.

### `/brief` — Briefing prawny

```
/brief daily              # Poranny przegląd
/brief topic [zapytanie]  # Brief tematyczny z analizą IURA
/brief incident [temat]   # Szybki brief incydentalny
```

### `/respond` — Odpowiedź z szablonu

Generowanie odpowiedzi z szablonów z weryfikacją aktualnych przepisów przez IURA MCP.

## Skille

| Skill | Opis |
|-------|------|
| `contract-review` | Analiza umów oparta o playbook z orzecznictwem SN i KC |
| `nda-triage` | Screening NDA z odniesieniem do UZNK i orzecznictwa |
| `compliance` | RODO, UODO, przegląd DPA, wnioski osób |
| `canned-responses` | Zarządzanie szablonami z weryfikacją przepisów |
| `legal-risk-assessment` | Framework oceny ryzyka z orzecznictwem |
| `meeting-briefing` | Przygotowanie spotkań z aktualnym stanem prawnym |
| `tabular-review` | Masowy przegląd dokumentów do Excela z analizą IURA |

## Integracja IURA MCP

Każdy skill automatycznie korzysta z IURA MCP aby:

1. **Weryfikować przepisy** — Search_DU sprawdza aktualny stan prawny przed analizą
2. **Wyszukiwać orzecznictwo** — Search_SN/Search_SP/Search_CBOSA znajduje precedensy
3. **Cytować źródła** — każda analiza zawiera sygnatury orzeczeń i odniesienia do przepisów
4. **Monitorować zmiany** — Search_News śledzi bieżące zmiany w prawie

## Struktura plików

```
legal-pl/
├── .claude-plugin/plugin.json
├── .mcp.json
├── CONNECTORS.md
├── README.md
├── commands/
│   ├── review-contract.md
│   ├── triage-nda.md
│   ├── vendor-check.md
│   ├── brief.md
│   └── respond.md
└── skills/
    ├── contract-review/SKILL.md
    ├── nda-triage/SKILL.md
    ├── compliance/SKILL.md
    ├── canned-responses/SKILL.md
    ├── legal-risk-assessment/SKILL.md
    ├── meeting-briefing/SKILL.md
    └── tabular-review/SKILL.md
```
