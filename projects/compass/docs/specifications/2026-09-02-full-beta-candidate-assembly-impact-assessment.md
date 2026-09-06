# Change Impact Assessment: Assemble complete Compass beta candidate

## Document control

- **Date:** 2026-09-02
- **Status:** accepted for Gate 0 planning
- **Owner:** User / product owner
- **Changed source/version:** [Compass compact full-beta strategy version 1.0](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md)
- **Motivation:** [Accepted compact full-beta strategy decision](../decisions/2026-09-02-adopt-compact-full-beta-test-strategy.md)

## Change summary

Compass is moving from isolated experimental Skill slices to assembly of one complete beta candidate containing five compatible Skills and one versioned Orchestration. This changes test organization and development order; it does not change the Charter's authority, portability, history, or truthful-reporting boundaries.

The assembly work reuses prior Skill concepts and test evidence where applicable, but does not promote prior artifacts or untested claims. Shared contracts and graph schema must first be reduced to one accepted beta baseline so later Skill and Orchestration definitions do not encode incompatible identities, relationships, write outcomes, or recovery behavior.

## Impact map

| Dependent item | Current version/evidence | Impact | Required action |
| --- | --- | --- | --- |
| [Compass PRD](../requirements/compass-product-requirements.md) | 0.2 living synthesis | none to product boundaries; affected delivery order | Keep the complete-candidate beta relationship and trace new Skill responsibilities to current requirements. |
| [Shared contracts](compass-shared-contracts-specification.md) | 0.3-beta-baseline accepted; Graph Governor evidence remains scoped to the prior 0.2 read-only subset | affected | Use the accepted baseline for all Slice B responsibility specifications. |
| [Graph schema](compass-graph-schema-specification.md) | 0.3-beta-baseline accepted; Graph Governor evidence remains scoped to the prior 0.2 read-only subset | affected | Use the accepted object, identity, relationship, configuration, and Daily Log baseline; keep nonblocking fields deferred. |
| Installation Interview | Perspective Discovery 0.1.2 corrective source plus unreconciled prior Installation artifact | affected | Define bootstrap, configuration, foundational objects, approval, and validation responsibilities; keep broad daily retrieval in Daily Scan. |
| Daily Scan | Immutable prior Beta 1 reference only | affected | Preserve useful bounded retrieval and source-identity behavior while replacing prior architecture dependencies with accepted contracts. |
| Tracking Topic Interview | Immutable prior Beta 2 reference only | affected | Preserve user wording and topic authority while aligning status, relationship ownership, Daily Log, and validation handoffs. |
| Curator | Charter capability only | affected | Define review and proposal responsibilities without independent authority to reorganize or delete graph state. |
| Graph Governor | 0.1.0 experimental read-only source and bounded evidence | affected | Preserve applicable read-only behavior; define only the validation, precondition, verification, and recovery role required by beta writes. |
| Compass Orchestration | none | affected | Define lifecycle routing, typed handoffs, approvals, effect accounting, and recovery across all five Skills. |
| Prior package specimens | Immutable packages and static review | none | Retain unchanged as reference inputs; never relabel them as beta candidates or evidence. |
| Existing test evidence | Graph Governor bounded confidence; Perspective Discovery partial results | partially applicable | Reuse exact observed claims; do not extrapolate to writes, complete Skills, or integrated beta. |
| Test program | [Compact full-beta strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md) | affected | Use seven-check default ceiling and one consolidated result per gate. |

## Evidence disposition

- **Still applicable:** Graph Governor package, fixture, runtime, closure, and bounded confidence records for the exact synthetic read-only behavior; Perspective Discovery records for observed authorization, retrieval limits, privacy-minimized cancellation, and host-surface behavior; prior artifact static observations.
- **Invalidated or uncertain:** No completed evidence is invalidated. Prior architecture names, responsibilities, expected synthetic cases, and runtime claims remain non-authoritative. Any evidence about an earlier package does not establish compatibility with the future complete candidate.

## Smallest justified retest set

| Test | Reason | Decision enabled |
| --- | --- | --- |
| Surface probes S1-S3 | Candidate versions, routing, and host behavior are runtime-sensitive. | Admit exact candidate to critical-operation testing. |
| Critical operations C1-C3 | Identity, writes, recovery, authority, and privacy have material consequences. | Admit exact candidate to integrated rehearsal. |
| One complete synthetic Orchestration rehearsal | Cross-Skill handoffs and final durable state cannot be established by isolated evidence. | Decide whether to authorize full beta. |

## Excluded regression

- Do not repeat the eight closed Graph Governor read-only scenarios unless its parser, accepted contract subset, or relevant runtime changes.
- Do not run every prior synthetic case; adapt only representative cases that distinguish a beta decision.
- Do not test every schema field, card variation, file order, or conversational wording before beta.
- Do not perform connected Work IQ retrieval merely to validate interaction presentation.

## Authorization required

The [accepted beta contract baseline](../decisions/2026-09-02-accept-compass-beta-contract-baseline.md) authorizes Slice B responsibility-specification work. Compass Orchestration source still requires Slice C authorization. This assessment authorizes none of those changes by itself.