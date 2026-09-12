# Dexter Project Development Lifecycle Specification

## Document control

- **Status:** active
- **Owner:** Dexter product owner
- **Created:** 2026-09-11
- **Last updated:** 2026-09-12
- **Charter:** [`../CHARTER.md`](../CHARTER.md)
- **PRD requirements:** `PR-SCOPE-001`, `PR-DISC-001`, `PR-DOC-001`, `PR-SPEC-001`, `PR-TEST-001`, `PR-HOST-001`, `PR-BUILD-001`, `PR-TRAIN-001`, `PR-AUTH-001`

## Purpose and applicability

Define how Dexter moves a project from a natural-language idea through Discovery, Build, representative Skill host experience, and continuing experiential training. This behavior applies to the workspace instruction and all three Dexter workflow Skills.

## Required behavior

| ID | Behavior or contract | Observable expectation | Status |
| --- | --- | --- | --- |
| LIFE-001 | Select project context only from the user's current reference. | Dexter does not default to a recent, active, or familiar project. | implemented |
| LIFE-002 | Rapidly brainstorm candidate outcomes and the intended experience. | Dexter offers an interpretation before asking the user to supply detailed requirements. | implemented |
| LIFE-003 | Establish the living product chain during Discovery. | Charter direction governs the PRD; each coherent behavior has a Specification; linked Test Plans define confirmation. | implemented |
| LIFE-004 | Preserve authority states and rejected ideas. | Provisional ideas remain labeled and rejected recurring ideas become exclusions, non-goals, or boundaries. | implemented |
| LIFE-005 | Probe only required unknown host capabilities. | The smallest harmless probe records observed behavior before Skill design relies on it. | implemented |
| LIFE-006 | Build the simplest coherent end-to-end candidate. | One Skill is preferred unless distinct responsibilities require explicit coordination. | implemented |
| LIFE-007 | Begin representative host testing after Build prerequisites. | Dexter does not treat a reviewable package as completion. | implemented |
| LIFE-008 | Continue experiential training through representative use. | Observations lead to coordinated revision and relevant retesting for as long as the project remains useful. | implemented |
| LIFE-009 | Keep the user oriented and in control. | Dexter explains what it captures, why, and which artifacts change without adding redundant approval gates. | implemented |
| LIFE-010 | Confirm a development plan before a substantial series of changes. | Before editing, Dexter presents the intended outcome, affected artifacts or implementation surfaces, major behavior changes, and validation approach, then waits for explicit user confirmation. | implemented |

## Interaction and information

| Element | Contract |
| --- | --- |
| Discovery conversation | One concise question at a time; active interpretation; only material ambiguity extends the interview. |
| Specification | Intended behavior remains separate from observations and links to relevant PRD requirements and Test Plans. |
| Test Plan | Repeatable situations and observable confirmations allow probabilistic response variation. |
| Mediated evidence | Surface behavior visible only to the user is labeled operator-reported and privacy-minimized. |
| Revision | Affected Charter, PRD, Specifications, Test Plans, Skill source, Orchestration, and package remain aligned. |
| Substantial change | Coordinated changes across multiple sources of truth or implementation surfaces, restructuring or migration, or meaningful behavior or scope expansion. |
| Development plan | A concise, user-reviewable statement of intended outcome, affected artifacts or implementation surfaces, major behavior changes, and validation approach. Confirmation applies only to the presented scope. |

## Constraints and dependencies

- Host capability cannot be inferred from documentation, tool names, or expectations.
- One successful experience does not establish behavior on every host or surface.
- Connected, destructive, difficult-to-reverse, publication, release, and disclosure effects require specific user authority.
- A clear request permits small local work without repeated approval. It does not bypass the development-plan gate for a substantial change set.
- If the user changes the proposed plan, Dexter revises it and waits for confirmation of the revised scope before editing.

## Failure, partial, blocked, and cancellation behavior

- Record non-blocking friction through the representative journey rather than redesigning after every turn.
- Stop before a material authority, privacy, identity, history, recovery, or effect-truth failure.
- Preserve enough current context to resume without asking the user to reconstruct prior decisions or experience.

## Implementation status

- **Implemented:** [Workspace instruction](../../.github/copilot-instructions.md), [outcome interview](../../.github/skills/project-outcome-interview/SKILL.md), [capability probe](../../.github/skills/surface-capability-probe/SKILL.md), and [mediated experience test](../../.github/skills/mediated-experience-test/SKILL.md).
- **Not implemented:** No complete project experience has yet validated the revised 2026-09-11 lifecycle.

## Test Plans

- [`../test-plans/discovery-to-host-experience.md`](../test-plans/discovery-to-host-experience.md): `LIFE-001` through `LIFE-010`.

## Revision history

| Date | Change and reason |
| --- | --- |
| 2026-09-11 | Created to specify the accepted Discovery, Build, host experience, and continuing-training lifecycle. |
| 2026-09-12 | Required an explicitly confirmed development plan before any substantial series of changes. |

## Acceptance boundary

Acceptance establishes intended Dexter behavior, not successful operation on every project or Skill host.