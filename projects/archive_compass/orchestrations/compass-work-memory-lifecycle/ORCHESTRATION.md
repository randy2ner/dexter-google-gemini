# Orchestration: Compass work-memory lifecycle

## Identity

- **Name:** compass-work-memory-lifecycle
- **Version:** 0.7.0-production-test-candidate
- **Owner:** User / product owner
- **Status:** accepted definition
- **Created:** 2026-09-02
- **Last updated:** 2026-09-08
- **Implementation authority:** Production-content testing and native Work IQ source, orchestration, packaging, and static validation authorized by the user on 2026-09-08

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
| [Compass Specification](../../docs/SPECIFICATION.md) | Product and behavior contract | `1.0` | Yes | Stop behavior not supported by an accepted requirement or responsibility. |
| User | Human authority | Current interaction | Yes for consequential meaning | Proposal remains proposed, rejected, cancelled, or blocked. |

## Interaction continuity

Compass presents one current purpose, one current accountable Skill, and one next meaningful user decision. Internal handoffs should not force the user to restate accepted context or expose protocol mechanics.

Every transition must:

1. name the practical reason for the transition when it is not obvious;
2. carry only the accepted context needed by the receiving Skill;
3. preserve proposal versus authoritative-state distinctions;
4. retain one correlation ID across validation, application, recovery, and reporting; and
5. provide typed continue, change, back, pause, or cancel paths where they are meaningful; and
6. omit Person UPN from proposals and handoffs while preserving any pre-existing value as unmanaged content pending separate cleanup authority; and
7. carry reviewed normalized Person email addresses when supplied or exposed for the authorized purpose, without treating them as graph identity.

An initiating Skill remains responsible for the user-facing outcome of its request. Graph Governor may explain a block or recovery state directly, but the Orchestration returns control to the initiating Skill with that result rather than ending in an unexplained subsystem response.

## Flow

### 1. Installation and resume

1. `Help me install Compass` routes directly to Installation Interview, which offers to create a user-confirmed OneDrive Documents `Compass` folder or use one existing folder.
2. Installation Interview inspects only the selected folder to distinguish new, resumable, configured, conflicting, or inaccessible setup.
3. For new setup, it collects direct user context and may use all relevant native Work IQ capabilities Cowork exposes for the user-authorized production setup purpose. It attempts complete relevant coverage without arbitrary numeric caps or sample substitution. Classification alone is not a stop condition; source protection remains platform-enforced and only minimized user-approved derivations may enter the graph.
4. It interprets direct answers, accepted graph context, and authorized Work IQ into its best useful editable suggestion for configuration, foundational objects, Person emails, relationships, and installation-date Daily Log.
5. It prepares one exact bootstrap proposal and asks follow-up questions only for material ambiguity that cannot be represented safely in that suggestion.
6. The user approves, changes, skips optional objects, or cancels.
7. An approved proposal goes to Graph Governor for pre-write validation, config-first authorized application, and post-write verification. The verified configuration write is the capability check; no disposable probe or delete is used.
8. Installation reports `Compass is installed` only after configuration and Daily Log validate, then offers ordinary actions to scan, discuss a Topic, or review Compass.

### 2. Daily capture

1. Daily Scan displays one production retrieval plan for an absolute local period, purpose, relevant work scope, retained output, and controls. It uses all relevant Work IQ sources and continuation capabilities Cowork exposes without arbitrary numeric caps or sample substitution.
2. After retrieval authority, it groups activity only by verified durable source Conversation identity and prepares its best useful editable Conversation proposals with qualifying participants and reviewed normalized emails when known. A first-name-only mention pauses the affected identity decision until the user confirms a last name and existing-or-new Person binding.
3. The user keeps, changes, leaves out, pauses, or cancels each proposal through a progressive interaction.
4. Each proposal contains one explicit Topic disposition: a valid existing Topic ID or `parking-lot`. `Keep` approves that displayed relationship; Topic creation, lifecycle, merge, CSP meaning, and direct Topic participant management still route to Tracking Topic Interview.
5. Accepted Conversation effects, complete-name participant references without UPN, approved Conversation-owned `trackingTopicId`, deterministic non-excluded Topic participant funnel effects, and source-date Daily Log effect form one change handoff to Graph Governor.
6. Daily Scan reports only the post-verification common outcome and accounts for source gaps, rejected proposals, and every intended effect.
7. When the user offers detailed troubleshooting content or authorizes it in the retrieval purpose, Daily Scan may prepare a minimized narrative candidate and route it to Tracking Topic Interview without Topic-write authority.

### 3. Topic organization

