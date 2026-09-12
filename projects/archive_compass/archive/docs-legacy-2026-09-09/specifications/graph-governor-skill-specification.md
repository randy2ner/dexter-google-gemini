# Specification: Graph Governor behavior

## Document control

- **Status:** Accepted responsibility specification
- **Project:** Compass
- **Applies to Skills:** Graph Governor
- **Version:** 0.8-production-test-responsibility
- **Created:** 2026-08-28
- **Last updated:** 2026-09-08
- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Approval:** Accepted as part of Slice B on 2026-09-02
- **Implementation authority:** Production-content testing, provenance validation, source, packaging, and static validation authorized by the user on 2026-09-08

## 1. Purpose

Graph Governor is Compass's integrity authority. It protects the structure of the knowledge graph and the rules governing modifications while leaving meaning, organization, and consequential choices under user authority.

Its Beta role is to:

- validate every proposed graph write before application;
- verify every graph write after application;
- inspect graph health when the user requests it;
- identify, rank, and explain integrity issues;
- guide the user through safe resolution; and
- prevent ambiguous, unauthorized, conflicting, or structurally invalid modifications.

Graph Governor does not decide what the user's knowledge should mean. It determines whether a requested operation is authorized and structurally safe under accepted Compass contracts.

## 2. Governing sources

This specification is subordinate to:

1. the [Compass Vision and Scope Charter](../charter/compass-vision-and-scope-charter.md); and
2. the [Compass Shared Contracts Specification](compass-shared-contracts-specification.md); and
3. the accepted [Compass Graph Schema Specification 0.7](compass-graph-schema-specification.md).

The charter defines vision and authority. The shared contracts define cross-Skill rules. This document defines Graph Governor's role within those boundaries.

Files under the charter's source-material directory describe a different, incomplete prior effort. They may inform review but do not assign responsibilities to this Skill.

## 3. Intended interaction style

Graph Governor should feel like a **quiet safety officer**:

- mostly invisible when an operation is valid;
- concise, calm, and specific when intervention is required;
- focused on impact and next steps rather than internal mechanics;
- unwilling to describe uncertainty as success;
- helpful without becoming conversational overhead; and
- firm about accepted integrity and authority boundaries.

A successful routine validation should not require a long compliance report. A blocked operation should explain what was protected, why it stopped, and what the user can do next.

## 4. Invocation model

### 4.1 Pre-write validation

Every Skill must invoke Graph Governor before changing durable graph state. Graph Governor evaluates the proposed operation and returns a validation decision. No write may proceed from an invalid, blocked, or indeterminate decision.

### 4.2 Post-write verification

After a write is attempted, Graph Governor verifies the actual effects against the authorized effects and relevant graph contracts. The initiating Skill may report successful modification only after Graph Governor verifies completion.

### 4.3 User-requested health scan

The user may ask Graph Governor to inspect the graph independently of a proposed write. A health scan is read-only in the first Beta and produces a prioritized integrity report with guided resolution steps.

### 4.4 Excluded Beta invocations

The first Beta does not run autonomous scheduled scans or accept an unattended request to repair the graph. These invocation modes require later review and evidence.

## 5. Required pre-write request

Before Graph Governor can validate a proposed write, the initiating Skill must provide:

| Required information | Purpose |
| --- | --- |
| **Request identity** | Correlates validation, application, post-write verification, and reporting. |
| **Initiating Skill and version** | Identifies the component requesting authority to modify the graph. |
| **User authority reference** | Identifies the direct user instruction or explicit proposal approval authorizing the change. |
| **Exact intended effects** | Lists the objects, relationships, and managed fields expected to change. |
| **Source-state evidence** | Supplies fingerprints, versions, or equivalent evidence for detecting intervening edits. |

When a proposed meaning derives from Microsoft 365 activity, supporting evidence references may also be required by the initiating Skill's specification. They are not automatically required for direct user-authored maintenance.

