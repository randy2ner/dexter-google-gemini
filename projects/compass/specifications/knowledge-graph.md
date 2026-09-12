# Compass Knowledge Graph Specification

## Document control

- **Status:** active
- **Version:** 1.4
- **Owner:** User / product owner
- **Created:** 2026-09-11
- **Last updated:** 2026-09-12
- **Charter:** [Compass Charter](../CHARTER.md)
- **PRD requirements:** [Compass PRD](../PRD.md), `PR-007` through `PR-014` and `PR-017` through `PR-025`
- **Implementation authority:** Local Skill source, fixtures, and disconnected validation are authorized. Connected OneDrive writes, migration, packaging, deployment, and release remain unauthorized.

## Purpose and applicability

This Specification defines the portable Markdown/YAML knowledge graph that Compass Skills read and write in OneDrive. It applies independently of the Skill Host. Archived Compass schema is reference input; only contracts confirmed in the current project are accepted here.

## Scope and boundaries

- **In scope:** Object semantics, managed fields, stable identity, relationships, cardinality, preservation behavior, and Daily Log indexing.
- **Out of scope:** Skill conversation flow, Work IQ retrieval behavior, OneDrive transport mechanics, and unconfirmed archived fields.
- **Authority, privacy, and safety:** The graph contains inspectable working knowledge refined over time. It preserves source context, unrelated user-authored content, and the user's ability to correct ordinary content directly. Ambiguous identity or placement and destructive, overwriting, or disclosing changes require user direction.

## Required behavior

