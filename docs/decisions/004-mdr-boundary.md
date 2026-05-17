# ADR 004 — Staying outside MDR SaMD classification

**Status:** Accepted  
**Date:** 2026-05

## Context

EU Regulation 2017/745 (MDR) and the accompanying MDCG guidance on Software as a Medical Device (SaMD) define when a software product requires CE marking as a medical device. Classification triggers regulatory obligations that are incompatible with a student competition prototype timeline (conformity assessment, QMS, clinical evaluation, notified body involvement for Class IIa+).

MDCG 2019-11 guidance: software is SaMD if it is "intended to be used for one or more medical purposes" including diagnosis, prevention, monitoring, prediction, prognosis, treatment, or alleviation of disease.

## Decision

Design all product features to remain below the MDR/SaMD threshold:

- **Display only:** the app shows information, it does not process patient-specific clinical data to produce a clinical output
- **No diagnostic or triage function:** the app explicitly directs patients to contact their care team for any clinical questions
- **No ePRO with clinical feedback loop:** symptom logging (diary) is private, local, and not transmitted to clinicians
- **Explicit disclaimer:** every session includes a clear statement that the tool is educational, not a substitute for clinical advice

## Reasons

1. MDR Class IIa+ requires a notified body and full QMS — timeline of 2+ years and significant cost, incompatible with Phase 1.
2. Staying outside SaMD classification allows faster iteration and deployment.
3. The clinical value proposition (informed patient, better first consultation) does not require clinical data processing — education alone achieves it.
4. The boundary is clinically honest: we are not a diagnostic tool, and marketing it as such would be misleading.

## Alternatives considered

- **Pursue SaMD classification from the start:** Rejected. Kills the prototype timeline entirely. Revisit if Phase 3 introduces clinical decision support features.
- **Add symptom severity scoring with clinical thresholds:** Rejected for Phase 1. Scoring that triggers a clinical recommendation crosses the SaMD line.

## Consequences

- The app must never present personalized clinical recommendations based on user input.
- The diary/notes feature must remain entirely local (localStorage, no sync) to avoid creating a medical record.
- Any future feature that processes patient-reported data to produce a clinical output must trigger an MDR assessment before development.
- Disclaimer language must be reviewed by MUDr. Čermáková before public deployment.