An incomplete request is not valid. Graph Governor must not infer missing consequential intent.

## 6. Pre-write validation responsibilities

Graph Governor validates only against accepted contracts and schemas. The first Beta is expected to evaluate:

### 6.1 Authority

- The initiating Skill and version are identified.
- The Skill's accepted specification permits the requested operation.
- The supplied user authority covers the exact material effects.
- The approval has not been silently extended to changed targets, relationships, or wording.

### 6.2 Frontmatter structure

- YAML is parseable using the accepted safe parsing rules.
- Required fields exist.
- Managed fields use accepted names, types, formats, and allowed values.
- Item IDs are not substituted for source Conversation IDs.
- Unknown or user-managed content is preserved according to the accepted schema contract.

Graph Governor enforces only fields and rules in the accepted schema version claimed by the initiating Skill.

### 6.3 Identity

- Durable graph objects have valid stable graph identities.
- Conversation records have a durable source Chat or Email Conversation ID.
- Source Conversation IDs are distinguished from item-level evidence IDs.
- The same source Conversation ID does not create conflicting active Conversation representations.
- Titles, participants, timestamps, or semantic similarity are not used as substitute identity.
- Proposed schema-version-2 Person effects do not introduce or update `userPrincipalName`; a pre-existing value outside the requested effect remains preserved unmanaged frontmatter pending separate cleanup authority.

### 6.4 Relationship integrity

- Each Conversation has exactly one `trackingTopicId`: a valid Tracking Topic ID or reserved `parking-lot` value.
- Every Conversation `participantIds` member resolves to one Person with meaningful `firstName` and `lastName`.
- Every Tracking Topic `participantIds` and `excludedParticipantIds` member resolves to one Person, each list is unique, and the lists are disjoint.
- Every Tracking Topic has exactly one `attentionState`: `action`, `waiting`, or `observing`.
- Deterministic Conversation participant funneling honors Topic exclusions and does not prune participants after Conversation lifecycle or alignment changes.
- Each Tracking Topic has zero or one authoritative CSP relationship stored on the Tracking Topic.
- Referenced objects exist and have the expected type.
- Topic Conversation lists and CSP Topic lists are treated as derived views, not competing authoritative relationships.
- The proposed change does not create dangling or contradictory relationships.

### 6.5 Conflict safety

- The graph artifacts to be changed still match the source-state evidence used to prepare the request.
- An intervening user or Skill edit stops replacement unless an accepted rule permits exactly one meaning-preserving reconciliation.
- A materially changed proposal returns to the user-authority step.

### 6.5.1 Topic narrative metadata and preservation

- A present Topic `tags` value is a unique list of non-empty lowercase kebab-case strings.
- A present Topic `reviewBullet` value is boolean.
- Proposed changes to either field and material Topic narrative changes have exact user authority and appear in expected effects.
- `hpi`, `solved`, `reviewBullet`, `status`, `success`, and `attentionState` remain independent; Graph Governor never infers one from another or judges narrative truth.
- Unrelated operations preserve accepted Topic metadata, narrative sections, and user-authored content.
- A Daily Scan narrative handoff is context, not Topic-write authority; Tracking Topic Interview initiates the approved Topic effect.

### 6.6 Last-activity integrity

Graph Governor will validate Conversation and Tracking Topic last-activity values only after scenarios establish their accepted meanings.

Testing must compare:

- source activity versus graph modification for Conversations; and
- aligned Conversation activity versus Tracking Topic Interview engagement for Topics.

Until those contracts are accepted, Graph Governor may identify inconsistent or missing values for investigation but must not enforce one derivation as authoritative.

### 6.7 Daily Log integrity

For every authorized graph update, Graph Governor validates that the proposed write set includes the applicable Daily Log update required by the shared contract. It checks the user-local date basis, stable object-ID membership, deduplication, preservation of user-authored content, and source-state evidence for the Daily Log.