| ID | Behavior or contract | Observable expectation | Status |
| --- | --- | --- | --- |
| GRAPH-001 | Each Customer Success Plan is a durable Markdown object with stable identity, a non-empty title, and user-authored or approved narrative describing customer outcomes and strategic context. | The CSP remains identifiable after title, filename, or folder changes, and its content is readable without a Skill Host. | Accepted |
| GRAPH-002 | A CSP has no managed lifecycle status and stores no authoritative reverse list of Efforts. | CSP membership is derived from Effort references; no competing relationship list or CSP status is required. | Accepted |
| GRAPH-003 | Each Effort aligns with zero or one CSP. | An Effort may be unaligned or reference one stable CSP identity, never several. | Accepted |
| GRAPH-004 | Each Effort is a durable Markdown object with stable identity, a non-empty title, and optional user-authored or approved narrative. | The Effort remains identifiable after title, filename, or folder changes, and its narrative is readable without a Skill Host. | Accepted |
| GRAPH-005 | Each Effort has `active` or `archived` status and one attention state: `action`, `waiting`, or `observing`. | The graph rejects an Effort with an unsupported, missing, or multiple status or attention values. | Accepted |
| GRAPH-006 | An Effort may record a conditional success value, optional unique lowercase-kebab tags, an optional review marker, and, when archived, retained metadata for removed Activities. | Optional fields remain absent unless applicable and preserve their defined types and normalized values when present. | Accepted |
| GRAPH-007 | An Effort owns its optional CSP reference and unique, disjoint included and explicitly excluded Person references. | CSP and Person relationships are derived from the Effort; the same Person cannot be simultaneously included and excluded. | Accepted |
| GRAPH-008 | Each Conversation, also called an Activity, is a durable Markdown object with stable Compass identity, a non-empty title, a concise account of meaningful customer work, and minimized provenance for source-derived content. | The object explains customer work independently of its evidence, filename, title, and OneDrive transport identity. | Accepted |
| GRAPH-009 | Activity identity follows the coherent unit of customer work rather than a source container. | Evidence from several messages, threads, chats, meetings, or direct user input may support one Activity; one source may support several Activities when it contains distinct customer work. | Accepted |
| GRAPH-010 | Each Conversation owns a unique set of participating Person references. | A Person appears at most once in a Conversation's participant set, while the same Person may participate in other Conversations. | Accepted |
| GRAPH-011 | Each Conversation has exactly one Effort reference or the Parking Lot disposition. | A Conversation cannot align with multiple Efforts and cannot remain without either an Effort or Parking Lot disposition. | Accepted |
| GRAPH-012 | Ambiguous Activity continuity blocks automatic merge or update. | Compass reports uncertainty when evidence could describe a new Activity or continue an existing one and does not infer identity solely from a source container. | Accepted |
| GRAPH-013 | Each Person is a durable Markdown object with stable Compass identity and meaningful `firstName` and `lastName` values. | The same person remains identifiable after title, filename, email, or folder changes. | Accepted |
| GRAPH-014 | A Person may contain optional user-reviewed normalized email addresses. | Only reviewed email values are stored, and equivalent normalized values do not create duplicate Person identities. | Accepted |
| GRAPH-015 | Reverse Person relationships to Efforts and Conversations are derived rather than stored as authority on the Person. | Reading the graph can find a Person's related Efforts and Conversations without competing reverse lists. | Accepted |
| GRAPH-016 | Each Daily Log is one Markdown file for a user-local date and indexes durable graph changes on that date. | Each creation, revision, move, archive, and other durable graph change appears once in the applicable local-date file. | Accepted |
| GRAPH-017 | Each managed Daily Log entry contains only the required metric facts: timestamp, object type, stable object ID, and change type. | Counts and trends for graph changes can be derived without parsing narrative or duplicating object relationships. | Accepted |
| GRAPH-018 | Daily Log entries describe graph activity only and do not become work-event history or relationship authority. | Work events are represented through their appropriate graph objects, and object relationships remain authoritative outside the log. | Accepted |
| GRAPH-019 | Every graph object has YAML frontmatter containing `schemaVersion: 2`, its accepted `type`, stable `id`, non-empty `title`, and immutable `createdAt`. | A reader can identify and interpret every object independently of its title, filename, folder, or Skill Host. | Accepted |
| GRAPH-020 | Compass-managed field names use camelCase and managed timestamps use timezone-explicit UTC ISO 8601. | Managed values have consistent portable syntax across all object types. | Accepted |
| GRAPH-021 | Stable object IDs survive title, filename, and folder changes. | Renaming or moving an object does not change its identity or create a duplicate object. | Accepted |
| GRAPH-022 | Managed updates preserve unrecognized frontmatter and user-authored Markdown unless that content prevents safe parsing. | A routine Compass update leaves unrelated user additions intact; unsafe parsing blocks the affected update rather than overwriting content. | Accepted |
| GRAPH-023 | The graph root contains `_compass/config.yaml`, `CSPs/`, `Efforts/`, `People/`, `Conversations/`, and `Daily Logs/`. | Managed files are created under the folder for their accepted object type, and the configuration has one predictable location. | Accepted |
| GRAPH-024 | Folder paths and filenames are transport locations, not object identity. | A valid move or rename preserves stable ID and relationships; graph references do not depend on a title or filename remaining unchanged. | Accepted |
| GRAPH-025 | Source-derived working knowledge preserves enough source context to distinguish evidence from Compass interpretation. | A reader can inspect where a fragment came from without relying on hidden Skill Host state or treating a summary as a source fact. | Accepted |
| GRAPH-026 | Governor validates structure and effects without claiming that structurally valid content is substantively correct. | Invalid structure is blocked, verified effects are reported truthfully, and ordinary content remains open to user and Curator refinement. | Accepted |
| GRAPH-027 | `_compass/config.yaml` contains `schemaVersion: 2`, one stable UUID `graphId`, and one confirmed IANA `timezone`. | The graph remains identifiable across moves, readers select the correct schema contract, and Daily Log files use deterministic user-local dates. | Accepted |
| GRAPH-028 | Graph object filenames use readable lowercase kebab-case slugs derived from their titles; stable YAML IDs remain authoritative. | Users can recognize files by name, while title or filename changes do not change object identity or relationships. | Accepted |
| GRAPH-029 | A same-folder filename collision stops the affected write until the user selects a distinct filename. | Compass does not overwrite, merge objects, append an invented suffix, or treat equal title slugs as equal identity. | Accepted |
| GRAPH-030 | An archived Effort may retain a historical Activity metadata entry containing the Activity's stable ID, title, `lastActivityAt`, optional `startedAt`, participating Person references, concise customer-work summary, and minimized provenance. | Removing the Activity file does not erase the historical fact, customer significance, participants, or evidence grounding needed for later transparency. | Accepted |
| GRAPH-031 | Retained Activity metadata on an archived Effort is historical context, not a live Activity object or authoritative active relationship. | Graph readers do not resolve the retained entry as an existing Activity file or count it as current work. | Accepted |
| GRAPH-032 | An Activity file may be removed only after its Effort is archived, its required metadata is durably written and verified on that Effort, and the user explicitly authorizes removal. | A failed or unverifiable Effort update leaves the Activity file intact; successful removal leaves a readable historical entry and no dangling active reference. | Accepted |
| GRAPH-033 | Each Activity records timezone-explicit `lastActivityAt` from its newest meaningful supporting customer-work content; it may also record `startedAt` when the Activity spans a useful period. | Activity recency reflects when the customer work occurred, not when Compass retrieved, summarized, indexed, moved, or edited the file. | Accepted |
| GRAPH-034 | An Effort's last Activity is derived as the greatest reliable `lastActivityAt` among its live Activities and retained archived Activity metadata. | Curator can calculate Effort inactivity without storing a competing mutable Effort timestamp or treating a maintenance edit as customer work. | Accepted |

