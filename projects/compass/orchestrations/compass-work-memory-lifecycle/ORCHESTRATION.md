# Orchestration: Compass work-memory lifecycle

## Identity

- **Name:** compass-work-memory-lifecycle
- **Version:** 0.2.0-dogfood-candidate
- **Owner:** User / product owner
- **Status:** accepted definition
- **Created:** 2026-09-02
- **Last updated:** 2026-09-02
- **Implementation authority:** None; Orchestration definition only

## Purpose

Coordinate the five Compass Skills as one understandable work-memory lifecycle while preserving each Skill's accepted responsibility, the user's authority over durable meaning, and Graph Governor's structural safety boundary.

The Orchestration provides continuity, routing, handoff, approval, cancellation, effect-accounting, and recovery rules. It does not become a sixth Skill, hold hidden authority, or create an independent source of graph truth.

## Trigger

The Orchestration begins from one explicit user intent:

- install or resume Compass setup;
- review one selected day of authorized work activity;
- create, refine, align, merge, archive, or reactivate a Tracking Topic;
- review the usefulness or organization of retained work memory; or
- inspect graph integrity or resolve a known issue.

The entry point routes directly to the accountable Skill. Installation is required before date-dependent or graph-mutating routine use, but routine workflows do not replay installation.

## Dependencies

| Dependency | Type | Version/constraint | Required | Failure impact |
| --- | --- | --- | --- | --- |
| [Shared Contracts](../../docs/specifications/compass-shared-contracts-specification.md) | Contract | `0.3-beta-baseline` | Yes | Stop the affected handoff or operation. |
| [Graph Schema](../../docs/specifications/compass-graph-schema-specification.md) | Schema | `0.3-beta-baseline` / schema version 1 | Yes | Stop graph mutation; read-only guidance may continue. |
| [Installation Interview](../../docs/specifications/installation-interview-skill-specification.md) | Skill responsibility | `0.2.3-dogfood-responsibility` | Yes for setup | Setup cannot complete. |
| [Daily Scan](../../docs/specifications/daily-scan-skill-specification.md) | Skill responsibility | `0.2-dogfood-responsibility` | Yes for daily capture | Daily evidence cannot become Conversation proposals. |
| [Tracking Topic Interview](../../docs/specifications/tracking-topic-interview-skill-specification.md) | Skill responsibility | `0.2-dogfood-responsibility` | Yes for organization | Topic lifecycle and relationship changes remain unapplied. |
| [Curator](../../docs/specifications/curator-skill-specification.md) | Skill responsibility | `0.2-dogfood-responsibility` | Yes for review | Curation review is unavailable; other flows remain independent. |
| [Graph Governor](../../docs/specifications/graph-governor-skill-specification.md) | Skill responsibility | `0.3-dogfood-responsibility` | Yes for writes and integrity | No durable write may proceed or be reported committed. |
| User | Human authority | Current interaction | Yes for consequential meaning | Proposal remains proposed, rejected, cancelled, or blocked. |

## Interaction continuity

Compass presents one current purpose, one current accountable Skill, and one next meaningful user decision. Internal handoffs should not force the user to restate accepted context or expose protocol mechanics.

Every transition must:

1. name the practical reason for the transition when it is not obvious;
2. carry only the accepted context needed by the receiving Skill;
3. preserve proposal versus authoritative-state distinctions;
4. retain one correlation ID across validation, application, recovery, and reporting; and
5. provide typed continue, change, back, pause, or cancel paths where they are meaningful.

An initiating Skill remains responsible for the user-facing outcome of its request. Graph Governor may explain a block or recovery state directly, but the Orchestration returns control to the initiating Skill with that result rather than ending in an unexplained subsystem response.

## Flow

### 1. Installation and resume

1. `Help me install Compass` routes directly to Installation Interview, which offers to create a user-confirmed OneDrive Documents `Compass` folder or use one existing folder.
2. Installation Interview inspects only the selected folder to distinguish new, resumable, configured, conflicting, or inaccessible setup.
3. For new setup, it collects direct user context and may use a user-selected classified or sensitivity-labeled Microsoft 365 file or Loop page through the signed-in Cowork context. Classification alone is not a stop condition; source protection remains platform-enforced and only minimized user-approved derivations may enter the graph.
4. After selected-source retrieval and before managed structure is created, it proves one disposable representative plain-text write, read-back, and cleanup at the confirmed root in the current protected session context. Only an actual environment refusal stops as `write-blocked` / `blocked`.
5. It prepares one exact bootstrap proposal for configuration, user-selected foundational objects, relationships, and installation-date Daily Log.
6. The user approves, changes, skips optional objects, or cancels.
7. An approved proposal goes to Graph Governor for pre-write validation, config-first authorized application, and post-write verification.
8. Installation reports `Compass is installed` only after configuration and Daily Log validate, then offers ordinary actions to scan, discuss a Topic, or review Compass.

