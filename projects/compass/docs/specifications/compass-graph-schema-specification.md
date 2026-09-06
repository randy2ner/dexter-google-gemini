# Compass Graph Schema Specification

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

This document defines the minimum accepted Markdown and YAML frontmatter schemas that the complete Compass beta candidate will share and Graph Governor will validate.

The first Beta covers five durable object types:

- Conversation;
- Tracking Topic;
- CSP; and
- Person; and
- Daily Log.

Daily Log write semantics are defined in the Shared Contracts Specification. This document defines the corresponding Daily Log frontmatter and managed-section schema. Item-level evidence records remain deferred. This specification defines graph representation and validation expectations, not Skill implementation or permission to write a real graph. The disposable-beta recovery protocol is behavioral and defined by the Shared Contracts Specification; its snapshot and operation-evidence representation remains outside this schema version.

## 2. Governing contracts

This specification is subordinate to:

1. the [Compass Vision and Scope Charter](../charter/compass-vision-and-scope-charter.md);
2. the [Compass Shared Contracts Specification](compass-shared-contracts-specification.md); and
3. the [Graph Governor Skill Specification](graph-governor-skill-specification.md).

The charter is the governing expression of the user's vision. Imported source material may inform review but does not define this schema.

## 3. Representation rules

### 3.1 File format

Each managed object is represented by a Markdown file with YAML frontmatter. The Markdown body remains readable and editable outside Compass.

```markdown
---
# Compass-managed and user/plugin frontmatter
---

# Human-readable Markdown
```

### 3.2 Field naming

Compass-managed frontmatter uses `camelCase`.

### 3.3 Timestamps

Machine-managed timestamps use timezone-explicit UTC ISO 8601 values, for example `2026-08-28T14:30:00Z`.

### 3.4 Stable identity

- Every object has a stable Compass `id`.
- The `id` survives title, filename, and folder changes.
- Display names, titles, filenames, and wiki-link labels are not identity.
- The exact ID-generation format remains an implementation decision.

### 3.5 Frontmatter ownership

Compass validates and modifies only accepted Compass-managed fields. Unknown frontmatter fields and unmanaged Markdown content are preserved unchanged.

Unknown fields do not fail validation merely because Graph Governor does not recognize them. A field fails only when it conflicts with an accepted Compass-managed field or prevents safe parsing and preservation.

## 4. Common object contract

Every managed object requires:

```yaml
---
schemaVersion: 1
type: conversation
id: <stable-compass-id>
title: <human-readable-title>
createdAt: 2026-08-28T14:30:00Z
---
```

| Field | Type | Required | Contract |
| --- | --- | --- | --- |
| `schemaVersion` | positive integer | Yes | Identifies the schema used to validate and evolve the object. |
| `type` | closed string value | Yes | One of `conversation`, `tracking-topic`, `csp`, `person`, or `daily-log` in the first Beta. |
| `id` | string | Yes | Globally unique, stable Compass object identity. |
| `title` | non-empty string | Yes | Human-readable label; not identity. |
| `createdAt` | UTC ISO 8601 timestamp | Yes | Time the durable Compass object was created; immutable after creation. |

A universal `modifiedAt` field is not required in the first Beta. Graph modification time and meaningful work activity must not be conflated before last-activity testing is complete.

## 5. Conversation schema

### 5.1 Minimum candidate frontmatter

```yaml
---
schemaVersion: 1
type: conversation
id: <stable-compass-id>
title: <human-readable-title>
createdAt: 2026-08-28T14:30:00Z
sourceSystem: microsoft-365
sourceType: chat
sourceConversationId: <durable-source-conversation-id>
activeParticipantIds:
  - <person-id>
trackingTopicId: <tracking-topic-id>
---
```

### 5.2 Conversation fields

| Field | Type | Required | Contract |
| --- | --- | --- | --- |
| `sourceSystem` | closed string value | Yes | `microsoft-365` in the first Beta. |
| `sourceType` | closed string value | Yes | `chat` or `email`. |
| `sourceConversationId` | string | Yes | Durable source-system structural truth grouping all activity under this Conversation. |
| `activeParticipantIds` | unique list of Person IDs | Yes | People observed authoring at least one processed email or chat item under the source Conversation ID. An empty list is valid until evidence is processed. |
| `trackingTopicId` | Tracking Topic ID | No | The Conversation's zero-or-one authoritative Topic alignment. Absence places it in the Parking Lot projection. |

