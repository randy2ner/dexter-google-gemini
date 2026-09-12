# Compass Skill Exchange

This is the project-local handoff area for exact Compass artifacts. It isolates test specimens from Dexter's reusable scaffolding and from other projects.

- `incoming/`: artifacts awaiting inspection.
- `ready-for-test/`: reviewed artifacts ready for Cowork import.
- `tested/`: exact artifacts used in recorded runs.
- `archive/`: superseded artifacts retained for traceability.

## Current project artifacts

| State | Artifact | Evidence |
| --- | --- | --- |
| Historical tested artifacts | [`tested/`](tested/) and earlier individual candidates | See the legacy evidence summarized by the [Test Plan](../docs/TEST-PLAN.md). |
| Earlier candidates | Individual packages under [`ready-for-test/`](ready-for-test/) | Retained as exact specimens; not the current production baseline. |
| Recommended fresh-installation set | [`ready-for-test/2026-09-08-fresh-installation/`](ready-for-test/2026-09-08-fresh-installation/) | Five byte-verified Skills; runtime unrun. |
| Production shaping baseline | [`ready-for-test/2026-09-08-production-content-test/`](ready-for-test/2026-09-08-production-content-test/) | Five byte-verified Skills; optional shaping inputs, not presumed final. |

Artifact presence does not authorize Cowork upload, execution, connected access, or deployment. `ready-for-test` means only that disconnected source and package checks are recorded.
