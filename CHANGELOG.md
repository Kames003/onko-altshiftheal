# Changelog

All notable changes to this project are documented here.  
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

---

## [0.2.0] — 2026-05-17

### Added
- 18-slide team presentation (`docs/presentations/onko-podklady-schuzka1.html`) — full system analysis, architecture overview, sub-agentic content maintenance concept, competitive positioning
- `docs/analysis/details_per_slide.md` — expanded clinical and technical context for each slide, including open questions for the clinical guarantor
- `docs/decisions/` — Architecture Decision Records: narrow wedge (001), offline-first single-file (002), sub-agentic content maintenance (003), MDR boundary (004)
- GitHub Actions workflow for automatic deployment to GitHub Pages on push to `main`
- `CHANGELOG.md`, `LICENSE`
- `.github/ISSUE_TEMPLATE/` — bug report and feature request templates
- `docs/index.html` — redirect entry point for GitHub Pages

### Changed
- Repository restructured: `docs/`, `app/`, `research/` hierarchy
- Prototype moved to `app/prototype/prototyp.html`

### Fixed
- JavaScript syntax error in prototype (unterminated string literal in HOSPITAL data constant) — all buttons were unresponsive

---

## [0.1.0] — 2026-05 (pre-repo)

### Added
- Functional prototype (`prototyp.html`) — single-file PWA, localStorage, offline-capable
- Treatment personalization: RT, HT, surgery, active surveillance, RT+HT
- Features: treatment timeline, side effects, nutrition, saved questions (with print), hospital navigation, family view, personal diary
- Initial system analysis (`docs/analysis/analyza-podklady.md`) — since superseded by `details_per_slide.md`
- Source brief: `docs/brief/35_Čermáková.pptx`