After application, Graph Governor verifies both the graph-object effects and the required Daily Log entry. An object update with a missing or invalid required Daily Log effect is not reported as fully committed.

### 6.8 Graph configuration integrity

Graph Governor validates `_compass/config.yaml`, including its supported schema version, canonical lowercase UUID v4 graph ID, and IANA timezone. It verifies that graph identity is retained across rename, movement, synchronization, and restoration, while independent graphs and fixtures do not intentionally share an identity. A valid direct user edit is authoritative except that an established `graphId` is immutable. An invalid edit or changed established graph identity is preserved and blocks dependent writes without preventing read-only inspection or guided resolution.

If configured timezone is unavailable, Graph Governor may validate provisional use of a Microsoft 365 timezone only when the value directly matches a pinned IANA database or maps deterministically through a pinned Unicode CLDR `windowsZones.xml` release, its provisional status is disclosed, and its source and mapping evidence are retained. Fuzzy, offset-only, unknown, absent, or ambiguous values are invalid for date assignment.

One provisional timezone is limited to one stable operation ID, including retries and recovery for that operation. Graph Governor blocks another date-dependent operation and setup completion until a valid IANA timezone is confirmed in configuration. A later mismatch is reported without silently moving Daily Log entries.

## 7. Pre-write decisions

Graph Governor returns one primary decision:

| Decision | Meaning |
| --- | --- |
| **Valid** | The request satisfies the contracts evaluated and may proceed using the validated source state. |
| **Invalid** | The request violates an accepted structural or role contract and must not proceed. |
| **Blocked** | Required authority, identity, permission, source state, or information is missing. |
| **Conflict** | The relevant graph state changed or competing states prevent safe replacement. |
| **Indeterminate** | The rules do not yield one safe interpretation; user or design review is required. |

A `Valid` decision is not evidence that the write occurred. It applies only to the exact request and source state validated.

## 8. Post-write verification responsibilities

After a write attempt, Graph Governor verifies:

1. every authorized effect was applied;
2. no unauthorized material effect was introduced;
3. each changed artifact remains structurally valid;
4. affected identities and relationships remain valid;
5. protected user-authored content was preserved;
6. the touched closure remains consistent; and
7. the reported outcome accurately distinguishes success, warning, rollback, uncertainty, or failure.

Only a fully applied and verified request may be reported as committed. If verification cannot establish the resulting state, Graph Governor returns an uncertain or recovery-required result rather than assuming success.

## 9. Health scan responsibilities

The first Beta user-requested health scan examines:

- all managed graph files for parse and accepted-schema issues;
- all accepted authoritative relationships for missing targets, wrong target types, duplicate authority, and cardinality violations;
- Conversation source IDs for missing, malformed, item-level, or conflicting values; and
- last-activity consistency to the extent an accepted contract exists.

A defect unrelated to a proposed write does not automatically block that write. It blocks the write only when the defect affects the intended change or makes validation of that change uncertain.

### 9.1 Health issue report

Each reported issue should include:

- a stable issue identity;
- affected graph artifact or relationship;
- violated contract or unresolved rule;
- severity and practical impact;
- whether the issue blocks a specific operation;
- whether the resolution is deterministic or requires user judgment; and
- concise guided resolution steps.

### 9.2 Candidate severity model

| Severity | Candidate meaning |
| --- | --- |
| **Critical** | Durable knowledge may be corrupted, overwritten, misidentified, or falsely reported as valid. |
| **High** | A graph object or important relationship cannot be safely interpreted or modified. |
| **Medium** | The graph remains usable, but a bounded inconsistency affects navigation, reporting, or future operations. |
| **Low** | A non-blocking convention or quality issue should be corrected but does not threaten meaning or integrity. |

The labels and thresholds require scenario review before acceptance.

## 10. Guided resolution

The production-test candidate validates, reports, and guides. It does not independently retrieve Work IQ, interpret source evidence, originate a graph modification, or perform automatic recovery.

A guided resolution should:

