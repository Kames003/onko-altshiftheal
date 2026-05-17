# ALT+SHIFT+HEAL — Onko

Digitálny sprievodca príchodom pacienta s karcinómom prostaty.
Projekt pre **Zdravotnictví 4.0 Challenge** · FEI VŠB–TUO · 2026.

**Klinický garant:** MUDr. Zuzana Čermáková, Ph.D. · FN Ostrava, Onkologická klinika  
**Tím:** Mucha · Martynková · Tomica · Tobola

---

## Štruktúra repozitára

```
.
├── docs/
│   ├── brief/               ← Pôvodné zadanie (35_Čermáková.pptx)
│   ├── analysis/            ← Systémová analýza, details per slide
│   └── presentations/       ← HTML prezentácie pre stretnutia
│
├── app/
│   ├── prototype/           ← Aktuálny funkčný prototyp (prototyp.html)
│   └── src/                 ← Produkčný kód (budúca fáza)
│
└── research/                ← Zdroje, evidence, guidelines (budúca fáza)
```

---

## Rýchly štart

**Pozrieť prototyp:**
```
open app/prototype/prototyp.html
```

**Pozrieť prezentáciu:**
```
open docs/presentations/onko-podklady-schuzka1.html
```

---

## Produkt v skratke

Pacient dostane QR kód priamo v odporúčacom liste od urológa. Otvorí sprievodcu ešte doma — žiadna registrácia, žiadna inštalácia. Obsah sa personalizuje podľa typu liečby (RT / HT / chirurgia / aktívne sledovanie / RT+HT).

**Čo sprievodca obsahuje:**
- Kroky liečby krok po kroku
- Nežiaduce účinky a výživa podľa liečby
- Timeline termínov
- Záložka na ukladanie otázok pre lekára (+ tlač)
- Kontakty, navigácia do nemocnice, čo je normálne
- Pohľad pre rodinu
- Osobný deník

**Čo sprievodca nie je:**
- Nie je diagnostický nástroj
- Nie je ePRO monitoring
- Nie je integrácia do NIS
- Nie je MDR-klasifikovaný softvér

---

## Architektúra (3 vrstvy)

| Vrstva | Stav | Popis |
|--------|------|-------|
| 1 · Pacientská app | Hotovo | Single-page PWA, localStorage, offline |
| 2 · Content CMS + validácia | Fáza 2 | Editácia obsahu bez kódu, schvaľovací flow |
| 3 · Sub-agentná správa | Fáza 3 | Monitoring guidelines → draft → deploy |

---

## Kľúčové dokumenty

| Súbor | Popis |
|-------|-------|
| `docs/analysis/details_per_slide.md` | Rozšírený komentár ku každému slidu prezentácie |
| `docs/presentations/onko-podklady-schuzka1.html` | Prezentácia (18 slidov) |
| `app/prototype/prototyp.html` | Funkčný prototyp aplikácie |
