# Compass Shared Contracts Specification

## Document control

- **Status:** Accepted beta baseline
- **Project:** Compass
- **Version:** 0.3-beta-baseline
- **Created:** 2026-08-28
- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Approval:** Accepted by user on 2026-09-02
- **Implementation authority:** None granted by this specification

## 1. Purpose

This document defines the candidate agreements that allow Compass Skills to work on one knowledge graph without inventing incompatible meanings, authority rules, handoffs, or outcomes.

A shared contract states what every participating Skill must honor. It does not prescribe the complete internal design of a Skill. Individual Skill specifications may add stricter behavior but must not weaken an accepted shared contract.

This accepted beta baseline is deliberately smaller than the imported technical specification. It establishes the minimum cross-Skill rules needed to define compatible Skill responsibilities and one Orchestration. Detailed storage APIs, production transaction design, and package mechanics remain separate decisions.

## 2. Basis and authority

The current [Compass Vision and Scope Charter](../charter/compass-vision-and-scope-charter.md) is the governing source for this specification.

Files in the charter's [`source-material/`](../charter/source-material/) directory describe a similar prior effort. They may contribute useful examples, risks, or design candidates, but they do not define the new Compass project and have no decision authority. Nothing from those files becomes a Compass requirement or Skill responsibility unless the user explicitly reaffirms it in a current project record.

Where source material differs from the charter or a current user decision, the charter and current decision govern. Where the charter remains provisional, this document records the uncertainty instead of resolving it from prior-project material.

## 3. Contract principles

These four confirmed charter boundaries govern every contract in this specification:

1. **User-approved authority:** AI evidence or interpretation does not become trusted knowledge without user authority.
2. **Inspectable, portable data:** Authoritative knowledge remains readable and editable outside Compass.
3. **Preserved history:** Normal lifecycle behavior does not destructively erase retained knowledge. Staleness alone never authorizes deletion; any permitted deletion is a separate, explicit user-approved action.
4. **No false success:** Partial, uncertain, blocked, or failed actions are reported honestly.

The following additional principles are part of the accepted beta baseline:

- Skills use shared meanings for graph objects, identifiers, relationships, authority, and outcomes.
- A Skill may modify only the objects and relationships assigned to its role.
- Ambiguous identity, authority, or structural intent stops the affected modification.
- Valid direct user edits are authoritative and must not be silently overwritten.
- Cross-Skill handoffs carry structured intent and provenance, not hidden assumptions.
- The Graph Governor evaluates shared rules consistently; it does not acquire authority to make ambiguous user decisions.
- Every authorized graph update is reflected in the appropriate Daily Log without making the Daily Log a second source of relationship truth.
- Daily Log maintenance preserves user-authored content and never converts provisional evidence into authoritative graph activity.

## 4. Shared vocabulary

| Term | Candidate shared meaning |
| --- | --- |
| **Evidence** | Authorized Microsoft 365 activity or another identified source used to support a proposal. Evidence of activity is not automatically authoritative graph knowledge. |
| **Conversation** | Durable work memory organized around one source-system Conversation ID and grounded in the email or chat activity under that durable umbrella. |
| **Tracking Topic** | A user-managed durable concept that organizes related Conversations across time. |
| **CSP** | A Customer Success Plan representing durable customer outcomes, strategic objectives, or business priorities. |
| **Person** | A durable identity that provides relationship context and may participate in Conversations or contribute Evidence. |
| **Daily Log** | A user-local-date index of authorized graph activity. It provides derived navigation to affected graph objects and is not an authoritative relationship owner. |
| **Parking Lot** | A derived view of Conversations not aligned to a Tracking Topic; it is not a stored graph object. |
| **Proposal** | A reviewable candidate change produced by Compass that has not yet received the required user authority. |
| **Authoritative knowledge** | Graph content established through valid direct user authorship or the required user approval. |
| **Deterministic action** | An action for which the accepted rules permit exactly one valid result without choosing among plausible user meanings. |
| **Touched closure** | The changed objects plus the relationships and referenced objects that must be checked to determine whether the change is valid. |