1. preserve the current artifact;
2. explain the integrity issue in user-facing terms;
3. identify the evidence needed to resolve it;
4. help the user locate or verify that evidence;
5. prepare an exact candidate correction when possible;
6. show the affected fields and relationships;
7. require explicit user approval;
8. submit the correction through normal pre-write validation; and
9. verify the result after application.

### 10.1 Missing source Conversation ID

A missing source Conversation ID is an exceptional integrity problem, not a normal capture mode. Graph Governor should:

1. block automatic correlation or update of the affected Conversation;
2. identify the affected artifact;
3. guide the user to locate the originating chat or email in Teams or Outlook;
4. obtain a verified source Conversation ID through an approved and tested mechanism;
5. distinguish that ID from message or item IDs;
6. present the proposed frontmatter correction;
7. obtain explicit user approval; and
8. validate the correction and affected relationships before and after application.

Graph Governor must never infer the missing ID from subject, participants, timing, or semantic similarity. If verification is unavailable, the artifact remains unchanged and blocked for automatic correlation.

## 11. Modification and recovery authority

The first Beta has **no independent semantic graph modification authority**.

Graph Governor may:

- inspect the graph;
- validate proposed changes;
- verify completed changes;
- report and prioritize issues;
- prepare or explain candidate repairs; and
- guide the user through resolution.

Graph Governor may not:

- apply a repair without explicit user approval;
- create, merge, align, retire, archive, or delete semantic graph objects on its own;
- delete a Conversation merely because it is stale or delete a Tracking Topic under any lifecycle state;
- choose among plausible source identities or relationships;
- rewrite user-authored prose;
- broaden another Skill's approval;
- authorize a Skill operation not permitted by that Skill's accepted specification; or
- automatically roll back, repair, or delete production content; or
- claim the whole graph is healthy when only a bounded scope was inspected.

A partial or unverifiable production application returns `recovery-required`, accounts for every completed, unapplied, uncertain, and preserved effect, and blocks dependent writes pending user-led resolution.

## 12. Explicit exclusions

Graph Governor is not:

- the owner of the user's knowledge or organizational decisions;
- a replacement for individual Skill specifications;
- a general-purpose content editor;
- an autonomous curator;
- a Microsoft 365 evidence-discovery Skill;
- a background monitoring service in the first Beta;
- proof that Cowork or OneDrive supports a proposed runtime mechanism; or
- permission to implement, package, install, or connect a Skill.

## 13. Candidate behavior examples

### GG-BETA-001 — Valid pre-write request

A fully authorized, structurally valid change with matching source-state evidence receives `Valid` without unnecessary user interruption.

### GG-BETA-002 — Missing authority

A structurally valid change without a sufficient user-authority reference is blocked and no write occurs.

### GG-BETA-003 — Material approval drift

A request changes materially after user approval. Graph Governor invalidates the old approval scope and sends the revised proposal back for authority.

### GG-BETA-004 — Missing source Conversation ID

A Conversation lacking the required source ID is reported and blocked from automatic correlation. Graph Governor guides verification without inventing an ID.

### GG-BETA-005 — Item ID substituted for Conversation ID

A message-level or item-level ID in the source Conversation field is rejected when the distinction can be determined.

### GG-BETA-006 — Invalid Topic relationship

A Conversation references a missing object or an object that is not a Tracking Topic. The affected change is blocked and the existing artifact is preserved.

### GG-BETA-007 — Invalid CSP relationship

A Tracking Topic references a missing object or an object that is not a CSP. The affected change is blocked and the existing artifact is preserved.

### GG-BETA-008 — Intervening direct edit

A user changes a target artifact after the request was prepared. Graph Governor detects the conflict and prevents silent overwrite.

### GG-BETA-009 — Post-write mismatch

The actual effects differ from the authorized effects. Graph Governor refuses to report committed success and identifies the uncertain or recovery-required state.

### GG-BETA-010 — Unrelated graph damage

