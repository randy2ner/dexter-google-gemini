# Specification: Compass graph schema

## Document control

- **Status:** Accepted HPI narrative baseline
- **Project:** Compass
- **Version:** 0.7-hpi-narrative-baseline
- **Created:** 2026-08-28
- **Last updated:** 2026-09-08
- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Applies to Skills:** Compass Installation Interview, Compass Daily Scan, Compass Tracking Topic Interview, Compass Curator, Graph Governor
- **Approval:** Schema version 1 accepted on 2026-09-02; schema version 2 participant-management, archival-success, attention-state, and Person UPN removal revisions accepted on 2026-09-06; HPI narrative and review metadata accepted on 2026-09-08
- **Implementation authority:** HPI narrative documentation, Skill source, Orchestration, packaging, sample, and test updates authorized by the user on 2026-09-08

## 1. Purpose

This document defines the minimum accepted Markdown and YAML frontmatter schemas that Compass Skills share and Graph Governor validates. Schema version 2 adds intentional Conversation disposition, confirmed participant identity, persistent Topic participant management, a boolean success outcome for archived Topics, and explicit Topic attention state. The current schema-version-2 baseline removes UPN from managed Person data. Schema version 1 artifacts and completed evidence remain historical specimens and require an explicit migration before a schema-version-2 writer changes them.

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
schemaVersion: 2
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
schemaVersion: 2
type: conversation
id: <stable-compass-id>
title: <human-readable-title>
createdAt: 2026-08-28T14:30:00Z
sourceSystem: microsoft-365
sourceType: chat
sourceConversationId: <durable-source-conversation-id>
participantIds:
  - <person-id>
trackingTopicId: parking-lot
---
```

### 5.2 Conversation fields

| Field | Type | Required | Contract |
| --- | --- | --- | --- |
| `sourceSystem` | closed string value | Yes | `microsoft-365` in the first Beta. |
| `sourceType` | closed string value | Yes | `chat` or `email`. |
| `sourceConversationId` | string | Yes | Durable source-system structural truth grouping all activity under this Conversation. |
| `participantIds` | unique list of Person IDs | Yes | People who authored a processed item or were named in authored message content and then identity-confirmed by the user. An empty list is valid until qualifying evidence is accepted. |
| `trackingTopicId` | Tracking Topic ID or `parking-lot` | Yes | The Conversation's intentional disposition. A valid Topic ID aligns it; reserved value `parking-lot` retains it without Topic alignment. Missing, null, or empty values are invalid. |

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

### 5.4 Participants

Conversation participation is established only by accepted authored activity or an identity-confirmed name mention in authored message content.

- The initial author and every later author or responder qualify.
- A named mention qualifies only after the user confirms the intended identity. A first-name-only mention requires the user to provide or confirm the last name before Compass binds an existing Person or creates one.
- Passive email recipients and listed chat members are excluded until they author an observed item or are named in authored content and identity-confirmed.
- Reactions alone do not establish active participation in the first Beta.
- Signatures, quoted history, automated footers, disclaimers, and distribution-list names do not establish a mention.
- `participantIds` accumulates unique accepted participants as Compass processes additional activity.
- A current scan must not remove a previously accepted participant merely because that person was absent from the scan window.
- Participant count is derived from unique `participantIds`; it is not stored separately.
- Every listed Person ID resolves to a valid Person with meaningful `firstName` and `lastName`.

### 5.5 Intentional Topic disposition

Every Conversation stores exactly one `trackingTopicId` value. A Tracking Topic ID is a canonical relationship to that Topic. `parking-lot` is the sole reserved non-ID value and records an intentional decision to retain the Conversation without Topic alignment.

Parking Lot remains a derived view, not an object or sentinel Topic:

```text
Conversations where trackingTopicId == "parking-lot"
```

No Tracking Topic may use `parking-lot` as its object ID. Moving a Conversation to Parking Lot replaces its Topic ID with `parking-lot`; aligning it replaces `parking-lot` with the accepted Topic ID.

### 5.6 Evidence details

Whether Conversation frontmatter should retain item-level email or chat references is deliberately deferred for scenario testing. Tests should compare:

- traceability and source recovery;
- privacy and data minimization;
- ability to determine active participants;
- ability to calculate meaningful last activity; and
- cost or reliability of retrieving source activity again.

No first-Beta schema field for item-level references is accepted by this draft.

### 5.7 Conversation last activity

No authoritative Conversation last-activity field is defined yet. Scenario tests must determine whether meaningful recency is represented by:

- latest processed source activity;
- latest available source activity;
- latest graph modification; or
- separate timestamps for source activity and graph modification.

Graph Governor must not treat maintenance edits as meaningful work activity unless a later accepted contract explicitly does so.

### 5.8 Conversation staleness and deletion

Staleness is derived from a future accepted last-activity and retention rule; it is not a stored lifecycle state in the first Beta. Becoming stale does not automatically modify, archive, or delete a Conversation.

A stale Conversation may be deleted only after explicit user review and approval of the exact Conversation or an explicitly bounded set. The deletion contract must account for affected Topic membership, Person relationships, provenance, and any historical references before Graph Governor permits it. The first Beta may identify deletion candidates but does not receive independent deletion authority.

## 6. Tracking Topic schema

### 6.1 Minimum candidate frontmatter

```yaml
---
schemaVersion: 2
type: tracking-topic
id: <stable-compass-id>
title: <human-readable-title>
createdAt: 2026-08-28T14:30:00Z
status: active
attentionState: action
cspId: <csp-id>
participantIds:
  - <person-id>
