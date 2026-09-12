# Compass Graph Contract

## Root

```text
_compass/config.yaml
CSPs/
Efforts/
People/
Conversations/
Daily Logs/
```

`_compass/config.yaml` contains:

```yaml
schemaVersion: 2
graphId: <stable UUID>
timezone: <confirmed IANA timezone>
```

Paths and lowercase kebab-case filenames are readable transport labels. Stable YAML IDs are authoritative. A same-folder filename collision stops the affected write until the user selects a distinct filename.

## Shared object header

Every Markdown object begins with YAML containing:

```yaml
schemaVersion: 2
type: <csp|effort|person|conversation|daily-log>
id: <stable ID>
title: <non-empty title>
createdAt: <timezone-explicit UTC ISO 8601>
```

Managed field names use camelCase. Stable identity survives title, filename, or folder changes. Preserve unrecognized frontmatter and user-authored Markdown unless safe parsing is impossible.

## Objects and relationships

### Customer Success Plan

- Stable ID, title, and Markdown narrative describing customer outcomes and strategic context.
- No managed lifecycle status or authoritative reverse Effort list.

### Effort

- `status`: exactly `active` or `archived`.
- `attentionState`: exactly `action`, `waiting`, or `observing`.
- Optional `cspId`: zero or one stable CSP reference.
- Optional unique `participantIds` and disjoint `excludedParticipantIds`.
- Optional narrative, conditional success, unique lowercase-kebab tags, and review marker.
- Reverse CSP and Activity views are derived rather than stored as competing authority.

### Person

- Meaningful `firstName` and `lastName`.
- Optional user-reviewed normalized email addresses.
- Stable Compass ID, not email address, is identity.
- Related Efforts and Activities are derived from their Person references.

### Conversation or Activity

- Stable Compass identity independent of source identity.
- `lastActivityAt`: required timezone-explicit UTC timestamp of the newest qualifying customer-work item.
- Optional `startedAt`: earliest qualifying item when the Activity spans a useful period.
- Unique participating Person references.
- Exactly one Effort reference or Parking Lot disposition.
- Concise customer-work account and minimized provenance in readable Markdown/YAML.

### Daily Log

- One Markdown file per user-local date.
- One entry per durable graph change containing timestamp, object type, stable object ID, and change type.
- It indexes graph changes; it is not work-event history or relationship authority.

## Canonical YAML shapes

Object IDs use `<type>:<UUID>`. References always use stable IDs, never filenames. Omit optional fields when absent; do not write placeholder strings or `null`.

### Customer Success Plan

```yaml
schemaVersion: 2
type: csp
id: csp:<UUID>
title: <title>
createdAt: <UTC timestamp>
```

### Effort

```yaml
schemaVersion: 2
type: effort
id: effort:<UUID>
title: <title>
createdAt: <UTC timestamp>
status: active
attentionState: action
cspId: csp:<UUID>
participantIds:
	- person:<UUID>
excludedParticipantIds: []
tags:
	- <lowercase-kebab>
reviewBullet: true
```

`status` is `active` or `archived`; `attentionState` is `action`, `waiting`, or `observing`. `cspId`, participant arrays, tags, and `reviewBullet` are optional. Arrays are unique and participant arrays are disjoint. `success` is omitted while active and is a required boolean when archived.

### Person

```yaml
schemaVersion: 2
type: person
id: person:<UUID>
title: <full name>
createdAt: <UTC timestamp>
firstName: <meaningful first name>
lastName: <meaningful last name>
emailAddresses:
	- <reviewed normalized email>
```

`emailAddresses` is optional and is not identity. Never store or infer a user principal name.

### Conversation or Activity

```yaml
schemaVersion: 2
type: conversation
id: conversation:<UUID>
title: <title>
createdAt: <UTC timestamp>
lastActivityAt: <UTC customer-work timestamp>
startedAt: <optional UTC customer-work timestamp>
participantIds:
	- person:<UUID>
effortId: effort:<UUID>
provenance:
	- system: microsoft-365
		sourceType: email
		sourceRef: <minimized stable reference>
		observedThrough: <UTC item boundary>
```

Exactly one of `effortId` or `disposition: parking-lot` is present. `startedAt` is optional. `provenance` is optional for direct user input; otherwise each entry uses `sourceType: email` or `teams-chat`. `observedThrough` records coverage and never replaces `lastActivityAt`.

### Daily Log

```yaml
schemaVersion: 2
type: daily-log
id: daily-log:<YYYY-MM-DD>
title: <YYYY-MM-DD>
createdAt: <UTC timestamp>
date: <YYYY-MM-DD>
changes:
	- timestamp: <UTC timestamp>
		objectType: <csp|effort|person|conversation|daily-log>
		objectId: <stable object ID>
		changeType: <lowercase-kebab effect>
```

The path is `Daily Logs/YYYY-MM-DD.md`, with the date calculated in the configured timezone. Append one entry per durable object effect.

## Required write order

1. Read configuration and only the authorized object scope.
2. Parse YAML and Markdown structurally; preserve IDs, `createdAt`, unknown frontmatter, and user Markdown.
3. Resolve stable-ID references and validate schemas, cardinality, timestamps, paths, filenames, and collisions.
4. Present exact effects and obtain `Create` authority.
5. Re-read targets and stop changed, ambiguous, or unsafe operations.
6. Write only approved fields and content.
7. Append one Daily Log entry per durable object effect.
8. Read back and validate every affected object and log before reporting success.

## Validation and effects

Block the affected write for:

- missing or duplicate stable identity;
- unsupported type, lifecycle, or attention value;
- multiple CSPs on one Effort;
- an Activity with multiple Efforts or neither Effort nor Parking Lot;
- duplicate participants or ambiguous Person identity;
- uncertain Activity continuity or unqualified `lastActivityAt`;
- unsafe parsing, unresolved references, or filename collision; or
- missing or invalid graph configuration.

Before reporting success, read back affected files and verify expected content, stable identity, relationships, timestamps, preservation, paths, and one Daily Log entry per durable change. Distinguish completed, unapplied, partial, blocked, conflicting, and uncertain effects.