## 5. Knowledge relationship contract

The candidate alignment model is:

```text
Evidence
    ↓ grounds
Conversation -- zero-or-one --> Tracking Topic -- zero-or-one --> CSP
    ↑
People participate in or provide relationship context
```

### SC-KNOW-001 — Conversation alignment

A Conversation may align to zero or one Tracking Topic at a time. The Conversation owns this authoritative relationship by storing the aligned Tracking Topic ID. A Tracking Topic's Conversation list is derived by querying Conversations rather than storing a second authoritative membership list. No Skill may create multiple simultaneous authoritative Topic alignments for one Conversation.

### SC-KNOW-002 — Topic alignment

A Tracking Topic may align to zero or one CSP at a time. The Tracking Topic owns this authoritative relationship by storing the aligned CSP ID. A CSP's Topic list is derived by querying Tracking Topics rather than storing a second authoritative list. A Topic without a CSP remains valid unless a later accepted requirement says otherwise.

### SC-KNOW-003 — Parking Lot projection

A Conversation with no Tracking Topic alignment appears in the Parking Lot. Skills must not create a Parking Lot object, folder-owned relationship, sentinel Topic, or second source of truth to represent this state.

### SC-KNOW-004 — Evidence grounding

A Conversation records enough provenance to identify why it exists without storing raw transcripts or unrelated source content by default. Missing or inaccessible evidence must be disclosed rather than reconstructed as fact.

### SC-KNOW-005 — Relationship ownership

Each authoritative relationship has one canonical owner or representation. Reverse relationships are derived rather than independently maintained unless an accepted specification explicitly establishes another design.

**Confirmed:** The Tracking Topic owns its zero-or-one CSP relationship. The exact frontmatter key remains a schema decision.

**Confirmed:** The Conversation owns its zero-or-one Tracking Topic relationship. Topic reports and Topic Interview context derive aligned Conversations by querying that relationship. The exact frontmatter key remains a schema decision.

### SC-KNOW-006 — Conversation staleness and deletion

Conversation staleness is a derived condition based on an accepted last-activity and retention rule. It may cause Compass to surface a Conversation for review, but it does not automatically change or delete the Conversation.

A stale Conversation may be deleted only after the user reviews the identified Conversation, understands the historical and relationship effects, and explicitly approves that deletion. Graph Governor must validate the exact deletion and affected relationships before application and verify the result afterward. Batch approval must account for each Conversation individually or identify an equally explicit bounded set.

### SC-KNOW-007 — Tracking Topic permanence

A Tracking Topic is never deleted. Its lifecycle state is `active` or `archived`, and it may transition between those states through an authorized operation. Archival preserves the Topic, its history, and its relationships. A stale Topic may be recommended for archival but staleness alone does not change its state.

### SC-KNOW-008 — Daily Log derivation

A Daily Log summarizes authorized graph activity for one user-local calendar date. Its managed entries link to affected graph objects by stable Compass ID. The objects and their owned relationship fields remain authoritative; a Daily Log entry does not create, change, or prove an object relationship.

Because its managed index is derived, Compass may rebuild that index from accepted graph and operation evidence. User-authored content outside defined managed sections remains authoritative and must be preserved.

## 6. Identity contract

### SC-ID-001 — Source Conversation ID is structural truth

Every chat or email Conversation is organized by a durable source-system Conversation ID. That ID is the structural truth that determines which chat messages or email items belong under one Conversation umbrella.

- For chat, participant additions or removals do not by themselves create a new Compass Conversation when the source Chat ID remains the same.
- For email, replies, forwards, and branches belong to the same Compass Conversation when the source Email Conversation ID places them under the same durable umbrella, even when the messages do not form one linear reply sequence.
- Activity with the same source Conversation ID updates the existing Conversation.
- Activity with a different source Conversation ID creates or proposes a distinct Conversation rather than being merged by title, participants, timing, or semantic similarity alone.

This is an accepted conceptual rule from the user. The exact Microsoft 365 fields and their observed durability must still be verified in the target Cowork and Work IQ environment before implementation claims compatibility.