excludedParticipantIds: []
---
```

### 6.2 Tracking Topic fields

| Field | Type | Required | Contract |
| --- | --- | --- | --- |
| `status` | closed string value | Yes | `active` or `archived`. |
| `success` | boolean or null | Conditional | Required as `true` or `false` when `status` is `archived`. When `status` is `active`, the field is absent or null. |
| `attentionState` | closed string value | Yes | `action`, `waiting`, or `observing`. Records the user's current relationship to the Topic, independently of lifecycle and participation. |
| `cspId` | CSP ID | No | The Topic's zero-or-one authoritative CSP alignment. |
| `participantIds` | unique list of Person IDs | Yes | Persistent People associated with the Topic through accepted Conversation funneling or Topic Interview management. Empty is valid. |
| `excludedParticipantIds` | unique list of Person IDs | Yes | People explicitly removed through Topic Interview and suppressed from automatic Conversation funneling until explicitly re-added. Empty is valid. |
| `tags` | unique list of normalized strings | No | User-approved Topic classifiers. Values use lowercase kebab-case. `hpi` identifies a High Profile Incident and `solved` identifies a resolved outcome; additional user-authored values are permitted. |
| `reviewBullet` | boolean | No | When `true`, Curator includes the Topic as a distinct bullet in an applicable bounded review. Absence or `false` creates no required review bullet. |

### 6.3 Lifecycle

- `active` means the Topic currently participates in the user's work-memory practice.
- `archived` means the Topic is retained for history but no longer actively participates; `success` records whether the Topic succeeded.
- Archiving requires the user to choose `success: true` or `success: false` as part of the exact approved proposal.
- An active Topic may omit `success` or store it as null. Reactivation removes `success` from frontmatter.
- `action` means the user has a next action on the Topic.
- `waiting` means progress depends on another person, event, decision, or external condition rather than a current user action.
- `observing` means the user retains awareness of the Topic without direct involvement or a current action.
- Topic creation and attention-state changes require exact user authority. Compass may propose a value from context but may not infer or silently change it.
- Archival preserves the last accepted `attentionState` as historical context. Reactivation requires the user to confirm that value or choose another before the Topic becomes active.
- Archival preserves the Topic file and historical relationships.
- Reactivation changes `archived` back to `active` through an authorized operation.
- A Tracking Topic is never deleted; staleness may support an archival recommendation but cannot trigger an automatic state change.
- No `paused`, `watching`, `completed`, or deleted state is accepted.

### 6.4 Derived Conversation membership

A Tracking Topic does not store an authoritative list of Conversation IDs. Its aligned Conversations are derived by querying Conversation files whose `trackingTopicId` equals the Topic's `id`.

Reports and the Tracking Topic Interview may use the derived list and the associated Conversation context without creating a duplicate source of relationship truth.

### 6.5 Persistent Topic participants

- When a Conversation is aligned to a Topic, each Conversation `participantIds` member not present in Topic `excludedParticipantIds` is added to Topic `participantIds` in the same authorized write set.
- Later accepted participants on an already aligned Conversation funnel to that Topic under the same rule.
- Removing, deleting, staling, or reassigning a Conversation does not remove People from the prior Topic.
- Topic Interview may add a Person directly. Re-adding an excluded Person removes the ID from `excludedParticipantIds` and adds it to `participantIds`.
- Topic Interview may remove a Person directly. Removal deletes the ID from `participantIds` and adds it to `excludedParticipantIds`.
- The two lists are disjoint. Neither operation deletes the Person, changes Conversation history, or rewrites prior Daily Logs.
- Person objects do not store reverse Topic or Conversation lists; reverse reporting is derived.

### 6.6 Topic last activity

No authoritative Topic last-activity field is defined yet. Candidate inputs are:

- meaningful source activity from currently aligned Conversations; and
- meaningful engagement through the Tracking Topic Interview Skill.

Scenarios must determine whether these inputs create one combined value or separate concepts such as latest work activity and latest Topic engagement.

### 6.7 Topic narrative body

A Tracking Topic may contain a detailed user-approved Markdown narrative. Content is optional and collected only when the user offers it, selects a source for review, or approves an evidence-derived proposal. The narrative is durable career and troubleshooting memory, not raw evidence storage.

Tracking Topic Interview owns narrative composition and later narrative changes. Daily Scan may retrieve bounded authorized evidence and hand off a minimized candidate contribution, but the handoff is not authority to change the Topic. Curator reads the accepted narrative and may surface a `reviewBullet: true` Topic without modifying it. Graph Governor validates the declared frontmatter effects and preservation boundaries; it does not decide whether the narrative is complete or true.

When applicable, use these readable sections without requiring empty headings:

1. `Summary`;
2. `Impact`;
3. `Troubleshooting Logic`;
4. `Evidence Considered`;
5. `Resolution`;
6. `Outcome and Contribution`;
7. `Lessons`;
8. `Follow-Up Outside This Topic`; and
9. `Review Bullet`.

The narrative contract requires:

- concise paraphrase instead of raw messages, transcripts, bridge links, addresses, phone numbers, end-user identifiers, or unnecessary names;
- clear separation of direct evidence, interpretation, disproved hypotheses, confirmed cause, and user-authored reflection;
- preservation of existing user-authored content during unrelated field or relationship changes;
- exact user review of material narrative additions or revisions before they become durable;
- no inference that an HPI was solved solely from prose, lifecycle, or source evidence; `tags: [hpi, solved]`, `status: archived`, and `success: true` each require user authority; and
- follow-up ideas may remain in the archived narrative without creating, suggesting, or opening another Topic unless the user initiates that work.

For a solved HPI selected for review, the accepted representation is:

```yaml
tags:
  - hpi
  - solved
