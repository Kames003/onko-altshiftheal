# ADR 003 — Sub-agentic system for content maintenance

**Status:** Proposed (Phase 3)  
**Date:** 2026-05

## Context

The primary long-term risk for a medical information product is content rot — guidelines change, drug protocols are updated, and outdated information in a patient-facing tool is a patient safety issue and a liability. Manual content review requires clinical time that the guarantor does not have on an ongoing basis.

Major oncology guidelines updated regularly:
- EAU (European Association of Urology) — prostate cancer guidelines, annual revision
- NCCN (National Comprehensive Cancer Network) — prostate cancer, continuous updates
- ČUS (Česká urologická společnost) — national adaptations

## Decision

Design Phase 3 of the architecture as a sub-agentic content maintenance pipeline:

1. **Monitor agent** — watches EAU, NCCN, ČUS publication feeds for relevant updates
2. **Diff agent** — compares new guideline content against current app content; flags affected sections
3. **Draft agent** — generates proposed content update in the established tone and structure
4. **Human validation gate** — MUDr. Čermáková (or designated clinician) reviews and approves the draft before deployment
5. **Deploy agent** — pushes approved content update through the CMS layer (Phase 2) to production

The human validation gate is non-negotiable and is architecturally enforced — no automated deployment without clinical sign-off.

## Reasons

1. Content rot is the primary reason health IT products lose clinical trust and are eventually abandoned.
2. The narrow wedge (ADR 001) makes this feasible: the surface area to monitor (prostate cancer guidelines) is bounded and manageable.
3. A broad oncology platform could not implement this pattern — the monitoring surface would be unmanageable.
4. Sub-agentic architecture is a long-term defensible differentiator that incumbent platforms (built before modern LLM agent tooling) do not currently offer.
5. The human gate keeps the system outside automated MDR classification while preserving the efficiency benefit.

## Alternatives considered

- **Periodic manual review:** Rejected as primary strategy. Relies on clinical staff availability; historically fails within 12–18 months for similar products.
- **Fully automated updates without human gate:** Rejected. Unacceptable patient safety risk; likely MDR-classifiable as SaMD with clinical decision support function.

## Consequences

- Phase 2 (CMS layer) must be designed with the agent pipeline in mind — content schema, versioning, and approval workflow are prerequisites.
- Requires an LLM API integration in Phase 3 (Claude API or equivalent).
- The human validation gate creates a dependency on clinical availability — SLA for review must be agreed with the guarantor.
- This architecture is the primary answer to the competition jury question: "How do you ensure the content stays accurate long-term?"
