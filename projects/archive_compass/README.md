# Compass

Compass is an isolated Project Dexter laboratory project.

## Current status

- **Stage:** Artifact-first production shaping within the production release-testing phase
- **Specification:** [Current purpose, requirements, behavior, decisions, and status](docs/SPECIFICATION.md)
- **Test Plan:** [Current cases, observations, gaps, and success assessment](docs/TEST-PLAN.md)
- **Current package baseline:** Five production-test candidate Skills in [`skill-exchange/ready-for-test/2026-09-08-production-content-test/`](skill-exchange/ready-for-test/2026-09-08-production-content-test/)
- **Known intent:** Explore a set of Copilot Cowork Skills for building a knowledge graph from tracked work activity.
- **Runtime status:** Artifact shaping may use flexible Cowork conversation, current Skills, other available Cowork capabilities, and manual edits. Observations from this stage shape the product but do not prove Skill repeatability.
- **Synthetic-test disposition:** Prior synthetic evidence remains immutable and useful for focused regression or destructive-boundary checks, but it is no longer the primary release signal.

This milestone authorizes the production release-testing phase, not production release or deployment. Work content remains private in the approved managed environment; Dexter records only privacy-minimized operational evidence. The finished graph will define the target outcomes, but a release decision still requires a later controlled run of exact derived Skills, independent inspection of durable effects, and separate user approval.

## Project boundary

Everything specific to Compass belongs below this directory. Dexter's root-level files remain reusable laboratory scaffolding and methodology.

## Documentation model

Compass has exactly two active governance documents:

1. [SPECIFICATION.md](docs/SPECIFICATION.md) describes what Compass is and must do.
2. [TEST-PLAN.md](docs/TEST-PLAN.md) describes how those claims are tested and what testing currently establishes.

Prior documentation is preserved unchanged in [`archive/docs-legacy-2026-09-09/`](archive/docs-legacy-2026-09-09/) for specific historical questions. It is not current product truth and Dexter does not update it.

## Local work areas

| Area | Purpose |
| --- | --- |
| [`docs/`](docs/) | One Specification and one Test Plan |
| [`archive/`](archive/) | Read-only legacy project records |
| [`skills/`](skills/) | Compass Skill source, when authorized |
| [`orchestrations/`](orchestrations/) | Compass Orchestration source, when authorized |
| [`skill-exchange/`](skill-exchange/) | Exact Compass test artifacts |