### 5.3 Structural source identity

The tuple below is the source-correlation key:

```text
sourceSystem + sourceType + sourceConversationId
```

Graph Governor validates that:

- a source Conversation ID is present;
- an item or message ID is not knowingly substituted for it;
- activity with the same source-correlation key maps to the existing Conversation;
- a different source-correlation key is not merged by title, participants, timing, or semantic similarity alone; and
- no conflicting active Conversation files claim the same source-correlation key.

The stable Compass `id` identifies the graph object. The source-correlation key determines which source activity belongs under that Conversation umbrella. Their mapping must remain explicit.

### 5.4 Active participants

An active participant is a Person who authored at least one processed source item under the durable source Conversation ID.

- Passive recipients or listed chat members are excluded until they author an observed item.
- Reactions alone do not establish active participation in the first Beta.
- `activeParticipantIds` accumulates unique observed authors as Compass processes additional activity.
- A current scan must not remove a previously observed active participant merely because that person did not author an item during the scan window.
- Participant count is derived as the number of unique `activeParticipantIds`; it is not stored as a second authoritative value.
- Every listed Person ID must resolve to a valid Person object.

### 5.5 Evidence details

Whether Conversation frontmatter should retain item-level email or chat references is deliberately deferred for scenario testing. Tests should compare:

- traceability and source recovery;
- privacy and data minimization;
- ability to determine active participants;
- ability to calculate meaningful last activity; and
- cost or reliability of retrieving source activity again.

No first-Beta schema field for item-level references is accepted by this draft.

### 5.6 Conversation last activity

No authoritative Conversation last-activity field is defined yet. Scenario tests must determine whether meaningful recency is represented by:

- latest processed source activity;
- latest available source activity;
- latest graph modification; or
- separate timestamps for source activity and graph modification.

Graph Governor must not treat maintenance edits as meaningful work activity unless a later accepted contract explicitly does so.

### 5.7 Conversation staleness and deletion

Staleness is derived from a future accepted last-activity and retention rule; it is not a stored lifecycle state in the first Beta. Becoming stale does not automatically modify, archive, or delete a Conversation.

A stale Conversation may be deleted only after explicit user review and approval of the exact Conversation or an explicitly bounded set. The deletion contract must account for affected Topic membership, Person relationships, provenance, and any historical references before Graph Governor permits it. The first Beta may identify deletion candidates but does not receive independent deletion authority.

## 6. Tracking Topic schema

### 6.1 Minimum candidate frontmatter

```yaml
---
schemaVersion: 1
type: tracking-topic
id: <stable-compass-id>
title: <human-readable-title>
createdAt: 2026-08-28T14:30:00Z
status: active
cspId: <csp-id>
---
```

### 6.2 Tracking Topic fields

| Field | Type | Required | Contract |
| --- | --- | --- | --- |
| `status` | closed string value | Yes | `active` or `archived`. |
| `cspId` | CSP ID | No | The Topic's zero-or-one authoritative CSP alignment. |

### 6.3 Lifecycle

- `active` means the Topic currently participates in the user's work-memory practice.
- `archived` means the Topic is retained for history but no longer actively participates.
- Archival preserves the Topic file and historical relationships.
- Reactivation changes `archived` back to `active` through an authorized operation.
- A Tracking Topic is never deleted; staleness may support an archival recommendation but cannot trigger an automatic state change.
- No `paused`, `watching`, `completed`, or deleted state is accepted.

### 6.4 Derived Conversation membership

A Tracking Topic does not store an authoritative list of Conversation IDs. Its aligned Conversations are derived by querying Conversation files whose `trackingTopicId` equals the Topic's `id`.

Reports and the Tracking Topic Interview may use the derived list and the associated Conversation context without creating a duplicate source of relationship truth.

### 6.5 Topic last activity

No authoritative Topic last-activity field is defined yet. Candidate inputs are:

- meaningful source activity from currently aligned Conversations; and
- meaningful engagement through the Tracking Topic Interview Skill.

Scenarios must determine whether these inputs create one combined value or separate concepts such as latest work activity and latest Topic engagement.