### SC-ID-002 — Stable Compass object identity

Every durable graph object also requires a stable graph identifier that does not change when its display title, filename, or location changes. For a Conversation, this object identifier must preserve an explicit mapping to its governing source Conversation ID. Whether Compass reuses a safely representable source ID or stores a separate internal ID is a later schema decision; either choice must preserve the source ID as the correlation authority.

### SC-ID-003 — Display labels are not identity

Titles, filenames, wiki-link labels, names, and generated summaries must not be used as the sole basis for object identity.

### SC-ID-004 — Ambiguous identity fails closed

When Compass cannot determine whether activity belongs to an existing object, it must not silently merge, suppress, replace, or duplicate the object. It must leave the graph unchanged for that decision and request a user disposition or report the unresolved ambiguity.

A missing source Conversation ID is treated as an exceptional integrity problem, not a normal alternate capture mode. Compass must not invent an ID or correlate the activity from subject, participants, timing, or semantic similarity.

### SC-ID-005 — Item identity, Conversation identity, and graph identity remain distinguishable

Compass must preserve the distinction between:

- an individual email, chat message, meeting, file, or other evidence-item ID;
- the durable source Conversation ID that groups those items under one chat or email umbrella; and
- the stable identity used to represent the Conversation object in the Compass graph.

An item-level identifier must never be mistaken for a Conversation ID. Graph representation choices must never displace the source Conversation ID as the structural correlation truth.

### Identity verification gate

Before implementing automatic correlation, evidence must establish:

1. which Work IQ or Microsoft 365 field supplies the source Conversation ID for chat and email;
2. that the field is available consistently to Cowork;
3. that chat participant changes preserve the same Chat ID;
4. how replies, forwards, and branches affect the Email Conversation ID;
5. how to distinguish item-level IDs from Conversation-level IDs; and
6. what Compass reports when the required Conversation ID is missing or unavailable.

Until this gate is satisfied by test evidence, the identity model is a specification requirement, not a verified runtime capability, and automatic cross-scan correlation must not be reported as proven.

### Candidate guided identity resolution

If a graph artifact is missing its source Conversation ID even though the originating item remains available in Microsoft 365, Compass should guide the user through recovery rather than guess:

1. Block automated merge or update of the affected Conversation.
2. Identify the affected graph artifact and explain that its structural source identity is missing.
3. Help the user locate the originating chat or email in Teams or Outlook using available non-authoritative clues.
4. Retrieve or have the user provide the verified source Conversation ID through an approved mechanism.
5. Present the proposed frontmatter correction and its affected relationships.
6. Apply the correction only with explicit user approval and Graph Governor validation.
7. Revalidate the corrected artifact and report whether normal processing may resume.

Manual frontmatter repair is a recovery path, not permission to type an inferred value. The exact method for exposing or retrieving the Microsoft 365 Conversation ID is an open runtime question and requires a tested procedure. If the source ID cannot be verified, the artifact remains unchanged and blocked for automatic correlation.

## 7. Authority and approval contract

### SC-AUTH-001 — Evidence is not trusted knowledge

Authorized retrieval proves only that Compass may inspect the source and that the source contains observed activity. AI-generated summaries, classifications, alignments, and recommendations remain proposals until the required user authority is obtained.

### SC-AUTH-002 — User authority

The user may establish authoritative knowledge through:

- a valid direct edit;
- an unambiguous direct instruction within an authorized Skill workflow; or
- explicit approval of a displayed proposal.

Whether a particular direct instruction is sufficiently unambiguous must be testable in that Skill's scenarios.

### SC-AUTH-003 — Approval scope

Approval authorizes only the material change presented to the user. If the target objects, relationships, wording, or effects materially change before application, Compass must obtain renewed authority.

### SC-AUTH-004 — Consequential decisions

Topic creation, Topic alignment, Topic merge, Topic retirement, CSP alignment, and other organizational decisions remain user-approved unless the user later accepts a narrower deterministic rule.

### SC-AUTH-005 — Deterministic governance

