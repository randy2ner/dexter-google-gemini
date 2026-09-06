# Compatibility Assessment: Slice B Skill responsibility set

## Document control

- **Status:** Accepted
- **Version:** 1.0
- **Owner:** User / product owner
- **Created:** 2026-09-02
- **Last updated:** 2026-09-02
- **Baseline:** [Shared Contracts and Graph Schema 0.3-beta-baseline](../decisions/2026-09-02-accept-compass-beta-contract-baseline.md)
- **Implementation authority:** None; disconnected specification assessment only

## Set reviewed

| Skill | Proposed responsibility specification |
| --- | --- |
| Installation Interview | [Installation Interview](installation-interview-skill-specification.md) |
| Daily Scan | [Daily Scan](daily-scan-skill-specification.md) |
| Tracking Topic Interview | [Tracking Topic Interview](tracking-topic-interview-skill-specification.md) |
| Curator | [Curator](curator-skill-specification.md) |
| Graph Governor | [Graph Governor](graph-governor-skill-specification.md) |

The accepted [Perspective Discovery specification](installation-interview-perspective-discovery-skill-specification.md) remains an optional read-only Installation input and is not replaced by this set.

## Responsibility map

| Responsibility | Accountable Skill | Required handoff or boundary |
| --- | --- | --- |
| Configuration and foundational bootstrap | Installation Interview | User-approved proposal to Graph Governor; Daily Log included. |
| Daily Email and Teams evidence discovery | Daily Scan | Explicit bounded retrieval authority; evidence remains non-authoritative. |
| Conversation proposal and source correlation | Daily Scan | Verified source Conversation identity; accepted changes go to Graph Governor. |
| Topic meaning and lifecycle | Tracking Topic Interview | Exact user authority; only `active` and `archived`; Topics are never deleted. |
| Conversation-to-Topic and Topic-to-CSP organization | Tracking Topic Interview | Canonical owner fields; no reverse authoritative lists. |
| Relevance and organization review | Curator | Recommendation only; routes meaning to Tracking Topic Interview and integrity to Graph Governor. |
| Structural validation, conflict checks, and verification | Graph Governor | Does not choose semantic meaning or broaden authority. |
| Disposable synthetic recovery supervision | Graph Governor | Limited to the accepted synthetic protocol and explicit test authority. |

No two Skills claim independent authority for the same semantic decision or canonical relationship.

## Prior-artifact reconciliation

- Installation no longer contains a broad daily Email and Teams scan. Perspective Discovery is optional and read-only; bootstrap is a separate reviewed write proposal.
- Daily Scan retains bounded retrieval, source-identity caution, proposal review, and injection resistance while adopting schema version 1, Daily Log effects, and Graph Governor handoffs.
- Tracking Topic Interview retains natural conversation and user wording while replacing prior status values and persistence dependencies with `active`/`archived`, canonical relationships, and accepted handoffs.
- Curator is newly specified as proposal-only review because no prior package exists.
- Graph Governor preserves its validated read-only role and adds proposed responsibility for shared preconditions, verification, and synthetic-only recovery supervision; no prior runtime evidence supports those added responsibilities.

## Deliberate beta reductions

The responsibility set narrows several Charter capabilities under the accepted beta baseline rather than silently inventing missing design:

- Daily Scan represents accepted activity through Conversation content and Daily Log entries; schema version 1 has no standalone Activity object.
- Tracking Topic retirement is represented by archival and preserved history; Tracking Topics are never deleted.
- Curator cannot confirm authoritative last-activity reporting while last-activity semantics remain deferred.
- Graph Governor cannot automatically resolve semantic issues; only the accepted disposable synthetic recovery protocol permits bounded restoration under explicit test authority.
- Person merge, CSP retirement, staleness automation, item-level evidence retention, and production persistence remain deferred.

These reductions are visible constraints for beta responsibility design, not claims that the broader Charter intent is rejected.

## Compatibility result

The five specifications are internally compatible with the accepted `0.3-beta-baseline` at the responsibility level:

- every write-capable initiating Skill includes exact user authority, a shared change handoff, Daily Log effects, Graph Governor pre-write validation, and post-write verification;
- Curator and Graph Governor do not acquire semantic organization authority;
- Installation and Daily Scan retrieval responsibilities do not overlap;
- Daily Scan cannot mutate Topic or CSP organization;
- Tracking Topic Interview cannot retrieve evidence, delete Topics, or bypass Graph Governor; and
- all five specifications deny implementation, connected operation, graph-write, test, deployment, and release authority.

This is a design compatibility finding only. No source, package, runtime, or write behavior was inspected or tested.

## Acceptance required

The user accepted the [Slice B responsibility-set decision](../decisions/2026-09-02-propose-acceptance-of-slice-b-responsibility-set.md). Slice B is closed and Slice C Orchestration definition is authorized.