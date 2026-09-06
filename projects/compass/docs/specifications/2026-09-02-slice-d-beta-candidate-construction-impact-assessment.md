# Change Impact Assessment: Construct complete Compass beta candidate

## Document control

- **Date:** 2026-09-02
- **Status:** accepted for Slice D planning
- **Owner:** User / product owner
- **Changed source/version:** [Accepted lifecycle Orchestration 0.1-beta-candidate](../../orchestrations/compass-work-memory-lifecycle/ORCHESTRATION.md)
- **Motivation:** [Accepted Slice C decision](../decisions/2026-09-02-propose-acceptance-of-compass-lifecycle-orchestration.md)

## Change summary

Slice D would turn the accepted responsibility and coordination specifications into one inspectable, disconnected beta candidate: five editable Skill sources, five deterministic `.skill` packages, five current inventory profiles, and one disposable complete-lifecycle synthetic graph with a verified restore baseline.

This construction changes no accepted product meaning. It does not execute Skills, access Microsoft 365, write a connected or personal graph, or establish runtime confidence.

## Impact map

| Dependent item | Current state | Impact | Required action |
| --- | --- | --- | --- |
| Installation Interview | No complete parent source; Perspective Discovery `0.1.2-experimental` source exists separately | affected | Create `compass-installation-interview` source that incorporates the accepted progressive interaction without rewriting the preserved sub-slice. |
| Daily Scan | Prior package only in immutable incoming area | affected | Create new source from accepted responsibility; use prior package only as a design reference. |
| Tracking Topic Interview | Prior package only in immutable incoming area | affected | Create new source from accepted responsibility; replace prior statuses and architecture dependencies. |
| Curator | Accepted responsibility only | affected | Create first source with proposal-only review behavior. |
| Graph Governor | Tested `0.1.0-experimental` read-only source/package | affected | Create a new version from current source, preserving validated behavior and adding only accepted candidate responsibilities. Keep tested package unchanged. |
| Lifecycle Orchestration | Accepted definition `0.1-beta-candidate` | affected dependency | Keep definition unchanged unless construction exposes a contract conflict; any material change returns to Slice C review. |
| Shared contracts and graph schema | Accepted `0.3-beta-baseline` | governing dependency | Candidate sources must claim this exact baseline and may not resolve deferred behavior privately. |
| Existing Graph Governor fixture | `gg-synthetic-graph-v1` for read-only scenarios | unaffected | Preserve unchanged; do not extend or relabel it as the lifecycle fixture. |
| New lifecycle fixture | absent | new | Create `compass-beta-graph-v1` with fictional inputs, baseline inventory, operation snapshot, and deterministic restore procedure. |
| Existing packages and evidence | immutable prior/tested specimens | unaffected | Preserve bytes, hashes, results, and confidence claims unchanged. |
| Inventory and exchange | partial profiles and candidate artifacts | affected | Add current profiles, exact versions, package hashes, dependencies, permissions, and disconnected inspection records. |

## Evidence disposition

- **Still applicable:** Graph Governor `0.1.0-experimental` evidence for its exact read-only behaviors; Perspective Discovery evidence for observed authorization, cancellation, privacy minimization, and host-control limitations; prior static-review observations.
- **Not transferable:** No prior evidence establishes the new complete Installation source, current Daily Scan, current Tracking Topic Interview, Curator, expanded Graph Governor, packaged candidate set, Orchestration behavior, writes, recovery, or interoperability.
- **Preserved unchanged:** Incoming prior packages, tested Graph Governor package, completed results, confidence assessment, and `gg-synthetic-graph-v1`.

## Smallest disconnected validation set

1. Verify every source has a root `SKILL.md`, required references, declared identity/version, accepted dependency versions, permissions, exclusions, and no secrets or personal data.
2. Verify the lifecycle fixture is wholly fictional, schema-valid at baseline, fully inventoried by byte count and hash, and restorable from an external snapshot.
3. Build each package deterministically and verify archive safety, root layout, source/package member equality, version, and SHA-256.
4. Verify all five packages and the accepted Orchestration use compatible handoff fields, authority boundaries, object ownership, Daily Log behavior, outcomes, and recovery limits.

These are Gate 0 inspections, not Cowork runtime tests and not additions to the seven-check pre-beta ceiling.

## Stop conditions

- Construction requires changing an accepted responsibility, shared contract, schema rule, or Orchestration behavior.
- A candidate depends on a deferred behavior such as authoritative last activity or production persistence.
- A package cannot be reproduced from its registered source or contains an unexpected member.
- The fixture contains real, tenant-specific, personal, customer, or Work IQ-derived content.
- A candidate implies connected access, graph-write, test, deployment, or release authority.
- Existing immutable package or evidence bytes would need to change.

## Authorization required

Accept the [proposed Slice D bounded construction decision](../decisions/2026-09-02-propose-slice-d-beta-candidate-construction.md) before creating or modifying Skill source, fixture content, packages, profiles, or inspection records.