The Graph Governor may automatically perform only actions that accepted contracts identify as deterministic and uniquely correct. It may not resolve competing interpretations, infer missing user intent, or use graph integrity as justification for changing durable meaning.

### SC-AUTH-006 — Direct edits

A valid direct user edit is authoritative. If it violates a shared contract, Compass preserves the content, reports the issue, and refrains from compounding the inconsistency. Automatic correction is allowed only when exactly one meaning-preserving repair is accepted by contract.

## 8. Skill responsibility contract

The charter confirms five candidate Skills by name and high-level intent. Their operational responsibilities, write ownership, handoffs, and exclusions have not yet been defined for the new Compass architecture.

The responsibility assignments in the imported Product and Technical Specs belong to the prior project. They are reference material only and must not be carried into this specification as defaults. Each new Skill requires its own reviewed specification. After those specifications exist, this section can record only the cross-Skill responsibility boundaries they share.

### SC-ROLE-001 — One accountable owner per modification

Every graph modification must identify the initiating Skill and the role contract that permits the operation.

### SC-ROLE-002 — No bypass of governance

A Skill that changes durable graph state must submit the intended change to the accepted validation and persistence boundary. It must not implement a private version of shared identity, authority, integrity, conflict, or outcome rules.

### SC-ROLE-003 — Read access does not imply write authority

The ability to retrieve evidence or inspect graph content does not authorize a Skill to modify that evidence, graph objects, or relationships.

### Responsibility-definition gate

Before implementing a Skill, its specification must define and receive user review for:

1. the outcome it owns;
2. the inputs and context it may use;
3. the graph objects and relationships it may propose or modify;
4. the decisions reserved for the user;
5. its handoffs to other Skills;
6. actions explicitly outside its role;
7. its expected interaction style or “vibe”; and
8. the scenarios that demonstrate these boundaries.

No prior-project Skill boundary is accepted merely because it appears in source material.

## 9. Change handoff contract

A cross-Skill change request should carry, at minimum:

| Field | Meaning |
| --- | --- |
| **requestId** | Stable identity for the handoff or proposal. |
| **initiatingSkill** | Skill and version that produced the request. |
| **authoritySource** | Direct user instruction, approved proposal, or accepted deterministic rule. |
| **operation** | Closed operation name rather than an unrestricted instruction to edit files. |
| **targets** | Stable graph IDs affected by the intended change. |
| **expectedEffects** | Objects and relationships expected to change. |
| **evidenceReferences** | Minimized provenance supporting the request, when applicable. |
| **baseState** | Fingerprints, versions, or equivalent evidence for detecting intervening edits. |
| **approvalReference** | Identity of the approval when approval is required. |
| **correlationId** | Identity connecting validation, application, recovery, and reporting. |

### SC-HAND-001 — Complete intent

A receiving Skill or shared capability must not infer omitted consequential intent. An incomplete request is rejected or returned for clarification.

### SC-HAND-002 — Material-change detection

If validation or current graph state changes the material effects of a request, the changed request returns to the authority step rather than extending the original approval silently.

### SC-HAND-003 — Minimized context

Handoffs include only the evidence and graph context required for the receiving responsibility. Raw transcripts, unrelated graph content, and secrets are excluded by default.

## 9A. Daily Log write contract

Daily Log maintenance is a shared consequence of graph modification. Any Skill that produces an authorized graph update must include enough information in its validated change request for the corresponding Daily Log update to be planned and verified with the same operation.

### SC-LOG-001 — Write trigger

Every action that results in an authorized durable graph update must create or update the applicable Daily Log. This includes approved Conversation changes, authorized Tracking Topic Interview changes, direct user-requested graph changes, and other accepted Skill operations.

Provisional evidence discovery, rejected proposals, blocked operations, validation-only activity, and failed writes do not create authoritative Daily Log activity entries.

### SC-LOG-002 — Date selection

- When an update is grounded in source activity, use the user's local calendar date of that activity.
- When an update has no underlying source-activity date, use the user's local date of the authorized action.
- When older activity is processed later, update the earlier source-date Daily Log rather than treating the activity as if it occurred on the processing date.
- Approval, processing, and write timestamps may be retained separately for traceability but do not change the selected Daily Log date.