reviewBullet: true
```

These fields are independent of `status`, `success`, and `attentionState`. Graph Governor checks their types and approved effects but does not infer one field from another.

## 7. CSP schema

### 7.1 Minimum candidate frontmatter

```yaml
---
schemaVersion: 2
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
schemaVersion: 2
type: person
id: <stable-compass-id>
title: <preferred-display-name>
createdAt: 2026-08-28T14:30:00Z
firstName: <confirmed-first-name>
lastName: <confirmed-last-name>
emailAddresses:
  - <normalized-email-address-when-known>
identityState: confirmed
---
```

### 8.2 Person fields

| Field | Type | Required | Contract |
| --- | --- | --- | --- |
| `firstName` | non-empty string | Yes | Confirmed given name; initials and placeholders do not satisfy the field. |
| `lastName` | non-empty string | Yes | Confirmed family name; initials and placeholders do not satisfy the field. |
| `emailAddresses` | unique list of strings | No | Known normalized email addresses supplied by the user or exposed by authorized Work IQ; supports recognition and source correlation. |
| `identityState` | closed string value | Yes | `confirmed` or `provisional`. |

### 8.3 Person identity

- The Compass `id` is the authoritative graph identity for a Person.
- Compass does not request, infer, retrieve for retention, add, or update `userPrincipalName`; UPN is not managed Person data.
- Accept and retain normalized email addresses when the user supplies them or authorized Work IQ exposes them for the approved purpose. They may establish or support recognition and source correlation when the Person participates in a Conversation.
- An email address does not replace the Person's stable Compass ID and is not treated as a request to collect UPN.
- A pre-existing `userPrincipalName` is preserved as unmanaged frontmatter during unrelated writes until separately authorized removal.
- A Person may also be worth tracking when mentioned by name, even if that Person has not authored observed activity, after the user confirms the complete identity.
- A display name alone must not silently merge two Person objects.
- First-name-only evidence cannot create or bind a Person. Compass asks the user for the last name and confirmation; unresolved mentions remain proposals outside the graph.
- `identityState: provisional` may represent incomplete directory correlation after a complete first and last name are known. It cannot excuse a missing name component.
- When no stable Microsoft 365 directory identity is available for an external active sender, a normalized email address may be used as the source-correlation fallback while Compass retains its own stable Person ID.
- If later evidence reveals that two Person records represent the same individual, merging them is a consequential user-approved operation.

### 8.4 Participant relationships

- A Person appears in Conversation `participantIds` after accepted authorship or an accepted, identity-confirmed authored-content mention.
- A Person appears in Topic `participantIds` through deterministic Conversation funneling or explicit Topic Interview management.
- A Person removed from a Topic appears only in that Topic's `excludedParticipantIds` until the user explicitly re-adds them.
- Person objects store no reverse relationship lists.

## 9. Daily Log schema

### 9.1 Minimum frontmatter

```yaml
---
schemaVersion: 2
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

