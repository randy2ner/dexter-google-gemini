# Implementation Plan: Slice D complete beta-candidate construction

## Document control

- **Status:** accepted and active
- **Version:** 1.0
- **Owner:** User / product owner
- **Created:** 2026-09-02
- **Last updated:** 2026-09-02
- **Governing sources:** [Assembly plan](2026-09-02-compass-full-beta-candidate-assembly-plan.md); [accepted baseline](../decisions/2026-09-02-accept-compass-beta-contract-baseline.md); [accepted Slice B set](../decisions/2026-09-02-propose-acceptance-of-slice-b-responsibility-set.md); [accepted Orchestration](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)
- **Implementation authority:** Exact disconnected construction actions in the accepted Slice D decision

## Objective

Construct one disconnected, inspectable Gate 0 candidate containing exact source and package versions for all five Skills, the accepted Orchestration definition, and a disposable synthetic lifecycle graph with a verified restore baseline.

## Candidate identities

| Capability | Editable source | Candidate version | Package |
| --- | --- | --- | --- |
| Installation Interview | `skills/compass-installation-interview/` | `0.1.0-beta-candidate` | `compass-installation-interview-v0.1.0-beta-candidate.skill` |
| Daily Scan | `skills/compass-daily-scan/` | `0.1.0-beta-candidate` | `compass-daily-scan-v0.1.0-beta-candidate.skill` |
| Tracking Topic Interview | `skills/compass-tracking-topic-interview/` | `0.1.0-beta-candidate` | `compass-tracking-topic-interview-v0.1.0-beta-candidate.skill` |
| Curator | `skills/compass-curator/` | `0.1.0-beta-candidate` | `compass-curator-v0.1.0-beta-candidate.skill` |
| Graph Governor | `skills/graph-governor/` | `0.2.0-beta-candidate` | `graph-governor-v0.2.0-beta-candidate.skill` |
| Lifecycle coordination | `orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md` | `0.1-beta-candidate` | Registered definition; no separate executable package is claimed. |

All paths are relative to `projects/compass/`. Packages are placed in `skill-exchange/ready-for-test/` only after disconnected inspection passes.

## Planned source and artifacts

| Path or artifact | Purpose | Change allowed after authorization |
| --- | --- | --- |
| Five source directories listed above | Cowork Skill instructions and required references | Create four; revise Graph Governor as a new source version |
| `docs/inventory/*-skill-profile.md` | Current identity, dependencies, permissions, package hash, and evidence boundary | Create or update five current profiles |
| `test-data/compass-beta-graph-v1/` | Fictional lifecycle baseline, operation snapshot, restore procedure, and manifest | Create |
| `skill-exchange/ready-for-test/*.skill` | Exact deterministic candidate packages | Create five after source inspection |
| `docs/test-results/2026-09-02-*-source-and-package-inspection.md` | Direct disconnected observations | Create one concise record per Skill or one consolidated record if all checks are identical |
| `docs/test-results/2026-09-02-compass-beta-graph-v1-construction-validation.md` | Fixture inventory, hashes, restore verification, and content declaration | Create |
| `docs/test-results/2026-09-02-compass-gate-0-candidate-compatibility.md` | Exact package-set and Orchestration compatibility result | Create after all prior inspections pass |
| Source-of-truth, RTM, exchange README, and registries | Current Gate 0 status and artifact links | Update only from observed construction results |

## Construction sequence

### Stage 1: Author sources

1. Create Installation Interview from its accepted parent responsibility and incorporate the approved Perspective Discovery progressive patterns without importing broad installation retrieval.
2. Create Daily Scan from its accepted responsibility and reusable prior interaction patterns, replacing obsolete schema and capability references.
3. Create Tracking Topic Interview from its accepted responsibility, canonical relationship ownership, and `active`/`archived` lifecycle.
4. Create Curator as bounded review and proposal routing with no mutation path.
5. Revise Graph Governor to `0.2.0-beta-candidate`, preserving its tested read-only capabilities and adding shared handoff validation, post-write verification guidance, and synthetic-only recovery supervision.