## 7. CSP schema

### 7.1 Minimum candidate frontmatter

```yaml
---
schemaVersion: 1
type: csp
id: <stable-compass-id>
title: <human-readable-title>
createdAt: 2026-08-28T14:30:00Z
---
```

### 7.2 Stability contract

A CSP is a stable North Star representing a durable customer outcome, strategic objective, or business priority. It is generally not treated as an attainable work item with a routine lifecycle state.

Therefore:

- CSP does not require `status` in the first Beta;
- Tracking Topics own their optional CSP alignment through `cspId`;
- CSP Topic membership is derived by querying Tracking Topics;
- ordinary Topic lifecycle changes do not mutate CSP identity; and
- retirement, replacement, or removal of a CSP requires a later explicit contract rather than an inferred status transition.

## 8. Person schema

### 8.1 Minimum candidate frontmatter

```yaml
---
schemaVersion: 1
type: person
id: <stable-compass-id>
title: <preferred-display-name>
createdAt: 2026-08-28T14:30:00Z
userPrincipalName: <optional-upn>
emailAddresses:
  - <optional-normalized-email-address>
identityState: confirmed
---
```

### 8.2 Person fields

| Field | Type | Required | Contract |
| --- | --- | --- | --- |
| `userPrincipalName` | string | No | Microsoft 365 UPN when available; an attribute and correlation signal, not the Compass object ID. |
| `emailAddresses` | unique list of strings | No | Known normalized email addresses; may support external-participant correlation. |
| `identityState` | closed string value | Yes | `confirmed` or `provisional`. |

### 8.3 Person identity

- The Compass `id` is the authoritative graph identity for a Person.
- A UPN or email address may establish or support source correlation when the Person participates in a Conversation.
- A Person may also be worth tracking when mentioned by name and determined to be involved, even if that Person has not authored observed activity.
- A display name alone must not silently merge two Person objects.
- A Person inferred only from contextual mention remains `provisional` until the user or sufficiently authoritative evidence resolves the identity.
- When no stable Microsoft 365 directory identity is available for an external active sender, a normalized email address may be used as the source-correlation fallback while Compass retains its own stable Person ID.
- If later evidence reveals that two Person records represent the same individual, merging them is a consequential user-approved operation.

### 8.4 Conversation relationship categories

The first Beta distinguishes:

- **active participant:** authored at least one processed source item and appears in Conversation `activeParticipantIds`; and
- **contextually involved Person:** mentioned or otherwise relevant but not necessarily an observed author.

Whether Conversations should store a separate `involvedPersonIds` field is open for scenario review. Graph Governor must not place a contextually mentioned Person in `activeParticipantIds` without observed authorship.

## 9. Daily Log schema

### 9.1 Minimum frontmatter

```yaml
---
schemaVersion: 1
type: daily-log
id: daily-log:2026-08-28
title: 2026-08-28
createdAt: 2026-08-28T23:15:00Z
date: 2026-08-28
---
```

| Field | Type | Required | Contract |
| --- | --- | --- | --- |
| `date` | ISO 8601 calendar date | Yes | User-local date represented by this log. |

The Daily Log `id` is deterministically `daily-log:<date>`. Exactly one managed Daily Log may claim a given date. `title` should equal the date unless a later presentation convention is accepted.

The user's timezone is required input to date assignment but is not duplicated in each Daily Log. It belongs in accepted Compass configuration. Graph Governor blocks automatic date assignment when that configured timezone or the source timestamp is unavailable or ambiguous.

### 9.2 Managed-section boundary

Compass-generated content is enclosed by one pair of exact HTML comment markers:

```markdown
<!-- compass:daily-log-index:start -->

## Compass Activity

<!-- Compass-managed activity index appears here. -->

<!-- compass:daily-log-index:end -->
```

- Compass owns only the content between these markers.
- Content before and after the markers is user-authored and must remain unchanged.
- Unknown frontmatter remains preserved under the general frontmatter-ownership contract.
- Missing, duplicated, nested, reversed, or malformed markers block automatic replacement and require guided resolution.
- Marker text appearing inside a fenced code block is not a managed boundary.
- Compass must not move user-authored text into the managed region or absorb adjacent sections while rewriting it.

### 9.3 Managed index organization

The managed index uses object-type sections in this order when they contain entries:

1. Conversations;
2. Tracking Topics;
3. CSPs; and
4. People; and
5. Configuration.

Each object appears once in its section, keyed by stable Compass object ID. Under that object is a chronological history of the authorized actions assigned to this Daily Log date.

```markdown
<!-- compass:daily-log-index:start -->

## Compass Activity

### Conversations

#### [Contoso deployment review](../Conversations/contoso-deployment-review.md) (`conversation:<id>`)

- **14:30 — updated** — Added approved activity summary. _Daily Scan `0.1.0-beta.1`_
- **16:10 — aligned** — Aligned to Production readiness. _Tracking Topic Interview `0.1.0-beta.1`_

### Tracking Topics

#### [Production readiness](../Tracking%20Topics/production-readiness.md) (`tracking-topic:<id>`)

- **16:10 — updated** — Added the approved Conversation alignment. _Tracking Topic Interview `0.1.0-beta.1`_

<!-- compass:daily-log-index:end -->
```

The example paths and version values are illustrative, not accepted filename or package conventions.

### 9.4 Managed entry contract

Every graph-object entry contains:

- a readable object title;
- its stable Compass object ID;
- a navigational link when the object still exists; and
- one or more authorized action records for the represented date.

Every action record contains:

- relevant activity or action time;
- accepted operation label;
- concise change summary; and
- initiating Skill name and version.

The first-Beta operation labels are:

| Label | Meaning |
| --- | --- |
| `created` | A new durable graph object was added. |
| `updated` | Existing durable content changed without a more specific accepted label. |
| `aligned` | A Conversation-to-Topic or Topic-to-CSP relationship was established or changed. |
| `unaligned` | An existing Conversation-to-Topic or Topic-to-CSP relationship was removed. |
| `archived` | A Tracking Topic moved from `active` to `archived`. |
| `reactivated` | A Tracking Topic moved from `archived` to `active`. |
| `deleted` | A Conversation was deleted after explicit user review and approval. |

The displayed action time uses the user's configured local timezone. Exact UTC time, stable operation ID, date basis, and authority reference must remain available to Graph Governor in the validated operation record even when they are not displayed in the Daily Log.

Configuration entries use the stable graph ID in place of an object ID and do not expose complete configuration values. They identify only the setting category and a concise safe description, such as a confirmed timezone change.

### 9.5 Ordering and deduplication

- Object entries are ordered by their most recent action time, newest first, then by stable object ID for deterministic ties.
- Actions under an object are ordered chronologically, oldest first, so the object's day history can be read in sequence.
- Every authorized graph update has a stable operation ID shared by its graph-object and Daily Log effects.
- Reprocessing an action with the same operation ID updates the existing action rather than duplicating it.
- A later distinct action against the same object is appended to that object's action history rather than creating a second object entry.
- Similar titles do not merge entries with different stable IDs.

### 9.6 Backdated and undated updates

- Source-grounded updates use the user-local date of source activity.
- Processing older activity updates the older date's Daily Log.
- An authorized graph update without a source-activity date uses the user-local date of the authorized action.
- Processing and approval timestamps may be retained in operation evidence but do not move source-grounded activity to a later Daily Log.

### 9.7 Deleted Conversation tombstone

When the user explicitly approves deletion of a stale Conversation, the Daily Log retains a non-navigational tombstone rather than a broken link:

```markdown
#### Contoso deployment review (`conversation:<id>`) — deleted

- **17:00 — deleted** — Removed after explicit stale-retention review: <approved concise reason>. _<initiating Skill and version>_
```

The tombstone preserves the stable ID, former title, deletion time, concise approved reason, and initiating Skill/version. It does not preserve deleted Conversation content or pretend the object remains navigable.

Deleting a Conversation does not remove its prior Daily Log history. Tracking Topics never receive deletion tombstones because Tracking Topics are never deleted.

## 10. Graph-level configuration schema

### 10.1 Location and minimum schema

Shared Compass settings live in one machine-readable file at `_compass/config.yaml`, separate from user-facing knowledge objects.

```yaml
schemaVersion: 1
graphId: 2f1c7f44-8858-4e61-a763-12a62ac93c15
timezone: America/Los_Angeles
```