The accepted operation labels are:

| Label | Meaning |
| --- | --- |
| `created` | A new durable graph object was added. |
| `updated` | Existing durable content changed without a more specific accepted label. |
| `aligned` | A Conversation-to-Topic or Topic-to-CSP relationship was established or changed. |
| `unaligned` | A Conversation was intentionally moved to `parking-lot`, or a Topic-to-CSP relationship was removed. |
| `archived` | A Tracking Topic moved from `active` to `archived`. |
| `reactivated` | A Tracking Topic moved from `archived` to `active`. |
| `deleted` | A Conversation was deleted after explicit user review and approval. |
| `person-linked` | Topic Interview added or explicitly re-added a Person to Topic `participantIds`. |
| `person-unlinked` | Topic Interview removed a Person from Topic `participantIds` and added the Person to `excludedParticipantIds`. |

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
| Conversation | `trackingTopicId` | Tracking Topic or reserved `parking-lot` value | exactly one | Conversation owns its intentional Topic disposition. |
| Conversation | `participantIds` | Person | zero or many, unique | Conversation owns accepted authorship and confirmed-mention links. |
| Tracking Topic | `cspId` | CSP | zero or one | Tracking Topic owns the link. |
| Tracking Topic | `participantIds` | Person | zero or many, unique | Tracking Topic owns persistent participant links. |
| Tracking Topic | `excludedParticipantIds` | Person | zero or many, unique | Tracking Topic owns explicit participant exclusions; this list must be disjoint from `participantIds`. |

Graph Governor validates that every Person or object target exists and has the expected `type`. The reserved `parking-lot` value is not resolved as an object. Reverse membership is derived and must not be treated as an independently authoritative list.

### 11.1 Four-object field-to-Skill traceability

This matrix is the coverage index for the Conversation, Tracking Topic, CSP, and Person YAML contract. It does not create fields or transfer authority between Skills. The field definitions in sections 4 through 8 remain normative; this index identifies where the current Skill instructions produce, preserve, consume, or validate them.