The user-local timezone used for date conversion must be known and consistently applied. The authoritative value is stored in graph-level configuration. If it is missing or invalid, Compass may use a valid Microsoft 365 timezone provisionally for at most one authorized write set when that use is disclosed and retained in operation evidence. A subsequent date-dependent write and setup completion require a confirmed configured timezone. If neither source yields one valid timezone, or the source timestamp is ambiguous, automatic date assignment is blocked.

### SC-LOG-003 — Stable membership and deduplication

Within each managed Daily Log section, an affected graph object appears at most once for that date and role. Membership is keyed by stable Compass object ID, not title, filename, or display link.

Repeated processing updates the existing managed entry instead of appending a duplicate. Separate objects with similar titles remain separate entries.

### SC-LOG-004 — Managed content and user content

Compass updates only explicitly defined managed sections of a Daily Log. User-authored narrative, unknown frontmatter, and content outside those sections must remain unchanged.

The managed index may be regenerated only when Compass can preserve user-authored content and reconstruct the index from accepted authoritative evidence. A formatter or rewrite must not silently alter the user's prose.

### SC-LOG-005 — Same-operation integrity

The graph-object change and its required Daily Log update form one declared write set. Graph Governor validates both before application and verifies both afterward.

Compass must not report the complete graph update as committed when the object changed but the required Daily Log update is missing or invalid. The outcome must distinguish rollback, partial application, or recovery-required state according to the accepted persistence contract.

### SC-LOG-006 — No circular authority

A Daily Log may help users and Skills navigate to graph activity, but it must not be used as the sole authority to reconstruct semantic relationships or prove that an update was authorized. Deleting or editing a managed Daily Log link does not delete or realign the referenced object.

### SC-LOG-007 — Minimum Daily Log handoff data

A graph-update request must provide or allow deterministic derivation of:

| Information | Purpose |
| --- | --- |
| **Affected object ID and type** | Creates stable, deduplicated navigation. |
| **Activity or action timestamp** | Selects the user-local Daily Log date. |
| **Date basis** | Distinguishes source activity from user-action fallback. |
| **Short display label** | Produces readable navigation without becoming identity. |
| **Operation and authority reference** | Establishes that the entry reflects an authorized graph update. |
| **Source-state evidence** | Detects an intervening Daily Log edit before replacement. |

Every authorized update uses a stable operation ID for action-level deduplication. Daily Logs display action time in the configured or disclosed provisional local timezone while exact UTC evidence remains available to Graph Governor. The authoritative timezone is graph-level Compass configuration rather than Skill memory or duplicated per-log configuration. A retry or recovery with the same operation ID remains part of the same provisional allowance; a different operation ID does not.

Graph configuration identifies the graph with one canonical lowercase UUID v4 generated securely at bootstrap and retained across rename, movement, synchronization, and backup restoration. Microsoft 365 timezone values are accepted directly only when they match a pinned IANA database, or are mapped deterministically from a Windows timezone ID through a pinned Unicode CLDR `windowsZones.xml` release. Unknown, fuzzy, offset-only, absent, or ambiguous values block date-dependent writes. Mapping evidence retains the raw value, resolved IANA name, source field, selected territory, and exact data releases.

Initial graph configuration is created and validated before the installation-date Daily Log is created in the same setup workflow. Later configuration changes appear in the Daily Log's managed Configuration section. Existing logs are not silently moved when timezone changes; a mismatch affecting provisional entries is reported for explicit reviewed correction.

The Graph Schema Specification defines the Daily Log frontmatter, managed-section syntax, and accepted first-Beta operation labels.

## 10. Validation contract

### SC-VAL-001 — Validate before modification

Before changing authoritative content, Compass validates:

1. the proposed object representation;
2. the stable identities and object types involved;
3. the relationships owned or affected by the change;
4. the authority supporting the change; and
5. the current source state needed to detect intervening edits.

### SC-VAL-002 — Validate after modification