### 2. Daily capture

1. Daily Scan displays one bounded connected or synthetic retrieval plan for an absolute local date, sources, limits, retained output, and controls.
2. After retrieval authority, it groups activity only by verified durable source Conversation identity and prepares reviewable Conversation proposals.
3. The user keeps, changes, leaves out, pauses, or cancels each proposal through a progressive interaction.
4. Each proposal may include zero or one existing Topic alignment with concise rationale. `Keep` approves that displayed relationship; Topic creation, lifecycle, merge, and CSP meaning still route to Tracking Topic Interview.
5. Accepted Conversation effects, observed active-author references, approved Conversation-owned `trackingTopicId`, and source-date Daily Log effect form one change handoff to Graph Governor.
6. Daily Scan reports only the post-verification common outcome and accounts for source gaps, rejected proposals, and every intended effect.

### 3. Topic organization

1. Tracking Topic Interview receives direct user intent or a recommendation/handoff that remains non-authoritative.
2. It explores meaning and prepares an exact proposal for Topic wording, lifecycle, Conversation-owned `trackingTopicId`, Topic-owned `cspId`, and applicable Daily Log effects.
3. Merge retains one target Topic, realigns only the approved Conversations, archives the source Topic, and preserves history.
4. The user approves, revises, rejects, pauses, or cancels the exact proposal.
5. The approved request goes to Graph Governor for validation, then authorized application and verification.
6. Tracking Topic Interview reports the verified outcome and returns control to the initiating user workflow.

### 4. Curation review

1. Curator confirms a bounded review scope and inspects accepted graph state only.
2. It derives latest recorded Compass activity from Daily Logs, labels it non-authoritative for source activity, and presents observations, interpretations, and recommendations as distinct information.
3. The user may keep the current state, dismiss or defer a recommendation, or explore it.
4. Topic meaning, lifecycle, consolidation, and relationship recommendations route to Tracking Topic Interview. Stale or completed status comes from user confirmation followed by a fresh exact archival proposal.
5. Integrity questions route to Graph Governor as read-only health requests.
6. Curator never converts a recommendation into a graph change or Daily Log activity.

### 5. Integrity and recovery

1. Graph Governor receives either a shared change handoff or a bounded user-requested health scope.
2. For a change, it returns `valid`, `invalid`, `blocked`, `conflict`, or `indeterminate` against the exact request and source state.
3. Only a `valid` request with continuing authority may proceed to application.
4. Graph Governor verifies every intended object, relationship, managed field, and Daily Log effect after application.
5. During authorized synthetic checks only, failure may enter the disposable-beta recovery protocol. Connected partial or unverifiable effects return `recovery-required` for user-led resolution and block dependent writes.
6. Verified restoration returns `rolled-back`; inability to prove or restore a complete valid state returns `recovery-required` and stops dependent activity.
7. The initiating Skill presents the common terminal outcome without converting uncertainty into success.

## Routing rules

| User intent or observed need | Route | Rule |
| --- | --- | --- |
| Setup or incomplete configuration | Installation Interview | Do not route to routine write flows until required configuration validates. |
| Selected-day Email/Teams review | Daily Scan | Retrieval needs its own displayed authorization. |
| Topic meaning, lifecycle, merge, or relationship | Tracking Topic Interview | Handoff never supplies authority for the decision. |
| Relevance, organization, or attention review | Curator | Recommendations remain non-authoritative. |
| Integrity, conflict, verification, or recovery | Graph Governor | Governor does not choose user meaning. |
| Missing source Conversation identity | Graph Governor guided resolution | Block automatic correlation; never infer identity. |
| Unresolved last activity or staleness automation | No modifying route | Explain the accepted deferral and preserve state. |

## Handoffs and contracts

| From | To | Data or artifact | Success condition |
| --- | --- | --- | --- |
| Perspective Discovery | Installation Interview | Reviewed generic patterns without evidence or real identities | User reviews patterns as optional setup proposals. |
| Installation Interview | Graph Governor | Complete bootstrap request and source-state evidence | Exact configuration, object, relationship, and Daily Log effects receive a decision. |
| Installation Interview | Daily Scan | Accepted graph configuration and visible foundational graph state | Daily Scan can determine timezone and inspect canonical context without hidden profile state. |
| Daily Scan | Tracking Topic Interview | Conversation ID, approved concise context, current alignment, and user's organization request | Receiver obtains enough context but no inherited authority. |
| Daily Scan | Graph Governor | Authorized Conversation, active-author reference, and Daily Log effects | Request conforms to the shared change handoff. |
| Curator | Tracking Topic Interview | User-selected recommendation, object IDs, and concise rationale | Receiver prepares a fresh reviewable proposal. |
| Curator | Graph Governor | User-selected bounded health question | Governor returns a read-only integrity result. |
| Tracking Topic Interview | Graph Governor | Authorized Topic, canonical relationship, and Daily Log effects | Request accounts for every affected object and relationship. |
| Graph Governor | Initiating Skill | Validation or common outcome, effect accounting, and actionable next step | Initiating Skill can report truthfully without reinterpreting the result. |