| Object | Managed field | Requirement | Producing or changing instruction | Validation or consumption instruction |
| --- | --- | --- | --- | --- |
| All four | `schemaVersion` | Required positive integer; `2` for this baseline. | Installation Interview bootstraps schema-version-2 objects; Daily Scan and Tracking Topic Interview prepare schema-version-2 effects. | Graph Governor indexes `schemaVersion` and validates object schema version `2`. |
| All four | `type` | Required closed value matching the object kind. | Each writer creates only the object kinds within its stated role. | Graph Governor identifies managed artifacts from accepted `type` values and does not infer type from path, title, or body. |
| All four | `id` | Required globally unique stable Compass identity. | Installation Interview and Daily Scan create stable IDs; later writers preserve them. | Graph Governor indexes IDs, detects duplicates, resolves references by ID, and does not merge by title or similarity. |
| All four | `title` | Required non-empty display label; never identity. | Installation Interview uses reviewed wording; Daily Scan proposes concise Conversation titles; Tracking Topic Interview preserves user wording. | Graph Governor validates structure but never uses `title` to resolve identity or relationships. |
| All four | `createdAt` | Required immutable UTC ISO 8601 creation timestamp. | The creating Skill includes it in the new-object effect; later writes preserve it. | Graph Governor indexes and validates the timestamp and verifies that unrelated changes preserve it. |
| Conversation | `sourceSystem` | Required; `microsoft-365`. | Daily Scan explicitly proposes `sourceSystem: microsoft-365`. | Graph Governor validates the closed value and includes it in the source-correlation tuple. |
| Conversation | `sourceType` | Required; `chat` or `email`. | Daily Scan explicitly proposes the observed source type. | Graph Governor validates the closed value and includes it in the source-correlation tuple. |
| Conversation | `sourceConversationId` | Required durable source Conversation identity. | Daily Scan requires verified source identity and forbids item/message ID substitution. | Graph Governor validates presence, tuple uniqueness, and the distinction from item identity when evidence permits. |
| Conversation | `participantIds` | Required unique Person-ID list; empty is valid. | Daily Scan adds accepted authors/responders and identity-confirmed authored-content mentions without pruning prior participants. | Graph Governor resolves every ID to a complete-name Person and rejects duplicates or unresolved targets. |
| Conversation | `trackingTopicId` | Required Tracking Topic ID or `parking-lot`. | Daily Scan displays one disposition in every proposal; Tracking Topic Interview performs approved alignment changes. | Graph Governor resolves a Topic ID, accepts `parking-lot` without resolution, and rejects missing, null, empty, dangling, or wrong-type values. |
| Tracking Topic | `status` | Required; `active` or `archived`. | Installation Interview creates active Topics; Tracking Topic Interview owns approved archival and reactivation effects. | Graph Governor rejects other values and checks lifecycle consistency with `success`. |
| Tracking Topic | `success` | Required boolean when archived; absent or null when active. | Tracking Topic Interview obtains the archival outcome and removes the field on reactivation. | Graph Governor rejects missing or non-boolean archived values and non-null active values. |
| Tracking Topic | `attentionState` | Required; `action`, `waiting`, or `observing`. | Installation Interview and Tracking Topic Interview require the user's explicit choice; Daily Scan may display but cannot change it. | Graph Governor validates the closed value and exact authority for creation or change; Curator reads it without deriving it. |
| Tracking Topic | `cspId` | Optional single CSP ID. | Installation Interview sets reviewed foundational alignment; Tracking Topic Interview owns later approved alignment changes. | Graph Governor resolves the present ID to exactly one CSP; CSP membership is derived from this field. |
| Tracking Topic | `participantIds` | Required unique Person-ID list; empty is valid. | Installation Interview initializes it; Daily Scan funnels accepted Conversation participants; Tracking Topic Interview adds, removes, or re-adds with authority. | Graph Governor resolves complete-name People, rejects duplicates and overlap, and Curator derives People views from this owner field. |
| Tracking Topic | `excludedParticipantIds` | Required unique Person-ID list disjoint from `participantIds`; empty is valid. | Installation Interview initializes it; Daily Scan preserves and honors it; Tracking Topic Interview owns explicit removal and re-add. | Graph Governor resolves IDs, rejects duplicates and overlap, and verifies that automatic funneling honors exclusions. |
| Tracking Topic | `tags` | Optional unique lowercase kebab-case string list. | Tracking Topic Interview writes only user-approved classifiers; Daily Scan may propose candidate tags in a minimized evidence handoff but cannot change them. | Graph Governor validates shape, normalization, uniqueness, and exact authority; Curator reads accepted values. |
| Tracking Topic | `reviewBullet` | Optional boolean. | Tracking Topic Interview writes the exact approved value. | Graph Governor validates type and authority; Curator emits one distinct bullet when the value is `true` and the Topic is in scope. |
| Person | `firstName` | Required meaningful non-empty given name. | Installation Interview, Daily Scan, and Tracking Topic Interview require user confirmation rather than inference. | Graph Governor rejects missing, empty, initial-only, or placeholder names for referenced People. |
| Person | `lastName` | Required meaningful non-empty family name. | Installation Interview, Daily Scan, and Tracking Topic Interview block first-name-only creation or binding. | Graph Governor rejects missing, empty, initial-only, or placeholder names for referenced People. |
| Person | `emailAddresses` | Optional unique normalized string list. | A creating Skill may include a reviewed normalized address when source correlation requires it; it is not Person identity. | Graph Governor validates accepted structure without merging People by email address. |
| Person | `identityState` | Required; `confirmed` or `provisional`. | A creating Skill records the reviewed identity state after complete first and last names are known. | Graph Governor validates the closed value; `provisional` never waives complete-name requirements. |