| Field | Type | Required | Contract |
| --- | --- | --- | --- |
| `schemaVersion` | positive integer | Yes | Identifies the configuration schema. |
| `graphId` | lowercase UUID v4 string | Yes | Stable identity distinguishing this graph from another vault or test fixture. |
| `timezone` | IANA timezone name | Yes after confirmation | Authoritative user timezone for Daily Log date assignment and local-time display. |

The first configuration contains no owner identity, locale, or graph creation timestamp. Unknown fields are preserved but have no Compass meaning until added by an accepted schema version.

#### 10.1.1 Stable graph identity

`graphId` uses the canonical lowercase UUID v4 text form `xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx`, where `y` is `8`, `9`, `a`, or `b`. It has no prefix, braces, or URN wrapper.

Compass generates the value once with a cryptographically secure UUID v4 generator during graph bootstrap. It remains unchanged when the graph is renamed, moved, synchronized, restored from backup, or opened on another device. A deliberately independent graph or test fixture receives a new value; an exact backup or synchronized replica retains the original value. Compass does not derive this identifier from a path, tenant, account, owner, title, or other personal or mutable data.

After bootstrap, changing an established `graphId` is an identity violation even when the replacement is syntactically valid. Graph Governor preserves the edit, blocks dependent writes, and guides explicit recovery or creation of an independent graph rather than silently restoring or accepting the value.

### 10.2 Direct user edits

The user may edit `_compass/config.yaml` directly. A valid direct edit is authoritative after Graph Governor validates the configuration before dependent use.

An invalid or changed established `graphId`, invalid `schemaVersion`, or invalid configured timezone blocks dependent writes. Read-only inspection and guided resolution remain available. Compass must not silently replace an invalid user value with a default.

### 10.3 Temporary Microsoft 365 timezone

When the stored timezone is missing or invalid but Microsoft 365 exposes a valid timezone for the signed-in user, Compass may temporarily use that value before it is confirmed and stored.

Before a write, Compass must:

1. display the retrieved IANA timezone or its verified IANA mapping;
2. disclose that date assignment is provisional;
3. retain the temporary timezone and its source in operation evidence; and
4. invite the user to confirm or correct the graph configuration.

The fallback does not silently modify `_compass/config.yaml`. If neither a valid configured timezone nor a valid Microsoft 365 timezone is available, writes requiring Daily Log assignment are blocked.

#### 10.3.1 Deterministic timezone verification and mapping

Compass resolves a Microsoft 365 timezone as follows:

1. Preserve the exact retrieved value and source field in operation evidence.
2. If the value exactly matches a timezone in the implementation's pinned IANA Time Zone Database release, use that IANA name.
3. Otherwise, treat the value as a Windows timezone ID and resolve it through a pinned Unicode CLDR `windowsZones.xml` release.
4. Use the mapping for the user's authoritative Microsoft 365 country or region only when that value is available and the CLDR entry yields one deterministic IANA result. Otherwise, use the CLDR global territory `001` mapping.
5. Block date-dependent writes when the value is unknown, the required mapping is absent, or the selected entry does not yield one deterministic result.

Compass does not infer a timezone from a UTC offset, display label, language, device location, filename, or fuzzy string match. Operation evidence records the raw value, resolved IANA name, source field, selected territory, and pinned CLDR and IANA database versions.

This mapping rule is a specification decision, not a tested capability claim. Before implementation confidence is assigned, fixtures must cover direct IANA values, Windows IDs using global and territory mappings, aliases, unknown values, ambiguous results, and dates on both sides of daylight-saving transitions. The result record must identify the exact CLDR and IANA database releases exercised.

#### 10.3.2 Provisional-use limit

A retrieved timezone may be used provisionally for at most one authorized write set. Compass must require confirmation or correction before another date-dependent write and before setup can be reported complete. The limit is operation-based rather than elapsed-time-based so it remains enforceable across interrupted or stateless Cowork sessions.

Reprocessing, retrying, or recovering the same stable operation ID does not create a second allowance. A different operation ID is a subsequent write and is blocked until `_compass/config.yaml` contains a confirmed valid IANA timezone. Read-only inspection and previews remain available.

### 10.4 Timezone confirmation and changes

When the user confirms a timezone, Compass stores its IANA name through a validated, authorized configuration update.

