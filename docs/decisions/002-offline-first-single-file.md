# ADR 002 — Offline-first, single-file PWA, no backend

**Status:** Accepted  
**Date:** 2026-05

## Context

The target user is a prostate cancer patient, typically 60–75 years old, receiving a QR code or link in a paper referral from a urologist. They will open the guide at home, potentially on a mobile device with variable connectivity. No hospital IT department is involved in distribution. There is no budget for server infrastructure in Phase 1.

## Decision

Build the patient application as a single self-contained HTML file:
- All logic, styles, and content in one file — no external dependencies at runtime
- State persistence via `localStorage` — no backend, no user accounts
- Deployable via GitHub Pages (static), or distributable as a file attachment
- Progressive Web App manifest so the patient can install it to their home screen

## Reasons

1. A single file has zero deployment complexity — the QR code can point directly to a GitHub Pages URL or to a file on any server.
2. No backend means no GDPR data processor obligations in Phase 1 (all data stays on the device).
3. Offline capability is critical — patients may review the guide during hospital visits with poor connectivity, or in areas with limited data.
4. Eliminates any risk of the service being "down" before a patient's critical first appointment.
5. Keeps the project outside MDR scope: the app stores and displays information; it does not transmit clinical data or make clinical decisions.

## Alternatives considered

- **React/Next.js SPA with backend:** Rejected for Phase 1. Adds build toolchain, hosting costs, auth complexity, and GDPR obligations without adding user-facing value.
- **Native mobile app:** Rejected. App store submission latency, OS fragmentation, and installation friction contradict the "open instantly from QR" distribution model.

## Consequences

- Content updates require a new file deployment (mitigated in Phase 2 by CMS layer, ADR 003).
- localStorage is not shared across devices — patients who switch devices lose their saved notes and questions. Acceptable for Phase 1.
- Bundle size must be managed manually as content grows.