Compass reports success only after re-reading or otherwise verifying that all intended effects exist and the touched closure remains valid.

### SC-VAL-003 — Unrelated damage

An unrelated graph problem may be reported without blocking an otherwise valid isolated change. The affected change must stop when the unrelated problem makes its own validity uncertain.

### SC-VAL-004 — Governor result

A Graph Governor validation returns one of these semantic results:

- valid for the requested operation;
- invalid with identified contract violations;
- blocked by conflict or missing authority;
- indeterminate and requiring user or design review.

Validation does not itself imply that a change was applied.

## 11. Persistence, conflict, and recovery contract

### SC-WRITE-001 — Preserve user changes

Compass must compare the source state used to prepare a change with the state present when the change is applied. A conflicting edit stops replacement unless one accepted, meaning-preserving result is uniquely determinable.

### SC-WRITE-002 — All-or-honest multi-object behavior

A change affecting multiple objects must not be reported as complete unless every intended effect completes and validates. If the storage platform cannot provide atomic multi-file writes, Compass must use an accepted recovery mechanism and disclose rollback or recovery-required outcomes.

### SC-WRITE-003 — Preserve recoverability

A failed or interrupted operation must leave either:

- the validated pre-operation state restored; or
- durable, understandable recovery evidence that does not overwrite later user edits.

### SC-WRITE-004 — Path and content safety

All changes remain inside the configured graph root, use supported file types, treat source content as untrusted data, and preserve unmanaged user-authored content.

### SC-WRITE-005 — Disposable-beta recovery protocol

Gate 0 through Gate 3 mutating checks may operate only on a disposable synthetic graph with a verified restorable baseline. Before each write set, the test operator or harness must:

1. confirm that no other writer is active;
2. retain a complete restorable snapshot outside the graph root;
3. identify every intended file effect and its current content fingerprint;
4. assign one stable operation ID; and
5. validate the complete proposed write set, including its Daily Log effect.

The writer rechecks each current fingerprint immediately before replacement, applies the declared files in deterministic order, and verifies the complete touched closure afterward. A changed fingerprint stops the operation as `conflict` before that file is replaced.

If application or verification fails, Compass accounts for every intended effect. It may restore from the retained baseline only when the graph is still the isolated disposable fixture, no intervening edit is detected, and restoration is within the user's authorization for that test. Restoration must itself be verified. Otherwise, Compass preserves the graph and recovery evidence unchanged and reports `recovery-required`.

This protocol supports bounded synthetic beta testing; it is not accepted for a personal or production graph. The exact snapshot format, fingerprint algorithm, operation-evidence schema, concurrency mechanism, and production transaction design remain deferred.

## 12. Common outcome contract

Every mutating operation must terminate with one primary outcome and enough detail to account for each intended effect.

| Outcome | Meaning |
| --- | --- |
| **proposed** | A candidate change exists but lacks required authority. No authoritative change was made. |
| **rejected** | The user declined the proposal. No authoritative change was made from it. |
| **committed** | All authorized effects completed and passed post-change validation. |
| **committed-with-warnings** | All authorized effects completed and validated; unrelated or non-blocking concerns were reported. |
| **blocked** | No change was attempted because authority, permission, identity, or required information was missing. |
| **conflict** | No unsafe replacement was made because source state changed or competing states exist. |
| **rolled-back** | Application began, failed, and the validated prior state was restored. |
| **recovery-required** | Compass cannot safely prove or restore a complete valid state without review. |
| **failed** | The operation did not complete; the report states whether any effect may have occurred. |

### SC-OUT-001 — No false success

Only `committed` and `committed-with-warnings` represent successful modification. A user-facing summary may use natural language, but it must preserve the semantic distinction.

### SC-OUT-002 — Effect accounting

The result identifies intended, completed, unapplied, rolled-back, uncertain, and preserved effects as applicable.

### SC-OUT-003 — Safe reporting

Results include stable operation references and actionable errors without exposing raw evidence, note bodies, secrets, or unrelated graph content.

**Review note:** Outcome names are candidates. Their meanings matter more than their final labels.

## 13. Compatibility and evolution contract