- A later timezone change applies to future date assignments.
- Existing Daily Logs remain unchanged by default.
- If a confirmed timezone differs from a temporary value used for provisional entries, Compass identifies potentially affected dates and offers an explicit reviewed correction.
- Compass never silently moves historical or provisional entries between Daily Logs.

### 10.5 Bootstrap

Initial setup uses a bounded bootstrap sequence:

1. generate the stable `graphId` and create `_compass/config.yaml`;
2. retrieve, verify, display, and obtain confirmation or correction of the candidate IANA timezone;
3. validate the completed configuration;
4. use the confirmed timezone to select the installation date;
5. create the first Daily Log; and
6. record the configuration creation in the managed Configuration section.

Configuration creation and the first Daily Log are one setup workflow. Provisional timezone processing may prepare or attempt the bounded write set, but setup is not reported complete unless the timezone is confirmed and both artifacts validate.

### 10.6 Configuration activity

Later authorized configuration changes create a safe Daily Log action under the managed Configuration section, keyed by `graphId`.

The entry records the action time, `updated` label, concise setting category, and initiating Skill/version. It must not expose sensitive values. A timezone change may name the prior and new timezone because those values are necessary to understand date behavior and are not treated as secret by this schema.

## 11. Relationship validation

| Source object | Managed field | Target object | Cardinality | Authority |
| --- | --- | --- | --- | --- |
| Conversation | `trackingTopicId` | Tracking Topic | zero or one | Conversation owns the link. |
| Conversation | `activeParticipantIds` | Person | zero or many, unique | Conversation owns the observed-author links. |
| Tracking Topic | `cspId` | CSP | zero or one | Tracking Topic owns the link. |

Graph Governor validates that every present target exists and has the expected `type`. Reverse membership is derived and must not be treated as an independently authoritative list.

## 12. Beta-baseline Graph Governor checks

For every managed file, Graph Governor should check:

1. frontmatter delimiters and safe YAML parsing;
2. presence and type of common required fields;
3. allowed object `type`;
4. uniqueness and immutability of `id`;
5. valid UTC timestamp format for `createdAt`;
6. preservation of unknown frontmatter and unmanaged Markdown;
7. type-specific required fields and allowed values;
8. reference existence, target type, uniqueness, and cardinality;
9. Conversation source-correlation key presence and uniqueness;
10. separation of active authors from passive or contextually mentioned People; and
11. absence of duplicate authoritative reverse relationship lists in Compass-managed fields;
12. Daily Log date identity, marker integrity, stable-ID membership, ordering, and deduplication; and
13. preservation of user-authored Daily Log content outside the managed markers;
14. configuration schema, canonical UUID v4 graph identity, and valid IANA timezone;
15. deterministic timezone mapping with pinned CLDR and IANA database versions; and
16. disclosed, traceable, and operation-bounded use of any temporary Microsoft 365 timezone.

Graph Governor may report last-activity gaps but cannot enforce an unresolved last-activity derivation.

## 13. Deferred fields and schemas

The following are intentionally deferred:

- item-level evidence references;
- Conversation source-activity timestamp;
- graph modification timestamp;
- Topic latest work activity;
- Topic latest interview engagement;
- contextually involved Person relationship field;
- complete filename and folder conventions;
- exact Compass ID format;
- exact source Conversation ID encoding and normalization;
- CSP retirement or replacement behavior;
- transaction, recovery, and audit-record schemas; and
- Conversation stale-retention duration and last-activity derivation.

Deferral prevents an untested assumption from becoming a Graph Governor rule.

The disposable-beta recovery protocol in `SC-WRITE-005` does not establish a production transaction or audit-record schema. Its retained snapshot and operation evidence are test controls, not authoritative graph objects in schema version 1.

## 14. Required schema scenarios

### GS-BETA-001 — Minimal valid objects

Graph Governor accepts one minimal valid fixture for each of the five object types.

### GS-BETA-002 — Unknown field preservation

A file containing user or plugin frontmatter outside Compass's managed schema survives a Compass-managed change without loss or unintended rewriting.

### GS-BETA-003 — Stable object identity

Renaming a title or file does not change the Compass `id` or break valid references.

### GS-BETA-004 — Source Conversation identity

Activity with the same verified source-correlation key resolves to the existing Conversation; activity with a different key does not merge based on similarity.

