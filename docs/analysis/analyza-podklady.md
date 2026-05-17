# ALT+SHIFT+HEAL — Analýza a podklady ke schůzce

> Zdravotnictví 4.0 Challenge (FEI VŠB–TUO) · klinický garant: MUDr. Zuzana Čermáková, Ph.D., FN Ostrava, Onkologická klinika
> Tým: Tomáš Mucha (full-stack/founder), Adela Martynková (data/health), Martin Tomica (SW eng.), David Tobola (Python/mobile)

## 1. Rozbor zadání (prezentace, 4 slidy, ~2 min pitch)

- Není to specifikace, ale **elevator pitch klinického problému**. Velký prostor pro definici → výhoda i riziko.
- **Problém:** ~400 nových pacientů/rok (FN Ostrava); informace ústně+papírově; až při vstupním vyšetření → informační deficit **před** první návštěvou.
- **Skutečná inovace = doručení, ne obsah:** odkaz/QR v lékařské zprávě odesílajícího pracoviště, personalizace dle typu léčby, příchod „připraven, ne naslepo".
- **Upřesnění týmu (A. Martynková):** není to jen průvodce — PDF se ztratí; pacient si může kontrolovat výsledky a přijde připravený. → trvalý bod pravdy.
- Zámerná **jednoduchost je feature**, ne nedostatek ambice. Cíl je provozní (orientace, stres, čas), ne klinický → snáze obhájitelné a měřitelné.

## 2. Validace a trh

Koncept je **evidence-based**: prospektivní studie n=112 (tablet+video vs. papír u ca prostaty, vyšší spokojenost), ePRO compliance studie, ICHOM standard set. Kaiku Health rutinně v 40+ EU onkocentrech.

**Mapa řešení:**
- A — statický obsah (CZ: rakovinaprostaty.org, cus.cz, linkos, MOÚ; svět: ZERO, PCF, Uroweb) → kurátorovat, neduplikovat.
- B — guideline navigátory (NCCN, Preveta) → pro lékaře, jiná skupina.
- C — ePRO platformy (Kaiku, Resilience, Careology, Vinehealth, Outcomes4Me, Belong) → těžké, drahé, regulované.
- D — **pre-arrival doručení přes referral → bílá díra = naše pozice**.

## 3. Je „celkový onkologický nástroj" dobrý nápad?

- ⛔ **Ne jako šířka funkcí** — červený oceán financovaných, MDR-regulovaných, v EU nasazených hráčů. Student. tým je za 10 měs. nepředběhne.
- ✅ **Ano jako úzký klín** — referral-embedded pre-arrival průvodce pro ca prostaty je volné místo.
- ★ **Doporučení: úzký vstup, škálovatelná architektura.** „Malý obhájitelný pilot, velká udržitelná vize." Modulární obsah + sub-agentní systém pro aktualizaci a rozšiřitelnost = odpověď na hlavní riziko (zastarání obsahu) i cesta k celoonkologické vizi.

## 4. Otevřené otázky na klinického garanta

1. Kde přesně vstupuje odkaz do cesty pacienta (urolog vs. onkologie; ručně vs. auto)?
2. Kdy je znám typ léčby? (často až MDT po 1. vyšetření — řeší logiku personalizace)
3. Generický vs. tokenovaný odkaz? (GDPR, autentizace, „kontrola výsledků")
4. Kdo je vlastník/garant aktualizace obsahu? (největší dlouhodobé riziko)
5. Jak měříme přínos? (čas vstupního vyšetření, pre/post dotazník stresu, opakované dotazy)

## 5. Hlavní rizika

Udržitelnost obsahu (🔴) · digitální gramotnost ~70 let + role rodiny (🔴) · logický rozpor personalizace před známým typem léčby (🟠) · adopce odesílajících lékařů (🟠) · „další portál" (🟠) · GDPR (🟠) · MDR pokud se rozšíří scope (🟢 při hlídání).

## 6. Výstupy v tomto folderu

- `prezentace-schuzka.html` — slide deck pro schůzku (12 slidů, klávesy ←/→).
- `prototyp.html` — klikací prototyp průvodce (výběr léčby, kroky, příprava, průběh, rodina).
- `analyza-podklady.md` — tento dokument.

## Zdroje

- Zdravotnictví 4.0 Challenge — https://www.fei.vsb.cz/challenge/cs
- Tablet vs. papír, ca prostaty — https://pubmed.ncbi.nlm.nih.gov/35711488/
- ePRO compliance — https://pmc.ncbi.nlm.nih.gov/articles/PMC7142743/
- Digital care pathway / ICHOM — https://theclinician.com/care-pathways/localised-prostate-cancer-digital-care-pathway
- Kaiku Health (Elekta) — https://dtxalliance.org/products/kaiku-health/
- Resilience Care — https://www.resilience.care/us
- Outcomes4Me — https://outcomes4me.com/
- CZ obsah — https://www.rakovinaprostaty.org/ · https://www.cus.cz/pro-pacienty/diagnozy/karcinom-prostaty/