## Skills and orchestration

| Component | Responsibility | Inputs and outputs | Authority |
| --- | --- | --- | --- |
| Any Compass Skill that reads or writes the graph | Honor the accepted graph contract and preserve unsupported or user-authored content. | Portable Markdown/YAML objects in OneDrive. | A Skill may change only content within its accepted responsibility and user authority. |

## Interaction and information

| Element | Contract |
| --- | --- |
| Customer Success Plan | Durable customer outcome and strategic context represented by stable identity, title, and narrative. |
| CSP-to-Effort relationship | The Effort owns the optional forward reference to one CSP; a CSP's Efforts are derived from those references. |
| CSP lifecycle | No managed CSP status is currently part of the graph contract. |
| Effort | Durable work context represented by stable identity, title, lifecycle status, attention state, optional success, optional tags, optional review marker, optional narrative, optional CSP reference, included or excluded Person references, and archived Activity metadata when applicable. |
| Effort lifecycle | `active` or `archived`; success is recorded only when its defined condition applies. |
| Effort attention | Exactly one of `action`, `waiting`, or `observing`. |
| Effort-to-Person relationship | The Effort owns unique and disjoint included and excluded Person references; reverse Person relationships are derived. |
| Conversation or Activity | Durable interpretation of one meaningful unit of customer work, represented by stable Compass identity, title, concise factual account, timezone-explicit `lastActivityAt`, optional `startedAt`, participating People, one Effort or Parking Lot disposition, and minimized provenance when source-derived. |
| Activity continuity | Coherent customer work determines whether new evidence refines an existing Activity or forms another one; source containers inform but never dictate that decision. |
| Archived Activity metadata | Historical entry on an archived Effort containing stable Activity ID, title, `lastActivityAt`, optional `startedAt`, participating People, concise customer-work summary, and minimized provenance after the Activity file is removed. |
| Effort last Activity | Derived maximum reliable `lastActivityAt` across the Effort's live Activities and retained archived Activity metadata; no file or Daily Log modification timestamp substitutes for it. |
| Person | Durable relationship context represented by stable identity, meaningful first and last names, and optional reviewed normalized email addresses. |
| Person reverse relationships | Related Efforts and Conversations are derived from their Person references rather than stored as authoritative lists on the Person. |
| Daily Log | One user-local-date Markdown file containing minimal structured entries for accepted graph changes. |
| Daily Log entry | Timestamp, object type, stable object ID, and change type; no required narrative or relationship duplication. |
| Shared object header | YAML `schemaVersion`, `type`, stable `id`, non-empty `title`, and immutable `createdAt`, followed by object-specific Markdown content. |
| Managed update | Change only accepted managed fields or content while preserving unrecognized frontmatter and user-authored Markdown. |
| Graph root | `_compass/config.yaml` plus `CSPs/`, `Efforts/`, `People/`, `Conversations/`, and `Daily Logs/` object-type folders. |
| Graph configuration | YAML schema version, stable UUID graph identity, and confirmed IANA timezone; it is configuration rather than a Markdown graph object. |
| Object filename | Human-readable lowercase kebab-case title slug used as a transport label, never as graph identity. |

## Canonical serialization