1. Tracking Topic Interview receives direct user intent or a recommendation/handoff that remains non-authoritative and may offer native Work IQ grounding for an explicitly authorized Topic purpose. It interprets that context into its best useful editable Topic artifact suggestion before requesting confirmation.
2. It explores meaning and prepares an exact proposal for Topic wording and narrative, optional `tags` and `reviewBullet`, lifecycle, Conversation-owned `trackingTopicId`, Topic-owned `cspId`, Topic participant add/remove/re-add, and applicable Daily Log effects.
3. Participant removal moves the Person ID from Topic `participantIds` to `excludedParticipantIds`; explicit re-add reverses both. Conversation lifecycle or reassignment never prunes Topic participants.
4. Merge retains one target Topic with one explicit `attentionState`, realigns only the approved Conversations, presents final participant and exclusion effects, archives each source Topic with its retained attention state and explicit user-approved boolean success value, and preserves history.
5. The user approves, revises, rejects, pauses, or cancels the exact proposal.
6. The approved request goes to Graph Governor for validation, then authorized application and verification.
7. Tracking Topic Interview reports the verified outcome and returns control to the initiating user workflow.
8. Follow-up ideas retained outside the archived Topic scope do not trigger another Topic prompt or handoff unless the user initiates it.

### 4. Curation review

1. Curator confirms a review purpose and scope, inspects accepted graph state, and may use explicitly authorized native Work IQ evidence as current non-authoritative context.
2. It derives latest recorded Compass activity from Daily Logs, labels it non-authoritative for source activity, and presents observations, interpretations, and recommendations as distinct information.
3. It emits exactly one distinct bullet for each in-scope Topic with `reviewBullet: true`; solved HPI bullets may summarize accepted outcome, transferable lesson, and contribution without reopening the incident.
4. The user may keep the current state, dismiss or defer a recommendation, or explore it.
5. Topic meaning, lifecycle, consolidation, and relationship recommendations route to Tracking Topic Interview. Stale or completed status comes from user confirmation followed by a fresh exact archival proposal that asks whether the Topic succeeded and includes the resulting boolean value.
6. Integrity questions route to Graph Governor as read-only health requests.
7. Curator never converts a recommendation into a graph change or Daily Log activity.

### 5. Integrity and recovery

1. Graph Governor receives either a shared change handoff or a bounded user-requested health scope.
2. For a change, it returns `valid`, `invalid`, `blocked`, `conflict`, or `indeterminate` against the exact request and source state.
3. Only a `valid` request with continuing authority may proceed to application.
4. Graph Governor verifies every intended object, relationship, managed field, and Daily Log effect after application.
5. Production partial or unverifiable effects return `recovery-required` for user-led resolution and block dependent writes. No Skill performs automatic rollback or repair.
6. The initiating Skill presents the common terminal outcome without converting uncertainty into success.

## Routing rules

| User intent or observed need | Route | Rule |
| --- | --- | --- |
| Setup or incomplete configuration | Installation Interview | Do not route to routine write flows until required configuration validates. |
| Selected-period Microsoft 365 work review | Daily Scan | Native Work IQ retrieval needs its own displayed purpose and authorization. |
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
| Daily Scan | Tracking Topic Interview | Conversation ID, approved concise context, optional minimized narrative candidate, current disposition, and user's organization, participant-management, or narrative request | Receiver obtains enough context but no inherited Topic authority. |
| Daily Scan | Graph Governor | Authorized Conversation participant, explicit Topic disposition, deterministic Topic funnel, and Daily Log effects | Request conforms to the shared change handoff. |
| Curator | Tracking Topic Interview | User-selected recommendation, object IDs, and concise rationale | Receiver prepares a fresh reviewable proposal. |
| Curator | Graph Governor | User-selected bounded health question | Governor returns a read-only integrity result. |
| Tracking Topic Interview | Graph Governor | Authorized Topic, canonical relationship, participant/exclusion, and Daily Log effects | Request accounts for every affected object and relationship. |
| Graph Governor | Initiating Skill | Validation or common outcome, effect accounting, and actionable next step | Initiating Skill can report truthfully without reinterpreting the result. |

Every mutating handoff includes `requestId`, `initiatingSkill`, `authoritySource`, `operationType`, `targetObjects`, `expectedEffects`, `sourceState`, `evidenceReferences` when needed, `approvalReference`, and `correlationId`. Daily Log data follows `SC-LOG-007`. Unknown or extra context is not silently treated as authority.

## Guardrails and approvals