Each source must keep one-to-three-choice progressive interactions where choices are useful, typed fallbacks for required controls, concise user-facing outcomes, and exact exclusions.

**Checkpoint:** disconnected source inspection confirms each Skill conforms to its accepted responsibility and baseline before fixture or package construction continues.

### Stage 2: Construct disposable lifecycle fixture

Create a new wholly fictional graph separate from `gg-synthetic-graph-v1`. It must support installation/bootstrap state, one bounded synthetic daily evidence set, Conversation creation/update, Topic organization, Curator review, Graph Governor validation, Daily Log effects, one conflict condition, and one recoverable partial-write condition.

Retain a complete baseline snapshot outside the materialized graph root. Record every file's byte count and SHA-256, deterministic materialization steps, expected operation IDs, and restore verification. Do not encode unresolved last-activity or item-level evidence schemas.

**Checkpoint:** baseline validates against schema version 1 and restore reproduces every recorded hash.

### Stage 3: Package and inspect

Build each `.skill` deterministically from its source directory with `SKILL.md` at archive root. Inspect member names, relative paths, text equality, versions, dependency declarations, permissions, absence of traversal or unexpected binary members, and SHA-256.

Do not overwrite prior packages. A failed inspection keeps the package out of `ready-for-test/` until a corrected source receives a distinct candidate build identity or the failed artifact is removed before registration.

**Checkpoint:** five exact package hashes and source identities are registered with no runtime claim.

### Stage 4: Close Gate 0 compatibility

Compare the five inspected packages and accepted Orchestration for handoff fields, authority, object ownership, Daily Log coupling, outcomes, privacy, cancellation, and recovery. Record direct observations separately from interpretation.

Gate 0 closes only when all five exact packages, the Orchestration, fixture, restore procedure, profiles, and inspection evidence are linked and no design conflict remains.

**Checkpoint:** prepare a separate Gate 1 authorization identifying exact package hashes and synthetic inputs. Do not execute Gate 1 under Slice D authority.

## Traceability

| Requirement | Candidate implementation | Gate 0 evidence |
| --- | --- | --- |
| `PR-AUTH-001`, `PR-INT-001` | Progressive proposal and approval interactions with typed fallbacks | Source/package inspection and compatibility review |
| `PR-PORT-001`, `PR-HIST-001`, `PR-GRAPH-001` | Schema version 1 Markdown/YAML and preserved history | Fixture construction validation |
| `PR-PRIV-001`, `PR-EVID-001` | Bounded retrieval declarations, minimized handoffs, durable source identity | Source/package inspection; runtime claims remain untested |
| `PR-SAFE-001`, `PR-TRUTH-001` | Graph Governor boundary, common outcomes, effect accounting, synthetic recovery | Source/package and fixture compatibility review |
| `PR-TEST-001` | Exact source, package, dependency, fixture, and hash registration | Consolidated Gate 0 compatibility result |

## Stop conditions

- Any stop condition in the linked impact assessment occurs.
- A source cannot satisfy its accepted responsibility without a product decision.
- A deterministic package cannot be reproduced from current source.
- Fixture validation or restore comparison fails.
- Gate 0 compatibility requires broadening a Skill's accepted authority.
- Work would cross into Cowork import, invocation, connected retrieval, connected storage, or runtime testing.

## Risks and rollback

- Preserve every incoming and tested package unchanged; new candidate versions are additive.
- Preserve the accepted Orchestration and responsibility specifications; stop for review rather than silently revise behavior.
- Remove only newly generated, unregistered failed package output when rebuilding; never remove evidence or prior specimens.
- Restore the disposable fixture only from its recorded external baseline and verify hashes afterward.
- Record unsupported runtime assumptions as untested limitations rather than implementation claims.

## Authorization boundary

Acceptance of this plan alone authorizes nothing. The linked decision must separately authorize the exact disconnected source, fixture, packaging, inspection, and registration actions. Neither document authorizes Cowork import or execution, Microsoft 365 access, connected graph writes, Gate 1, beta launch, deployment, or release.