### SC-EVO-001 — Contract versioning

Accepted shared contracts receive a version. Every tested Skill specimen identifies the contract version it claims to support.

### SC-EVO-002 — Change classification

A contract change is breaking when an existing conforming Skill could produce a now-invalid object, handoff, authority decision, or outcome. Breaking changes require explicit review and affected-scenario reruns.

### SC-EVO-003 — Evidence follows exact versions

Test results identify the exact Skill versions, contract version, graph fixture, and relevant environment used. Passing evidence for one combination does not automatically validate another.

### SC-EVO-004 — Preserve prior contracts

Superseded contract versions and their test evidence remain available for historical explanation. They are not rewritten to match later design.

## 14. Minimum contract for the beta candidate

The complete beta candidate must honor the accepted subset of the following contracts. This selection authorizes specification work only; it does not authorize implementation.

Graph Governor should validate all of the following where they apply to an operation:

1. **Frontmatter structure** — parseable YAML, required fields, allowed values, and identifier shape.
2. **Relationship integrity** — referenced objects exist, have the expected type, and obey accepted cardinality and ownership rules.
3. **Source identity** — Conversation records contain the required durable source Conversation ID and do not substitute item IDs or inferred similarity.
4. **Authority evidence** — a proposed modification identifies the authority that permits it.
5. **Conflict detection** — the target artifact has not changed since the proposed modification was prepared.
6. **Disposable-beta recovery** — synthetic write checks use the bounded protocol in SC-WRITE-005 and report every effect honestly.

Last-activity meaning and ownership remain deferred. Graph Governor may report a gap but must not enforce one derivation as authoritative.

The first Skill implementation should depend only on the smallest reviewed subset required to generate useful evidence. Before testing the first write-capable slice, review at least:

1. shared object vocabulary;
2. stable graph and evidence identity distinction;
3. user authority and approval scope;
4. one canonical representation for each relationship used by the slice;
5. validation request and result semantics;
6. conflict detection and honest write outcomes; and
7. the Graph Governor's responsibility for that slice; and
8. the guided recovery behavior for a missing or invalid source Conversation ID.

Other contracts may remain open if the slice cannot exercise them and no artifact falsely claims broader compatibility.

## 15. Required scenario families

Each Skill claiming compatibility with this specification should eventually be tested against:

### Individual Skill behavior

- performs its assigned responsibility;
- refuses operations outside its responsibility;
- preserves its intended interaction style or “vibe”;
- distinguishes proposals from authoritative changes; and
- reports empty, blocked, ambiguous, and failed outcomes honestly.

### Contract behavior

- produces and consumes valid object identities and relationships;
- uses the accepted handoff shape;
- honors approval scope;
- preserves direct user edits;
- stops on material conflicts; and
- accounts for every intended effect.

### Progressive integration

- initiating Skill with Graph Governor validation;
- one producer-to-consumer handoff at a time;
- recovery from failure at each write stage;
- regression after a Skill or contract version changes; and
- complete workflow only after component and adjacent-handoff evidence exists.

## 16. Deferred beta decisions

Runtime evidence must still determine which Microsoft 365 fields provide durable Chat and Email Conversation IDs. Skill boundaries will be defined in Slice B under these contracts.

The following remain explicitly deferred and do not block baseline acceptance:

- final last-activity semantics;
- item-level evidence retention;
- staleness automation;
- Person merge;
- CSP retirement;
- production-scale transaction design; and
- deterministic repair outside the disposable-beta recovery protocol.

## 17. Acceptance boundary

This specification is the accepted cross-Skill design baseline for version `0.3-beta-baseline`. Its acceptance permits Slice B responsibility-specification work only.

Approval would not authorize:

- implementation or modification of a Skill;
- creation or installation of a `.SKILL` package;
- access to Microsoft 365 evidence;
- creation or modification of a OneDrive graph;
- acceptance of imported Aegis implementation claims;
- deployment, publication, or release; or
- automatic acceptance of unresolved decisions in this document.

Open decisions must remain visible or be resolved in dated decision records before dependent implementation is authorized.