`userPrincipalName` is intentionally absent from the managed Person field inventory. Writer Skills must not request, infer, add, or update it. Graph Governor rejects a schema-version-2 effect that introduces or updates it while preserving a pre-existing value as unknown unmanaged frontmatter during unrelated work.

### 11.2 Four-object relationship-to-Skill traceability

| Relationship | Canonical representation | Writer behavior | Governor assertion | Derived view |
| --- | --- | --- | --- | --- |
| Conversation to Tracking Topic | Conversation `trackingTopicId` contains one Topic `id`. | Daily Scan proposes one reviewed disposition; Tracking Topic Interview applies later approved changes. | Target exists exactly once and has `type: tracking-topic`. | A Topic's Conversations are queried from matching Conversation fields; no Topic-side Conversation list exists. |
| Conversation to Parking Lot | Conversation `trackingTopicId: parking-lot`. | Daily Scan or Tracking Topic Interview records the intentional unaligned disposition. | Reserved value is accepted without object resolution; no object may use it as an ID. | Parking Lot is the set of matching Conversations, not an object. |
| Conversation to Person | Conversation `participantIds` contains Person `id` values. | Daily Scan accumulates qualifying participants after identity confirmation. | Every unique target exists exactly once, has `type: person`, and has complete names. | A Person's Conversations are queried from Conversation fields; Person stores no reverse list. |
| Tracking Topic to CSP | Tracking Topic `cspId` contains one CSP `id` or is absent. | Installation Interview or Tracking Topic Interview records user-approved alignment. | A present target exists exactly once and has `type: csp`. | A CSP's Topics are queried from Topic fields; CSP stores no reverse list. |
| Tracking Topic to included Person | Topic `participantIds` contains Person `id` values. | Installation Interview initializes reviewed links; Daily Scan funnels non-excluded Conversation participants; Topic Interview manages direct links. | Targets resolve to complete-name People; values are unique and disjoint from exclusions. | A Person's Topics are queried from Topic fields; Person stores no reverse list. |
| Tracking Topic to excluded Person | Topic `excludedParticipantIds` contains Person `id` values. | Topic Interview records explicit removal and re-add; other writers preserve and honor the list. | Targets resolve to complete-name People; values are unique and disjoint from participants. | Exclusion suppresses future automatic funneling only for that Topic. |

The corresponding package instructions are `compass-installation-interview`, `compass-daily-scan`, `compass-tracking-topic-interview`, `compass-curator`, and `graph-governor`. A package is schema-ready only when its active instructions and references use every managed field name exactly as listed here and define no competing authoritative reverse list.

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
10. accepted Conversation participation from passive recipients, roster-only members, and unresolved mentions;
11. complete Person names and user-confirmed binding for first-name-only mentions;
12. absence of introduced or updated Person `userPrincipalName` data in proposed schema-version-2 effects;
13. required intentional Conversation disposition and reserved `parking-lot` handling;
14. Topic participant accumulation, exclusion, disjointness, and non-cascading removal; and
15. absence of duplicate authoritative reverse relationship lists in Compass-managed fields;
16. Daily Log date identity, marker integrity, stable-ID membership, ordering, and deduplication;
17. preservation of user-authored Daily Log content outside the managed markers;
18. configuration schema, canonical UUID v4 graph identity, and valid IANA timezone;
19. deterministic timezone mapping with pinned CLDR and IANA database versions; and
20. disclosed, traceable, and operation-bounded use of any temporary Microsoft 365 timezone;
21. optional Topic `tags` list type, lowercase kebab-case normalization, and uniqueness; and
22. optional Topic `reviewBullet` boolean type and preservation across unrelated writes.