### GS-BETA-005 — Active participant accumulation

New observed authors are added once, passive recipients are excluded, and authors absent from a later scan are not removed.

### GS-BETA-006 — Mentioned Person separation

A contextually mentioned Person may be represented without being falsely classified as an active participant.

### GS-BETA-007 — Derived Topic membership

A Topic report obtains its Conversation list from Conversation `trackingTopicId` values without requiring a stored reverse list.

### GS-BETA-008 — Derived CSP membership

A CSP report obtains its Topic list from Tracking Topic `cspId` values without requiring a stored reverse list.

### GS-BETA-009 — Archived Topic history

Changing a Topic from `active` to `archived` preserves the Topic and historical Conversation relationships.

### GS-BETA-010 — No CSP lifecycle inference

Graph Governor does not require or invent a CSP status field.

### GS-BETA-011 — Daily Log boundary preservation

Compass updates the generated index between one valid marker pair while preserving user-authored content before and after it byte-for-byte where the accepted writer permits.

### GS-BETA-012 — Daily Log deduplication and history

Repeated processing does not duplicate an object or action. A distinct later action accumulates under the existing object entry, with deterministic object and action ordering.

### GS-BETA-013 — Backdated Daily Log

An update grounded in older source activity appears in the older user-local date log rather than the processing-date log.

### GS-BETA-014 — Deleted Conversation tombstone

An explicitly approved Conversation deletion preserves a non-navigational Daily Log tombstone with stable identity and approved deletion context without retaining deleted content.

### GS-BETA-015 — Malformed managed markers

Missing, duplicated, nested, reversed, or malformed Daily Log markers block automatic index replacement and preserve the existing file for guided resolution.

### GS-BETA-016 — Valid graph configuration

Graph Governor accepts one `_compass/config.yaml` containing a supported schema version, stable graph ID, and valid IANA timezone.

### GS-BETA-017 — Temporary Microsoft 365 timezone

When configured timezone is unavailable, Compass discloses and records a valid retrieved Microsoft 365 timezone before using it provisionally. It does not silently write that value to configuration.

### GS-BETA-018 — Timezone mismatch

A later confirmed timezone differs from the temporary value. Existing Daily Logs remain unchanged, affected dates are reported, and any correction requires explicit review.

### GS-BETA-019 — Configuration bootstrap

Initial configuration and the installation-date Daily Log both validate before setup is reported complete, and the Daily Log contains a safe Configuration entry.

### GS-BETA-020 — Direct invalid configuration edit

An invalid direct edit blocks dependent writes without preventing read-only health inspection or overwriting the user's value.

### GS-BETA-021 — Stable graph ID

Bootstrap generates a canonical lowercase UUID v4 once. A rename, move, synchronized replica, or backup restoration retains it, while a deliberately independent graph or fixture receives a different value. Malformed and non-v4 identifiers are rejected.

### GS-BETA-022 — Deterministic timezone mapping

Pinned IANA and CLDR fixtures verify direct IANA values and deterministic Windows-ID mappings. Unknown, absent, fuzzy, offset-only, and ambiguous inputs block date-dependent writes. Evidence identifies the raw value, result, territory, source field, and exact data releases used.

### GS-BETA-023 — Provisional-use exhaustion

One provisional timezone supports at most one stable operation ID, including its retries or recovery. A second date-dependent operation is blocked until a valid IANA timezone is confirmed in configuration; read-only inspection remains available.

## 15. Deferred beta decisions

Runtime evidence must still prove that source Chat and Email Conversation IDs behave as required.

The following remain explicitly deferred and do not block baseline acceptance:

- item-level evidence records and context-only Person relationships;
- last-activity fields and stale-retention rules;
- complete filename conventions and type-specific Compass ID formats;
- exact source Conversation ID encoding and normalization;
- Person merge and CSP retirement behavior; and
- transaction, recovery, and audit-record schemas beyond the behavioral disposable-beta protocol.

## 16. Acceptance boundary

This is the accepted beta-baseline schema specification. It establishes schema version 1 as the design baseline and permits Slice B responsibility-specification work only.

It would not authorize Skill implementation, `.SKILL` packaging, Microsoft 365 access, creation or modification of a OneDrive graph, connected testing, deployment, publication, or release.