A health issue outside the touched closure is reported, but an otherwise valid and independently verifiable write is not blocked.

### GG-BETA-011 — Read-only health scan

A user-requested scan ranks frontmatter, relationship, and source-identity issues without changing graph artifacts.

### GG-BETA-012 — Quiet valid path

A routine valid request produces a concise validation result without burdening the user with internal mechanics.

### GG-BETA-013 — Deferred last activity

Graph Governor identifies that authoritative last-activity validation is unavailable and does not invent or enforce a derivation.

### GG-BETA-014 — Stale Conversation retention

A Conversation crossing the accepted stale-retention threshold is retained and surfaced for review. No deletion occurs without explicit user approval of the exact Conversation or an explicitly bounded set.

### GG-BETA-015 — Permanent Tracking Topic

A stale active Topic may be proposed for archival, and an archived Topic may be reactivated, but Graph Governor rejects every operation that would delete a Tracking Topic. It also rejects archival without an explicitly approved boolean `success`, rejects inconsistent status/success combinations, requires every Topic to have a valid `attentionState`, and requires reactivation to remove `success` while confirming or changing attention state.

### GG-BETA-016 — Daily Log update

An authorized graph update creates or updates the Daily Log for the correct user-local activity date, links the affected object by stable ID, and preserves user-authored content outside managed sections.

### GG-BETA-017 — Backdated and repeated activity

Activity processed today for an earlier source date updates the earlier Daily Log. Reprocessing the same object for that date updates its existing managed entry rather than creating a duplicate.

### GG-BETA-018 — Incomplete Daily Log effect

The graph object changes but its required Daily Log update fails or cannot be verified. Graph Governor refuses full committed success and reports the applicable partial, rollback, or recovery-required outcome.

### GG-BETA-019 — Configuration and timezone validation

Graph Governor accepts valid graph configuration, preserves an invalid direct edit while blocking dependent writes, and verifies disclosed provisional timezone use without treating it as confirmed configuration.

### GG-BETA-020 — Bootstrap completeness

Initial setup is not reported complete unless graph configuration and the installation-date Daily Log both validate and the safe Configuration entry exists.

### GG-BETA-021 — Graph identity and timezone determinism

Graph Governor rejects malformed or non-v4 graph IDs; validates retention and separation rules for graph identity; records pinned IANA and CLDR mapping evidence; and blocks a second date-dependent operation after one provisional operation ID until timezone confirmation.

## 14. Required test evidence before broader authority

Graph Governor should not receive automatic repair authority until evidence demonstrates that:

- the repair rule has exactly one meaning-preserving result;
- later user edits cannot be overwritten;
- rerunning the repair is safe;
- partial application cannot be reported as success;
- the user can understand what changed and why; and
- regression scenarios protect the rule as graph schemas evolve.

## 15. Deferred design questions

1. Which Microsoft 365 or Work IQ fields provide durable Chat and Email Conversation IDs?
2. How can the user or Cowork expose those IDs during guided resolution?
3. What source-state evidence and post-write verification mechanisms can Cowork and OneDrive provide?
4. What do Conversation source activity, graph modification, Topic Conversation activity, and Topic Interview engagement each mean?
5. Should health issue severity affect only prioritization, or should any severity block unrelated writes?
6. What separately authorized production recovery workflow can safely resolve partial effects without automatic rollback?

## 16. Acceptance boundary

This specification defines Graph Governor's production-test responsibility boundary and compatibility with Shared Contracts `0.8-production-evidence-baseline` and Graph Schema `0.7-hpi-narrative-baseline`.

Acceptance would not authorize:

- implementation or modification of the Skill;
- creation or installation of a `.SKILL` package;
- independent access to Microsoft 365 evidence;
- writes to a OneDrive graph;
- autonomous repair authority;
- production-content testing beyond the exact user-authorized operation; or
- deployment, publication, or release.

Those activities require separate, explicit user direction and must produce linked Dexter evidence.
