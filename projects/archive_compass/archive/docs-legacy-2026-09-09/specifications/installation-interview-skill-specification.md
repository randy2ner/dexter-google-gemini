# Specification: Installation Interview behavior

## Document control

- **Status:** Accepted responsibility specification
- **Version:** 0.7-production-test-responsibility
- **Owner:** User / product owner
- **Created:** 2026-09-02
- **Last updated:** 2026-09-09
- **Governed by:** [Compass Charter](../charter/compass-vision-and-scope-charter.md); [Compass PRD](../requirements/compass-product-requirements.md); [Shared Contracts 0.8](compass-shared-contracts-specification.md); [Graph Schema 0.7](compass-graph-schema-specification.md)
- **Applies to Skills:** Compass Installation Interview
- **Implementation authority:** Production-content testing and native Work IQ source, packaging, and static validation authorized by the user on 2026-09-08

## Purpose and owned outcome

Installation Interview guides the user from an unconfigured workspace to one reviewed Compass foundation. It owns setup conversation, graph configuration, foundational object proposals, and the validated bootstrap handoff.

A completed installation contains a stable graph ID, confirmed IANA timezone, accepted foundational CSPs, Tracking Topics, and People that the user chose to create, and the installation-date Daily Log. Completion means every authorized effect passed Graph Governor pre-write validation and post-write verification. An empty foundational set is valid when the user prefers to begin without one.

The natural first-run entry is a request such as `Help me install Compass`. Installation owns creating a user-confirmed `Compass` folder in OneDrive Documents or resolving one existing OneDrive folder. It must not require the user to pre-create, attach, or describe a graph before the interview begins.

The accepted [Perspective Discovery slice](installation-interview-perspective-discovery-skill-specification.md) is an optional read-only input. It does not install Compass or authorize graph content.

## Inputs, outputs, and interfaces

| Element | Contract |
| --- | --- |
| User setup answers | The user's own role language, priorities, customer context, exclusions, and preferred initial organization. |
| Existing workspace state | Bounded inspection needed to determine whether configuration or managed objects already exist; user content remains authoritative. |
| Optional Perspective Discovery handoff | Reviewed generic patterns only; never raw evidence, real identities, or automatic graph authority. |
| Bootstrap proposal | Exact configuration, object, relationship, and Daily Log effects shown in user-facing language before approval. |
| Change handoff | Shared-contract request with initiating Skill/version, authority, expected effects, source-state evidence, approval reference, operation ID, and correlation ID. |
| Installation result | Common terminal outcome plus completed, unapplied, rolled-back, uncertain, and preserved effects as applicable. |

## Required behavior