This section is the normative schema for every Compass graph writer. Examples show field shape, not literal IDs or content. Object IDs use `<type>:<UUID>` with a lowercase type prefix and an RFC 4122 UUID. References always contain stable object IDs, never filenames or paths. Optional fields are omitted when they have no value; writers do not serialize placeholder strings or `null` unless a field explicitly permits it.

### Graph configuration

```yaml
schemaVersion: 2
graphId: 3f71e87e-b8b8-4e62-9d85-56c09e97d2c8
timezone: America/Los_Angeles
```

The file is `_compass/config.yaml`. `graphId` is an unprefixed UUID because it identifies the graph rather than a graph object. `timezone` is a confirmed IANA timezone name.

### Customer Success Plan

```yaml
---
schemaVersion: 2
type: csp
id: csp:11111111-1111-4111-8111-111111111111
title: Contoso identity outcomes
createdAt: 2026-09-12T16:00:00Z
---

Customer outcome and strategic-context narrative.
```

A CSP has no managed status, Effort list, or reverse relationship fields.

### Effort

```yaml
---
schemaVersion: 2
type: effort
id: effort:22222222-2222-4222-8222-222222222222
title: Conditional Access rollout
createdAt: 2026-09-12T16:01:00Z
status: active
attentionState: action
cspId: csp:11111111-1111-4111-8111-111111111111
participantIds:
	- person:33333333-3333-4333-8333-333333333333
excludedParticipantIds: []
tags:
	- identity
reviewBullet: true
---

Current purpose, context, progress, constraints, and next useful action.
```

`cspId`, `participantIds`, `excludedParticipantIds`, `tags`, and `reviewBullet` are optional. Arrays are unique; participant arrays are disjoint. `success` is omitted while active and is a required boolean when Curator archives the Effort. An archived Effort may also contain `archivedActivities` as defined below.

### Person

```yaml
---
schemaVersion: 2
type: person
id: person:33333333-3333-4333-8333-333333333333
title: Jordan Lee
createdAt: 2026-09-12T16:02:00Z
firstName: Jordan
lastName: Lee
emailAddresses:
	- jordan.lee@example.invalid
---

Optional user-authored relationship context.
```

`emailAddresses` is optional, unique after case-insensitive normalization, and stored only after user review. Email is not identity, and Compass does not store or infer a user principal name.

### Conversation or Activity

```yaml
---
schemaVersion: 2
type: conversation
id: conversation:44444444-4444-4444-8444-444444444444
title: Access-policy rollout decision
createdAt: 2026-09-12T16:03:00Z
lastActivityAt: 2026-09-12T15:47:00Z
startedAt: 2026-09-10T18:20:00Z
participantIds:
	- person:33333333-3333-4333-8333-333333333333
effortId: effort:22222222-2222-4222-8222-222222222222
provenance:
	- system: microsoft-365
		sourceType: email
		sourceRef: minimized-stable-reference
		observedThrough: 2026-09-12T15:47:00Z
---

Concise factual account of what happened, why it matters to the customer, and supported progress, decisions, risks, commitments, outcomes, or next steps.
```

`startedAt` is optional. `participantIds` is a unique array. Exactly one of `effortId` or `disposition: parking-lot` is present. `provenance` is optional for direct user input and otherwise contains one or more minimized source descriptors; it does not retain raw message text. `sourceRef` identifies supporting evidence sufficiently for later inspection without becoming Activity identity. `observedThrough` records the latest item boundary actually considered for that source and does not replace `lastActivityAt`.

### Archived Activity metadata

Curator appends entries under `archivedActivities` on an archived Effort before an Activity file can be removed:

```yaml
archivedActivities:
	- id: conversation:44444444-4444-4444-8444-444444444444
		title: Access-policy rollout decision
		lastActivityAt: 2026-09-12T15:47:00Z
		startedAt: 2026-09-10T18:20:00Z
		participantIds:
			- person:33333333-3333-4333-8333-333333333333
		summary: Customer approved the staged rollout and named the next validation step.
		provenance:
			- system: microsoft-365
				sourceType: email
				sourceRef: minimized-stable-reference
				observedThrough: 2026-09-12T15:47:00Z
```