Graph Governor may report last-activity gaps but cannot enforce an unresolved last-activity derivation.

## 13. Deferred fields and schemas

The following are intentionally deferred:

- item-level evidence references;
- Conversation source-activity timestamp;
- graph modification timestamp;
- Topic latest work activity;
- Topic latest interview engagement;
- complete filename and folder conventions;
- exact Compass ID format;
- exact source Conversation ID encoding and normalization;
- CSP retirement or replacement behavior;
- transaction, recovery, and audit-record schemas; and
- Conversation stale-retention duration and last-activity derivation.

Deferral prevents an untested assumption from becoming a Graph Governor rule.

The disposable-beta recovery protocol in `SC-WRITE-005` does not establish a production transaction or audit-record schema. Its retained snapshot and operation evidence are test controls, not authoritative graph objects.

## 14. Required schema scenarios

### GS-BETA-001 — Minimal valid objects

Graph Governor accepts one minimal valid fixture for each of the five object types.

### GS-BETA-002 — Unknown field preservation

A file containing user or plugin frontmatter outside Compass's managed schema survives a Compass-managed change without loss or unintended rewriting.

### GS-BETA-003 — Stable object identity

Renaming a title or file does not change the Compass `id` or break valid references.

### GS-BETA-004 — Source Conversation identity

Activity with the same verified source-correlation key resolves to the existing Conversation; activity with a different key does not merge based on similarity.

### GS-BETA-005 — Conversation participant accumulation

The initial author, later authors/responders, and user-confirmed People named in authored content are added once. Passive recipients and roster-only members are excluded, and accepted participants absent from a later scan are not removed.

### GS-BETA-006 — Mentioned Person confirmation

A complete-name mention may bind to a user-confirmed Person. A first-name-only mention remains unresolved until the user confirms the last name and existing-or-new identity; no partial Person or participant link is written.

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

### GS-BETA-024 — Intentional Parking Lot disposition

Every Conversation has a non-null `trackingTopicId`. `parking-lot` produces the derived Parking Lot view without resolving to a Topic object; missing, null, empty, and dangling Topic values are invalid.

### GS-BETA-025 — Persistent Topic participant funnel

Accepted Conversation participants funnel to an aligned Topic and remain after Conversation removal, deletion, staleness, or reassignment. Existing Topic exclusions are preserved.

### GS-BETA-026 — Topic participant removal and re-add

An approved removal moves the Person ID from Topic `participantIds` to `excludedParticipantIds` without changing the Person or Conversations. Automatic funneling does not re-add that Person. An approved Topic Interview re-add reverses both fields.

### GS-BETA-027 — Solved HPI review metadata

An approved archived successful Topic stores unique `hpi` and `solved` tags plus `reviewBullet: true`. Curator surfaces one distinct review bullet in an applicable bounded review without changing the Topic. Missing approval, duplicate or non-normalized tags, and non-boolean `reviewBullet` are invalid proposed effects.

### GS-BETA-028 — Offered-evidence Topic narrative

Daily Scan minimizes bounded offered evidence into a candidate narrative handoff. Tracking Topic Interview separates observed facts, interpretation, disproved hypotheses, cause, resolution, lessons, and out-of-scope follow-up; obtains exact approval; and preserves unrelated Topic content. Graph Governor validates the approved effects and preservation boundary without claiming narrative completeness or source truth.

## 15. Deferred beta decisions

Runtime evidence must still prove that source Chat and Email Conversation IDs behave as required.

The following remain explicitly deferred and do not block baseline acceptance:

- item-level evidence records;
- last-activity fields and stale-retention rules;
- complete filename conventions and type-specific Compass ID formats;
- exact source Conversation ID encoding and normalization;
- Person merge and CSP retirement behavior; and
- transaction, recovery, and audit-record schemas beyond the behavioral disposable-beta protocol.

## 16. Acceptance boundary

This is the accepted participant-management schema specification. It establishes schema version 2 for new or migrated Compass objects. Schema-version-1 artifacts remain readable historical inputs but are not silently rewritten; migration requires an explicit reviewed operation.

The user authorized coordinated documentation, Skill source, Orchestration, and test-source updates on 2026-09-06. This specification does not itself authorize Microsoft 365 access, modification of a personal graph, connected testing, deployment, publication, or release.