| ID | Requirement | Source | Acceptance criterion |
| --- | --- | --- | --- |
| INST-001 | Establish `_compass/config.yaml` with one stable graph UUID and confirmed IANA timezone. | `PR-GRAPH-001`, `PR-SAFE-001` | Setup is not complete until configuration validates. |
| INST-002 | Interpret direct input, accepted graph context, and authorized Work IQ into editable foundational artifact suggestions. | `PR-AUTH-001`, `PR-INT-002` | Compass proposes useful CSP, Topic, and complete-name Person content and relationships in ordinary language; the user confirms or revises every created object. |
| INST-003 | Preserve canonical relationship ownership and accepted object fields. | `PR-PORT-001`, `PR-GRAPH-001` | Topics own `cspId`, `participantIds`, and `excludedParticipantIds`; no reverse authoritative lists are created. |
| INST-004 | Include the installation-date Daily Log in the bootstrap write set. | `PR-GRAPH-001`, `PR-TRUTH-001` | Configuration and Daily Log validate before completion is reported. |
| INST-005 | Submit the complete write set to Graph Governor before application and after attempted application. | `PR-SAFE-001`, `PR-TRUTH-001` | No successful outcome precedes post-write verification. |
| INST-006 | Detect an existing or partial installation and offer resume, inspect, or cancel rather than overwrite. | `PR-HIST-001`, `PR-SAFE-001` | Existing managed and user-authored content remains preserved. |
| INST-007 | Keep routine evidence discovery in Daily Scan. | Accepted Slice B responsibility boundary | Installation performs no broad daily Email or Teams scan. |
| INST-008 | Accept user-selected classified or sensitivity-labeled Microsoft 365 files and Loop pages as setup evidence through the signed-in Cowork context. | `PR-PRIV-001`, `PR-AUTH-001` | Classification alone does not block installation; source selection and purpose are confirmed before bounded retrieval. |
| INST-009 | Preserve platform-enforced source protection and minimize retained content. | `PR-PRIV-001`, `PR-SAFE-001` | Installation does not remove, downgrade, relabel, export, or bypass protection and retains only user-approved derived knowledge, not raw classified source bodies or label metadata. |
| INST-010 | Use the approved bootstrap rather than a disposable file to verify write capability. | `PR-SAFE-001`, `PR-TRUTH-001` | Installation creates no probe; a refusal before any effect returns `write-blocked` / `blocked`, while a completed or uncertain effect returns `recovery-required`. |
| INST-011 | Apply an approved bootstrap config-first. | `PR-SAFE-001`, `PR-TRUTH-001` | `_compass/config.yaml` is the first write and is verified before remaining managed folders and objects are created. |
| INST-012 | Confirm incomplete Person names and initial Topic participation. | `SC-ID-006`, `SC-KNOW-010` | A first-name-only answer prompts for last name and identity; initial Topic participant links are separately reviewable and exclusions begin empty unless the user explicitly directs otherwise. |
| INST-013 | Establish one explicit attention state for every foundational Topic. | `PR-ATTN-001`, `SC-KNOW-012` | The user chooses `action`, `waiting`, or `observing`; Installation does not infer or default the value. |
| INST-014 | Exclude UPN from foundational Person collection and persistence. | `PR-PRIV-002`, `SC-ID-007` | Installation never requests, infers, retrieves for retention, adds, or updates `userPrincipalName`; existing unmanaged values remain unchanged without separate cleanup authority. |
| INST-017 | Retain reviewed normalized Person email addresses when known. | `PR-PERSON-001`, `SC-ID-007` | User-supplied or authorized Work IQ addresses appear in the Person proposal and handoff but never replace complete name or stable Compass ID. |
| INST-018 | Address approved OneDrive graph writes by graph-root-relative path. | `SC-WRITE-004` | Configuration and remaining files are created or replaced through their displayed relative paths, never by OneDrive item ID; folder resolution remains a separate operation. |
| INST-015 | Keep optional Topic narrative and review metadata outside bootstrap while preserving user intent for later refinement. | `PR-NARR-001`, `PR-HIGHLIGHT-001`, `SC-KNOW-013` | Installation does not infer or write Topic narrative, `tags`, or `reviewBullet`; offered intent routes to Tracking Topic Interview only after verified setup. |
| INST-016 | Use native Work IQ for user-authorized production setup discovery without artificial capability reduction. | `PR-WIQ-001`, `SC-EVID-001` | Relevant Cowork-exposed source types and continuation are used without arbitrary numeric caps or sample substitution; incomplete coverage is disclosed and all derived graph content remains a proposal. |

## Human interaction

Installation should feel like a short working conversation, not a configuration wizard or organizational interrogation. Ask one meaningful question at a time, reuse the user's language, explain visible consequences, and provide typed paths for every required choice. Offer useful defaults as editable proposals and allow pause, resume, skip, or cancel without claiming completion.

Technical fields stay behind plain-language explanations unless the user asks for detail. Approval summarizes durable effects by recognizable object and relationship, not by file mechanics alone.

## Authority, safety, and privacy boundaries

- Setup answers are direct user authority only for the exact displayed effects derived from them.
- Perspective Discovery patterns require installation review before becoming graph proposals.
- Installation may create or update configuration and user-approved foundational objects; it may not infer customers, priorities, People, Topics, or CSP relationships from unreviewed evidence.
- A material change after approval requires renewed approval.
- All durable changes include the required Daily Log effect and Graph Governor validation.
- Existing valid direct user edits and unmanaged content are preserved.
- Source classification does not reduce user authority or make the source invalid. Cowork and Microsoft 365 protection continue to govern source access and handling.
- Installation does not change the graph schema to Office or PDF merely in response to a source label; storage-format evolution requires a separate product decision.

## Handoffs and responsibility boundary

