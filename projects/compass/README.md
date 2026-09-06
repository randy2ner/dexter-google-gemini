# Compass

Compass is an isolated Project Dexter laboratory project.

## Current status

- **Stage:** Compass `0.3.3-dogfood-candidate` ready for protected-source first-run retest
- **Living source of truth:** [Compass source-of-truth register](docs/source-of-truth-register.md)
- **Product requirements:** [Compass PRD version 0.2](docs/requirements/compass-product-requirements.md), a living synthesis that is not separately accepted
- **Test strategy:** [Experience-led rehearsal](docs/test-plans/2026-09-02-compass-experience-led-rehearsal-plan.md), one realistic Compass journey followed by a beta decision; focused tests arise only from observed defects
- **Cowork session kit:** [Exact packages, setup boundary, opening prompt, and compact observation sheet](docs/scenarios/compass-experience-led-rehearsal.md)
- **Recorded MVP scope:** [Graph Governor read-only synthetic first slice](docs/mvp/compass-mvp-scope.md)
- **Requirements traceability:** [Compass requirements traceability matrix](docs/requirements/requirements-traceability-matrix.md)
- **Known intent:** Explore a set of Copilot Cowork Skills for building a knowledge graph from tracked work activity.
- **Charter:** Version 1.0 accepted by explicit user decision on 2026-08-28.
- **Prior Skills:** Three immutable artifacts received and statically reviewed; their Installation, Daily Scan, and Tracking Topic responsibilities are inputs to beta-candidate reconciliation.
- **Next slice:** Synthetic, read-only Graph Governor health scan accepted; generic fictional fixture family created and disconnected construction validation passed.
- **Perspective direction:** A separate read-only Work IQ Perspective Discovery boundary was accepted on 2026-08-28 to inform fictional test content without exposing Work IQ evidence to Graph Governor.
- **Perspective specification:** Installation Interview Perspective Discovery version 1.0 was accepted on 2026-08-28.
- **Perspective implementation:** Read-only source and exact reviewed package version `0.1.1-experimental` address the candidate-review usability finding through a natural question and plain-language choices. The 7,038-byte package has SHA-256 `3b563deddd98d162574d49c87e12a631d17f6a2453b7b119e92eaba8f056e6d2`; connected behavior remains untested for this version.
- **Gate 0 candidate:** Five deterministic source/package pairs, Lifecycle Orchestration `0.1-beta-candidate`, and the restorable fictional `compass-beta-graph-v1` fixture pass disconnected construction and compatibility inspection.
- **Graph Governor implementation:** Candidate `0.2.0-beta-candidate` adds static validation, verification, and synthetic recovery contracts while preserving `0.1.0-experimental` evidence as prior-version evidence only.
- **Runtime status:** The exact Graph Governor package has recorded Cowork evidence for the closed synthetic slice. Perspective Discovery `0.1.1-experimental` produced a partial connected result with a cancelled terminal outcome; `0.1.2-experimental` interface behavior remains untested. Prior artifacts and Aegis-produced claims are not accepted as Dexter runtime evidence.

The records above do not authorize Cowork import, rehearsal execution, connected retrieval, graph writes, development beta, deployment, or release. See the [Option B decision](docs/decisions/2026-09-02-adopt-experience-led-beta-route.md), [Gate 0 compatibility result](docs/test-results/2026-09-02-compass-gate-0-candidate-compatibility.md), [accepted charter](docs/charter/compass-vision-and-scope-charter.md), and [bounded prior-version confidence assessment](docs/confidence/2026-09-01-graph-governor-v0-1-0-experimental.md).

## Project boundary

Everything specific to Compass belongs below this directory. Dexter's root-level files remain reusable laboratory scaffolding and methodology.

## Local work areas

| Area | Purpose |
| --- | --- |
| [`docs/charter/`](docs/charter/) | Vision and scope agreement |
| [`docs/requirements/`](docs/requirements/) | Living product requirements and requirement traceability |
| [`docs/mvp/`](docs/mvp/) | Explicitly recorded MVP learning or delivery scope |
| [`docs/specifications/`](docs/specifications/) | Requirements, capability, MVP, and behavioral specifications |
| [`docs/inventory/`](docs/inventory/) | Compass Skill and Orchestration registry |
| [`docs/test-plans/`](docs/test-plans/) | Planned validation scope |
| [`docs/scenarios/`](docs/scenarios/) | Reproducible scenarios |
| [`docs/experiments/`](docs/experiments/) | Hypotheses and controlled changes |
| [`docs/test-results/`](docs/test-results/) | Direct test evidence |
| [`docs/confidence/`](docs/confidence/) | Evidence-based readiness assessments |
| [`docs/findings/`](docs/findings/) | Cross-run findings and lessons |
| [`docs/decisions/`](docs/decisions/) | Accepted choices and rationale |
| [`skills/`](skills/) | Compass Skill source, when authorized |
| [`orchestrations/`](orchestrations/) | Compass Orchestration source, when authorized |
| [`skill-exchange/`](skill-exchange/) | Exact Compass test artifacts |
