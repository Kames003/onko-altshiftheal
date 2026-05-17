# ADR 001 — Narrow wedge: prostate cancer, pre-arrival, referral-embedded

**Status:** Accepted  
**Date:** 2026-05

## Context

The oncology patient journey has many pain points across multiple cancer types, treatment phases, and care settings. There are well-funded global platforms (Kaiku Health / Elekta, Resilience, Outcomes4Me, Belong) covering broad oncology patient support with large teams and significant capital.

The team has one clinical partner (FN Ostrava, Onkologická klinika), one clinical guarantor (MUDr. Čermáková), a 10-month prototype window, and no external funding at project start.

## Decision

Scope the product to a single, defensible wedge:
- **Cancer type:** prostate carcinoma only
- **Phase:** pre-arrival (between urology referral and first oncology visit)
- **Distribution:** QR / link embedded in the referral document — push model, no registration

## Reasons

1. The pre-arrival gap is unaddressed by all current platforms — they begin at or after the first oncology visit.
2. Prostate cancer has the highest incidence among oncological diagnoses at FN Ostrava, maximizing pilot reach.
3. Narrow scope allows deep personalization (5 treatment paths: RT, HT, surgery, active surveillance, RT+HT) within the prototype window.
4. A focused pilot produces measurable outcomes (patient preparedness score, question quality at first visit) that a broad tool cannot.
5. The jury evaluates defensible scope, real clinical partnership, and a path to sustainability — not breadth.

## Alternatives considered

- **Broad oncology platform:** Rejected. Requires multi-cancer content governance, complex personalization logic, and directly competes with capitalized incumbents.
- **During-treatment ePRO monitoring:** Rejected. Requires MDR classification, clinical validation, and integration with hospital NIS — out of scope for this phase.

## Consequences

- Architecture must be modular so other cancer types can be added in later phases without rewriting.
- Content governance and update cadence are critical risks (see ADR 003).
- The sub-agentic maintenance layer (ADR 003) is only viable because of this narrow scope.
