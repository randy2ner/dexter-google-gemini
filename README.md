# Project Dexter

Dexter is a lightweight laboratory assistant for developing, testing, packaging, and evolving Copilot Skills and Orchestrations. It helps a user move quickly from a natural-language idea to a useful end-to-end experience on a Skill host such as Cowork or Scout.

## Project knowledge model

Every project maintains a living chain:

1. `CHARTER.md` preserves vision, purpose, users, outcomes, scope, boundaries, authority, and accepted versus provisional direction.
2. `PRD.md` translates the Charter into prioritized outcomes, requirements, capabilities, acceptance signals, non-goals, constraints, and dependencies.
3. `specifications/` defines coherent behaviors and contracts in separate Markdown files.
4. `test-plans/` provides reusable prompts or situations, practical checks, observable confirmation criteria, host profiles, and dated observations.

Several Test Plans may verify one Specification, and one Test Plan may cover related behavior from several Specifications. Product direction stays in the Charter or PRD, intended behavior in Specifications, and test definitions and observations in Test Plans. Dexter does not require separate decision, finding, confidence, impact, status, scenario, or test-result records.

The canonical project structure and sharing boundary are defined in [`projects/README.md`](projects/README.md). Starting templates are under [`docs/_templates/`](docs/_templates/), and the Skill source scaffold is under [`skills/_template/`](skills/_template/).

## Development lifecycle

### Discovery gate

Dexter quickly brainstorms the outcome and intended experience with the user, establishes the Charter and PRD, specifies the behaviors the product must carry, and probes only the Skill host capabilities that must be understood before building.

Discovery is sufficient when accepted direction and testable behavior support the smallest coherent end-to-end candidate. Non-blocking uncertainty remains visible without extending the interview.

### Build gate

Dexter builds the simplest Skill or coordinated set of Skills that can produce the experience. It creates linked Test Plans with repeatable situations and observable confirmations, packages the runtime source, and begins representative testing on the intended Skill host as early as authority and prerequisites allow.

A reviewable package is not the end of development. The first host experience begins the Skill's experiential training.

### Continuing training

Representative use reveals what is useful, confusing, unnatural, missing, or host-dependent. Dexter records bounded observations, coordinates revisions across affected project artifacts and source, and tests again. This continues for as long as the project remains useful; behavior observed on one host or surface is not automatically established on another.

## Laboratory Layout

| Location | Purpose |
| --- | --- |
| [`projects/`](projects/) | Isolated projects and the canonical project-layout contract |
| [`.github/skills/`](.github/skills/) | Dexter's on-demand Discovery, capability-probe, and mediated-testing workflows |
| [`skills/_template/`](skills/_template/) | Minimal project Skill source scaffold |
| [`orchestrations/`](orchestrations/) | Reusable Orchestration guidance and template |
| [`skill-exchange/`](skill-exchange/) | Package exchange guidance for intentionally shared artifacts |
| [`docs/`](docs/) | Dexter's own living product documents and project templates |
| [`archive/`](archive/) | Non-authoritative records from prior Dexter models |

## Quick Start

1. Create an isolated directory under [`projects/`](projects/).
2. Create its Charter, PRD, Specifications, and Test Plans from the templates.
3. Develop and package the simplest end-to-end Skill or Orchestration candidate inside the project boundary.
4. Begin the representative host experience, record observations in the relevant Test Plans, and make one coordinated revision.
5. Inspect the project as a standalone directory and remove required dependencies on Dexter's root scaffolding.

## Core Principles

- **Evidence over intuition.** Success must be bounded to observed results.
- **History over hindsight.** Preserve prior dated Test Plan observations and exact tested specimens.
- **Explicit dependencies.** A changed Skill should reveal which Specifications, Orchestrations, packages, and Test Plan cases may be affected.
- **Source versus specimen.** Develop in the owning project's `skills/`; test the exact packaged copy in that project's `skill-exchange/`.
- **Small and replaceable.** The framework should help the work without becoming the work.
- **No fabricated outcomes.** Record only what was directly observed, then separate interpretation from evidence.
- **Experiential training.** Evaluate and improve Skill guidance through representative use on the intended Skill host throughout the project's useful life.

## Naming and Lifecycle

- Use lowercase kebab-case for Skill and Orchestration names.
- Preserve package layouts and filenames required by Copilot Cowork.
- Place importable `.skill` files directly in the owning project's flat `skill-exchange/` directory and identify tested packages by exact filename in the relevant Test Plan.

## Collaboration

Read [`CONTRIBUTING.md`](CONTRIBUTING.md) before changing shared records or artifacts. Never commit credentials, private customer data, tenant identifiers, or sensitive test prompts.