`startedAt` and `provenance` are optional under the same rules as the live Activity. The entry is historical metadata, not an object or active relationship.

### Daily Log

The file path is `Daily Logs/YYYY-MM-DD.md`, where the date is derived in the configured timezone.

```yaml
---
schemaVersion: 2
type: daily-log
id: daily-log:2026-09-12
title: 2026-09-12
createdAt: 2026-09-12T16:04:00Z
date: 2026-09-12
changes:
	- timestamp: 2026-09-12T16:04:00Z
		objectType: conversation
		objectId: conversation:44444444-4444-4444-8444-444444444444
		changeType: created
---
```

`changes` is an append-only array for the managed date. Each entry contains exactly the four metric facts shown. `changeType` is a concise lowercase-kebab value such as `created`, `updated`, `moved`, `archived`, `activity-metadata-retained`, or `removed`.

## Required write procedure

Every Skill that proposes a graph mutation follows this order:

1. Read and validate `_compass/config.yaml`, then enumerate only the object files needed for the authorized operation.
2. Parse YAML and Markdown structurally. Preserve stable IDs, immutable `createdAt`, unrecognized frontmatter, and user-authored Markdown.
3. Resolve references by stable ID and validate type, cardinality, uniqueness, disposition, timestamp, filename, and lifecycle rules before presenting effects.
4. Present exact creates, updates, moves, archives, or removals and obtain the authority required by the responsible Skill.
5. Re-read every target immediately before mutation and stop the affected operation on changed or unsafe state.
6. Apply the authorized object changes without rewriting unrelated content.
7. Append one Daily Log change entry for each durable object effect using the configured timezone for the log date.
8. Read back every affected object and Daily Log, validate the resulting graph independently of the attempted operations, and report only verified effects.

Governor applies the validation portions of this procedure before and after mutation. It does not supply missing user intent, decide customer meaning, or grant another Skill authority.

## Constraints and dependencies

- The authoritative graph uses Markdown and YAML files in the user's OneDrive.
- Skill Host read and write behavior remains unverified.

## Failure, partial, blocked, and cancellation behavior

- A proposed Effort relationship to multiple CSPs is invalid and must not be written.
- A Skill must not infer or create an authoritative CSP reverse relationship list.
- Unsupported lifecycle or attention values and overlapping included/excluded Person references are invalid and must not be written.
- A Conversation with no material customer connection, multiple Efforts, no Effort or Parking Lot disposition, duplicate participants, or ambiguous Activity continuity is invalid and must not be written or automatically merged.
- Missing meaningful Person names or ambiguous identity blocks automatic Person creation or correlation.
- A Daily Log entry missing any required metric fact is incomplete and must not support a success claim for that indexed change.
- Missing or invalid shared header fields block the affected object write or update.
- Content that prevents safe parsing blocks the affected update; Compass does not overwrite it to force conformance.
- A file in an unexpected location or an ambiguous duplicate stable ID blocks automatic correlation or mutation until resolved.
- A duplicate filename slug blocks the affected creation or rename until the user chooses a distinct filename.
- Missing, invalid, or ambiguous graph configuration blocks installation completion and date-dependent writes.
- Unparseable identity or ambiguous CSP references block the affected relationship change.
- Missing or unverified required Activity metadata blocks removal of the corresponding Activity file.
- Activity removal from an active Effort or removal without explicit user authority is invalid.
- A partial archive or removal must preserve remaining Activity files and report the exact completed and blocked effects.
- Missing, conflicting, future-dated, timezone-ambiguous, or weakly inferred Activity timestamps block a confident stale classification for the affected scope.

## Decisions and open questions