Every mutating handoff includes `requestId`, `initiatingSkill`, `authoritySource`, `operationType`, `targetObjects`, `expectedEffects`, `sourceState`, `evidenceReferences` when needed, `approvalReference`, and `correlationId`. Daily Log data follows `SC-LOG-007`. Unknown or extra context is not silently treated as authority.

## Guardrails and approvals

- Retrieval, graph inspection, proposal approval, and graph modification are distinct authorities.
- Topic creation, merge, alignment, unalignment, archival, reactivation, CSP alignment, and Conversation deletion require exact user authority.
- A materially changed target, wording, relationship, or effect invalidates prior approval and returns to review.
- Each canonical relationship has one owner; reverse lists are derived.
- Every durable graph update includes its Daily Log effect in the same declared write set.
- User-authored content and unknown safe frontmatter remain preserved.
- No Skill or this Orchestration may claim success before Graph Governor post-write verification.
- The synthetic recovery protocol never applies to a personal or production graph.

## Failure and fallback behavior

- **Missing installation/configuration:** route to Installation Interview or offer read-only inspection; do not attempt a date-dependent write.
- **Permission or source unavailable:** constrain the current flow, disclose the gap, and preserve already reviewed choices.
- **Protected installation input:** preserve the source's classification and platform controls, minimize retrieval, treat content as evidence, and continue to user review and post-retrieval write preflight.
- **Plain-text write refused:** report `write-blocked` / `blocked` with the verbatim platform reason and probe cleanup state; do not create managed structure, weaken source protection, blame the valid source, or substitute labelable container formats.
- **Identity ambiguous:** block the affected object; guide verification without similarity-based substitution.
- **Authority missing or stale:** return to the exact proposal review; do not silently reprompt as if approval persisted.
- **Source-state conflict:** preserve both current state and proposal context, report `conflict`, and ask the accountable Skill to prepare a fresh proposal.
- **Partial application:** account for every effect and enter only the authorized synthetic recovery route; otherwise report `recovery-required`.
- **Downstream Skill unavailable:** keep the initiating result proposed or deferred and explain which action remains unapplied.
- **User pauses or cancels:** stop new retrieval and effects, preserve authoritative prior state, and report what was and was not completed.
- **Host control inaccessible:** provide an equivalent typed conversational path; never trap completion behind an inaccessible card control.

## Terminal reporting

The initiating Skill reports one common terminal outcome: `proposed`, `rejected`, `committed`, `committed-with-warnings`, `blocked`, `conflict`, `rolled-back`, `recovery-required`, or `failed`. Read-only flows may additionally use their accepted `empty` or `cancelled` interaction outcome while clearly stating `External changes: 0`.

The report identifies scope, unavailable dependencies, intended effects, completed effects, unapplied effects, rolled-back effects, uncertain effects, preserved user content, and the next actionable choice as applicable. It does not expose raw evidence, secrets, or unrelated graph content.

## Validation scenarios

- Surface probe S1: Installation progressive interaction and typed fallback.
- Surface probe S2: Daily Scan bounded retrieval and proposal review.
- Surface probe S3: Cross-Skill authority, routing, and honest blocked outcome.
- Critical operation C1: Durable Email/Teams Conversation identity.
- Critical operation C2: Synthetic multi-object write, Daily Log effect, conflict, and recovery.
- Critical operation C3: Privacy-minimized authority handoff.
- Integrated rehearsal: installation through daily capture, Topic organization, curation, Governor verification, and external inspection on one disposable graph.

These labels derive from the [compact full-beta strategy](../../docs/test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md). This definition does not authorize their execution.

## Change impact

A change to routing, handoff fields, approval renewal, common outcomes, Daily Log coupling, recovery, or a Skill responsibility requires impact review against all five Skill specifications and affected compact-strategy checks. A presentation-only change requires rerunning only an affected surface probe unless it changes authority or retained state. Completed evidence remains attached to the exact versions tested.

## Acceptance boundary

Version `0.1-beta-candidate` is the accepted Compass lifecycle coordination definition and closes Slice C. Acceptance does not authorize Skill or Orchestration implementation, package creation, connected access, graph writes, test execution, beta launch, deployment, or release. Slice D implementation requires separate explicit authorization.