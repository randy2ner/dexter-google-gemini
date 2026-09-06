# Implementation Plan: Compass full-beta candidate assembly

## Document control

- **Status:** active; Slice C accepted and Slice D planning authorized
- **Version:** 1.0
- **Owner:** User / product owner
- **Created:** 2026-09-02
- **Last updated:** 2026-09-02
- **Governing sources:** [Compass PRD 0.2](../requirements/compass-product-requirements.md); [compact full-beta strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md); [assembly impact assessment](2026-09-02-full-beta-candidate-assembly-impact-assessment.md)
- **Implementation authority:** Slice D planning and impact analysis only

## Objective

Assemble one internally compatible beta candidate containing all five Compass Skills and one project Orchestration, using the minimum accepted contracts and the smallest pre-beta test program that can responsibly support full beta admission.

## Planned source and artifacts

| Path or artifact | Purpose | Change allowed under this plan |
| --- | --- | --- |
| [Shared contracts](compass-shared-contracts-specification.md) | Cross-Skill vocabulary, identity, authority, handoff, validation, write, Daily Log, recovery, and outcome baseline | Accepted at `0.3-beta-baseline` |
| [Graph schema](compass-graph-schema-specification.md) | Portable beta object, configuration, and managed Daily Log representation | Accepted at `0.3-beta-baseline` |
| `projects/compass/docs/specifications/*-skill-specification.md` | Responsibility contract for each Skill | Slice B accepted |
| `projects/compass/skills/<skill>/` | Editable source for exact beta candidate Skills | None until the applicable Skill slice is accepted |
| `projects/compass/orchestrations/compass-work-memory-lifecycle/` | Versioned sequence, handoffs, approvals, failure behavior, and recovery | Slice C accepted at `0.1-beta-candidate` |
| `projects/compass/skill-exchange/ready-for-test/` | Exact inspected candidate packages | None until Slice D is accepted |
| `projects/compass/fixtures/` or existing project fixture area | Disposable synthetic beta graph and restore baseline | None until Slice D is accepted |

## Traceability

| Requirement | Planned implementation | Evaluation |
| --- | --- | --- |
| `PR-AUTH-001`, `PR-SAFE-001` | Shared approval scope, typed handoffs, Graph Governor boundary, conflict and recovery outcomes | C2, C3, integrated rehearsal |
| `PR-PORT-001`, `PR-HIST-001`, `PR-GRAPH-001` | Accepted Markdown/YAML schema, canonical relationship ownership, preserved archival history | C1, C2, external inspection |
| `PR-TRUTH-001` | Common terminal outcomes and complete effect accounting | S3, C2, C3, integrated rehearsal |
| `PR-INT-001` | Progressive choices, typed fallbacks, concise Skill-specific interaction guidance, coherent Orchestration voice | S1, integrated rehearsal, beta |
| `PR-PRIV-001`, `PR-EVID-001` | Minimized handoffs and verified source Conversation identity | S3, C1, C3 |
| `PR-TEST-001` | Exact versions, consolidated gate evidence, bounded beta readiness | Gates 1-4 |

## Construction and validation sequence

### Slice A: Accept the minimum beta contract baseline

Decide only what every beta Skill must share:

- stable graph ID and object IDs;
- source item, source Conversation, and graph identity distinction;
- canonical Conversation-to-Topic and Topic-to-CSP relationship ownership;
- required configuration and timezone behavior;
- proposal and approval scope;
- minimum typed handoff fields;
- pre-write validation and post-write verification;
- Daily Log as a same-operation effect;
- conflict detection, recoverability, and common terminal outcomes; and
- preservation of unmanaged user content.

Select one simple recovery protocol for a disposable beta graph. Defer item-level evidence storage, final last-activity semantics, staleness automation, Person merge, CSP retirement, and other behavior not required by the minimum lifecycle.

**Checkpoint:** User accepts the exact shared-contract and schema sections before any write-capable Skill source is authored.

### Slice B: Define five Skill responsibility specifications

Work in dependency order:

1. Installation Interview owns setup, graph configuration, foundational user-approved objects, and validated bootstrap. Perspective Discovery is a bounded optional input, not the installer itself.
2. Daily Scan owns bounded daily evidence discovery and Conversation proposals; it does not independently organize Topics.
3. Tracking Topic Interview owns user-approved Topic lifecycle and Conversation alignment proposals.
4. Curator owns review, relevance, staleness, and organization proposals; it does not independently apply consequential changes.
5. Graph Governor owns shared validation, write preconditions, post-write verification, and deterministic recovery behavior accepted by contract; it does not choose user meaning.

Each specification defines allowed inputs, proposed and permitted effects, user decisions, handoffs, exclusions, interaction style, and one representative positive, blocked, and boundary behavior. Reuse prior artifact language only when it conforms to current contracts.

**Checkpoint:** User accepts the five responsibility specifications as a compatible set.

### Slice C: Define the Compass Orchestration

Create `compass-work-memory-lifecycle` only after Slice B establishes participant responsibilities. Define:

- installation-to-routine-use transition;
- Daily Scan proposal review and graph-change request;
- Tracking Topic routing when organization is requested;
- Curator review routing;
- Graph Governor validation, application boundary, verification, and recovery;
- typed handoffs and correlation IDs;
- approval renewal after material change;
- cancellation and partial-failure behavior; and
- one coherent interaction voice across Skill handoffs.

**Checkpoint:** User accepts version 0.1-beta-candidate of the Orchestration definition. Definition does not authorize execution.

### Slice D: Package construction and beta-candidate inspection

After separate implementation authorization:

- author or revise each Skill source;
- preserve prior source and packages;
- create deterministic packages;
- register exact versions and hashes;
- create one disposable synthetic graph and restore baseline;
- inspect source/package identity and dependency compatibility; and
- prepare one concise Gate 1 execution authorization.

**Checkpoint:** Gate 0 closes only when the exact five-Skill package set, Orchestration, fixture, and restore procedure are inspectable and compatible.

## Stop conditions

- A proposed responsibility weakens user authority, portable data, preserved history, or truthful reporting.
- Two Skills claim canonical ownership of the same relationship or modification.
- Source Conversation identity cannot be obtained or distinguished from item identity for an automatic write path.
- The recovery protocol can overwrite an intervening user edit or report uncertain state as committed.
- A slice requires resolving a deferred behavior that is not necessary for beta admission.
- Implementation begins without an accepted bounded authorization.

## Risks and rollback

- **Overdesign before beta:** Accept only the minimum lifecycle contract and defer nonblocking semantics.
- **Prior artifact inheritance:** Keep prior packages immutable and trace each reused behavior to current requirements and accepted contracts.
- **Cross-Skill duplication:** Give every authoritative relationship and mutation one accountable owner.
- **Unsafe connected writes:** Use only a disposable synthetic graph through Gate 3; require backup and recovery before full beta.
- **Excessive testing:** Keep the seven-check ceiling and rerun only affected checks.

Planning records can be superseded without changing completed evidence. Source and packages created later receive new versions rather than rewriting tested specimens.

## Authorization boundary

This plan defines sequencing and decision checkpoints. It does not accept draft contract semantics, authorize Skill or Orchestration implementation, package creation, connected access, graph writes, test execution, beta launch, deployment, or release.