- **To Graph Governor:** one complete bootstrap request; Installation supplies meaning and authority, while Graph Governor supplies structural validation, conflict checks, and verification.
- **To Daily Scan:** validated graph configuration and the accepted foundational context available in the graph. No hidden profile or raw setup transcript is handed off.
- **To Tracking Topic Interview:** user requests that require deeper Topic creation, merge, realignment, archival, or reactivation outside the bounded initial proposal.
- **From Perspective Discovery:** optional minimized patterns that remain proposals until the user applies them during installation.

Installation does not own routine evidence retrieval, ongoing Conversation capture, Topic maintenance after bootstrap, curation, graph-health interpretation, or independent repair.

## Failure, partial, blocked, and cancellation behavior

- Missing or invalid timezone blocks date-dependent bootstrap effects; setup remains incomplete.
- Existing conflicting configuration or managed objects produce `conflict` or `blocked`, not replacement.
- An observed DLP, sensitivity-label, or protection-policy refusal of the first approved bootstrap write produces setup classification `write-blocked` and terminal outcome `blocked`, not `failed`, when no effect occurred. Classification alone does not produce that outcome.
- A blocked result reports the platform reason, graph root, zero completed effects, and whether only an empty user-confirmed root may remain. A completed or uncertain configuration effect is `recovery-required`.
- A blocked result does not tell the user to declassify or avoid the valid source. Retry requires an authorized platform or tenant-policy path that preserves source protection.
- A declined proposal produces `rejected` with no effects from that proposal.
- Cancellation preserves prior state and reports any retrieval or effects already attempted.
- Synthetic partial application may follow disposable-beta recovery. Connected partial application stops as `recovery-required` for user-led resolution and never becomes generic success.

## Edge cases and unresolved questions

- Dogfood bootstrap may target one user-selected connected graph. The candidate must carry enough normative schema to create a conformant graph in a clean session.
- Standalone Activity objects are not part of schema version 2; installation activity is represented in the Daily Log.
- Source Conversation identity and last-activity semantics are not installation decisions.

## Traceability and evaluation

- **Test plan:** [Compact full-beta strategy](../test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md)
- **Planned checks:** S1 installation interaction probe, C2 write/recovery check, and the integrated synthetic rehearsal
- **Prior input:** [Prior Skill static review](../findings/2026-08-28-prior-skill-static-review.md)

## Revision history

| Version | Date | Change | Motivation and impact |
| --- | --- | --- | --- |
| 0.1-beta-responsibility | 2026-09-02 | Defines complete Installation ownership while retaining Perspective Discovery as an optional bounded input. | Accepted Slice B set and beta baseline; supersedes no source or tested specimen. |
| 0.2.2-dogfood-responsibility | 2026-09-04 | Prohibits protected document ingestion, adds representative plain-text preflight, and orders bootstrap config-first. | First natural dogfood run was blocked by a label-required session after a protected Loop page entered the conversation and left empty managed folders. |
| 0.2.3-dogfood-responsibility | 2026-09-04 | Restores classified Microsoft 365 files as valid inputs while preserving protection, bounded derivation, post-retrieval preflight, and config-first ordering. | Product owner rejected the label-free avoidance approach and reaffirmed Copilot-orchestrated protected operation. |
| 0.3-participant-management-responsibility | 2026-09-06 | Requires complete Person names and permits reviewed initial Topic participant state under schema version 2. | Product-owner participant-management decision. |
| 0.4-attention-state-responsibility | 2026-09-06 | Requires an explicit user-selected attention state for every foundational Topic. | Product-owner attention-state decision. |
| 0.5-person-data-minimization-responsibility | 2026-09-06 | Removes Person UPN from setup collection, proposals, and handoffs. | Product-owner Person UPN removal decision. |
| 0.8-first-experience-responsibility | 2026-09-09 | Removes disposable write probing, accepts reviewed Person emails, and requires Work IQ-grounded editable artifact suggestions. | First artifact-building experience feedback. |

## Acceptance boundary

Acceptance would establish Installation Interview's responsibility boundary for compatible Skill and Orchestration design. It would not authorize Skill source implementation, package creation, evidence retrieval, graph writes, testing, deployment, or release.