- Retrieval, graph inspection, proposal approval, and graph modification are distinct authorities.
- Topic creation, attention-state change, merge, alignment, Parking Lot movement, archival, reactivation, CSP alignment, participant add/remove/re-add, and Conversation deletion require exact user authority. Every Topic has one `attentionState`: `action`, `waiting`, or `observing`. Archival retains it and includes `success: true` or `success: false`; reactivation removes success and confirms or changes attention state.
- Every Conversation stores a valid Topic ID or `parking-lot`; absence, null, and empty values are invalid.
- Every participant resolves to a Person with meaningful first and last names.
- Reviewed normalized Person email addresses are retained when known; they do not replace stable Compass identity or authorize UPN collection.
- Deterministic Conversation participant funneling honors Topic exclusions; Conversation lifecycle changes never prune Topic participants.
- A materially changed target, wording, relationship, or effect invalidates prior approval and returns to review.
- Each canonical relationship has one owner; reverse lists are derived.
- Every durable graph update includes its Daily Log effect in the same declared write set.
- Every created or replaced OneDrive graph file is addressed by its declared graph-root-relative path, never by OneDrive item ID. Graph-root resolution and source Conversation identity remain separate concerns.
- User-authored content and unknown safe frontmatter remain preserved.
- No Skill or this Orchestration may claim success before Graph Governor post-write verification.
- No production-test Skill substitutes sample, fictional, fixture, or synthetic evidence, imposes arbitrary Work IQ result caps, or silently narrows relevant Cowork-exposed source types.
- Production graph content is not exported or submitted for model training without a separate explicit user-authorized purpose and destination.

## Failure and fallback behavior

- **Missing installation/configuration:** route to Installation Interview or offer read-only inspection; do not attempt a date-dependent write.
- **Permission or source unavailable:** constrain the current flow, disclose the gap, and preserve already reviewed choices.
- **Protected installation input:** preserve the source's classification and platform controls, minimize retrieval, treat content as evidence, and continue to user review and approved config-first application.
- **First approved write refused:** report `write-blocked` / `blocked` with the verbatim platform reason when no effect occurred; report `recovery-required` when the configuration effect is completed or uncertain. Do not continue writing, weaken source protection, blame the valid source, or substitute labelable container formats.
- **Identity ambiguous:** block the affected object; for a first-name-only mention, ask for the last name and existing-or-new Person binding without similarity-based substitution.
- **Authority missing or stale:** return to the exact proposal review; do not silently reprompt as if approval persisted.
- **Source-state conflict:** preserve both current state and proposal context, report `conflict`, and ask the accountable Skill to prepare a fresh proposal.
- **Partial application:** account for every effect, report `recovery-required`, and require user-led resolution.
- **Downstream Skill unavailable:** keep the initiating result proposed or deferred and explain which action remains unapplied.
- **User pauses or cancels:** stop new retrieval and effects, preserve authoritative prior state, and report what was and was not completed.
- **Host control inaccessible:** provide an equivalent typed conversational path; never trap completion behind an inaccessible card control.

## Terminal reporting

The initiating Skill reports one common terminal outcome: `proposed`, `rejected`, `committed`, `committed-with-warnings`, `blocked`, `conflict`, `rolled-back`, `recovery-required`, or `failed`. Read-only flows may additionally use their accepted `empty` or `cancelled` interaction outcome while clearly stating `External changes: 0`.

The report identifies scope, unavailable dependencies, intended effects, completed effects, unapplied effects, rolled-back effects, uncertain effects, preserved user content, and the next actionable choice as applicable. It does not expose raw evidence, secrets, or unrelated graph content.

## Validation

- Surface probe S1: Installation progressive interaction and typed fallback.
- Surface probe S2: Daily Scan bounded retrieval and proposal review.
- Surface probe S3: Cross-Skill authority, routing, and honest blocked outcome.
- Critical operation C1: Durable Email/Teams Conversation identity.
- Critical operation C2: Synthetic multi-object write, Daily Log effect, conflict, and recovery.
- Critical operation C3: Privacy-minimized authority handoff.
- Integrated rehearsal: installation through daily capture, Topic organization, curation, Governor verification, and external inspection on one disposable graph.

These checks are maintained in the [Compass Test Plan](../../docs/TEST-PLAN.md). This definition does not authorize their execution.

## Change impact

A change to routing, handoff fields, approval renewal, common outcomes, Daily Log coupling, recovery, or a Skill responsibility requires updating the Specification and affected Test Plan cases. A presentation-only change requires rerunning only the affected case unless it changes authority or retained state. Dated observations remain attached to the exact versions tested.

## Acceptance boundary

Version `0.1-beta-candidate` is the accepted Compass lifecycle coordination definition and closes Slice C. Acceptance does not authorize Skill or Orchestration implementation, package creation, connected access, graph writes, test execution, beta launch, deployment, or release. Slice D implementation requires separate explicit authorization.