- **Accepted:** CSPs represent durable customer outcomes and strategic context.
- **Accepted:** CSPs have stable identity, title, and narrative, no managed status, and no authoritative reverse Effort list.
- **Accepted:** Efforts retain the archived Tracking Topic field contract under the canonical Effort name.
- **Accepted:** Conversations are customer-work Activities whose boundaries follow coherent work rather than source containers; they retain stable Compass identity, participants, provenance, and Effort-or-Parking-Lot disposition.
- **Accepted:** People use stable identity, meaningful first and last names, optional reviewed normalized email addresses, and derived reverse relationships.
- **Accepted:** Daily Logs use one local-date file and minimal per-change entries for graph-activity metrics.
- **Accepted:** Every object uses the shared identity header, common formatting conventions, and preservation behavior.
- **Accepted:** The graph uses object-type folders with `Efforts/` as the canonical work-object folder, and paths remain distinct from identity.
- **Accepted:** Source-derived fragments become inspectable working knowledge; Governor validates integrity and Curator supports organization and refinement.
- **Accepted:** Graph configuration contains only schema version 2, stable UUID graph ID, and confirmed IANA timezone.
- **Accepted:** Object filenames use readable lowercase kebab-case title slugs while stable YAML IDs remain authoritative.
- **Accepted:** Same-folder filename collisions require a user-selected distinct filename.
- **Accepted:** Archived Efforts retain essential metadata for stale Activities whose files the user authorizes Curator to remove.
- **Accepted:** Retained Activity metadata preserves history but does not impersonate a live Activity object or active relationship.
- **Accepted:** Meaningful customer-work content determines Activity recency; retrieval and graph-maintenance events do not.

## Implementation status

- **Implemented:** Canonical schema and write procedure; packaged runtime contracts for Installation, Activity Scan, Graph Governor, and Curator; and a synthetic example graph.
- **Not implemented:** Verified Cowork file behavior, connected graph effects, and migration.

## Test Plans

- [`../test-plans/installation-interview.md`](../test-plans/installation-interview.md): Exercises CSP creation and Effort alignment during installation.
- [Activity Scan Test Plan](../test-plans/activity-scan.md): Exercises Activity and Person updates plus Daily Log effects.
- [Graph Governor Test Plan](../test-plans/graph-governor.md): Exercises schemas, relationships, preservation, and effect validation.
- [Curator Lifecycle Test Plan](../test-plans/curator-lifecycle.md): Exercises archived Activity metadata and removal invariants.

## Revision history

| Version | Date | Change and reason |
| --- | --- | --- |
| 0.1 | 2026-09-11 | Created the graph contract and accepted the CSP object after object-by-object review. |
| 0.2 | 2026-09-11 | Accepted the archived Tracking Topic contract as the Effort object contract. |
| 0.3 | 2026-09-11 | Accepted the archived source-grounded Conversation object contract with Effort terminology. |
| 0.4 | 2026-09-11 | Accepted the Person identity and email contract using positive managed-field guidance and derived reverse relationships. |
| 0.5 | 2026-09-11 | Replaced the archived Daily Log detail with a minimal graph-activity metric contract. |
| 0.6 | 2026-09-11 | Accepted the shared object header, stable identity, formatting, and user-content preservation contracts. |
| 0.7 | 2026-09-11 | Accepted the object-type OneDrive folder layout with `Efforts/` replacing `Tracking Topics/`. |
| 0.8 | 2026-09-11 | Added provisional and accepted knowledge states and separated structural governance from user-controlled formalization. |
| 0.9 | 2026-09-11 | Accepted the graph configuration baseline: schema version 2, stable UUID graph ID, and confirmed IANA timezone. |
| 0.10 | 2026-09-11 | Accepted readable lowercase kebab-case title-slug filenames with stable YAML identity. |
| 0.11 | 2026-09-11 | Required user-selected filenames when readable title slugs collide. |
| 1.0 | 2026-09-12 | Activated the graph contract and removed the provisional/accepted state machine in favor of inspectable working knowledge refined over time. |
| 1.1 | 2026-09-12 | Redefined Conversation as customer-work Activity and replaced one-source-container identity with coherent-activity boundaries and minimized provenance. |
| 1.2 | 2026-09-12 | Added archived Activity metadata and preserve-before-remove integrity rules for Curator lifecycle maintenance. |
| 1.3 | 2026-09-12 | Added Activity work-time fields and derived Effort last Activity so Curator's 14-day review does not confuse maintenance with customer work. |
| 1.4 | 2026-09-12 | Defined canonical YAML shapes, stable ID syntax, provenance and archive fields, Daily Log serialization, and the required graph-write procedure. |

## Acceptance boundary

This active Specification authorizes local implementation and disconnected validation of the graph contract. It does not authorize migration, establish Skill Host compatibility, or permit connected OneDrive writes, packaging, deployment, or release.