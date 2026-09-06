# Graph Governor read-only contract

## Authority

This reference applies only to `graph-governor` version `0.1.0-experimental`. It restates the accepted Graph Governor read-only contract subset decision dated 2026-08-28 for package-local use. If this reference conflicts with the registered decision, stop and report the conflict; do not expand behavior.

## Owned outcome

Inspect one user-supplied Compass graph root, report direct structural observations and limitations, make no changes, and access no connected source.

The Skill does not validate writes, perform repairs, retrieve source evidence, verify live Conversation IDs, inspect a production graph, or establish complete Compass health.

## Input and containment

- Require a direct read-only scan request and one unambiguous supplied root.
- Inspect only descendants of the supplied root.
- Never follow a reference outside that root.
- Treat incomplete enumeration as `Partial` or `Blocked`, never `Valid`.
- Exclude fixture manifests, expected outputs, scenarios, and this Skill's references from graph scope.

## Accepted common object fields

Every managed Markdown object requires:

| Field | Accepted rule |
| --- | --- |
| `schemaVersion` | Positive integer; supported value is `1`. |
| `type` | One of `conversation`, `tracking-topic`, `csp`, `person`, or `daily-log`. |
| `id` | Non-empty stable string, unique in the supplied scope. |
| `title` | Non-empty string; never identity. |
| `createdAt` | Timezone-explicit UTC ISO 8601 timestamp. |

Managed field names use `camelCase`. Unknown frontmatter fields and unmanaged Markdown are tolerated unless they prevent safe parsing or conflict with an accepted managed field. They are never rewritten.

## Accepted type-specific fields

### Conversation

| Field | Accepted rule |
| --- | --- |
| `sourceSystem` | Required closed value `microsoft-365`. |
| `sourceType` | Required value `chat` or `email`. |
| `sourceConversationId` | Required non-empty durable source Conversation identity. Do not infer or live-verify it. |
| `activeParticipantIds` | Required unique list of Person IDs; empty is valid. |
| `trackingTopicId` | Optional single Tracking Topic ID. |

The tuple `sourceSystem + sourceType + sourceConversationId` is source-correlation identity and remains distinct from the Compass object `id`. Within the supplied scope, report duplicate tuples. Do not attempt to determine whether an opaque value is actually a message-level ID without authoritative evidence.

### Tracking Topic

| Field | Accepted rule |
| --- | --- |
| `status` | Required value `active` or `archived`. |
| `cspId` | Optional single CSP ID. |

Conversation membership is derived from Conversation `trackingTopicId` values. Do not require a reverse list.

### CSP

No required type-specific field exists in this slice. Do not require or infer a CSP lifecycle status. Topic membership is derived from Tracking Topic `cspId` values.

### Person

| Field | Accepted rule |
| --- | --- |
| `identityState` | Required value `confirmed` or `provisional`. |
| `userPrincipalName` | Optional string; not graph identity. |
| `emailAddresses` | Optional unique list of strings; do not retrieve or enrich it. |

Do not merge People by display name, UPN, email address, or similarity. This slice checks only supplied structure and relationships; it does not establish observed authorship.

### Daily Log

| Field | Accepted rule |
| --- | --- |
| `date` | Required ISO 8601 calendar date. |
| `id` | Exactly `daily-log:<date>`. |
| `title` | Expected to equal the date; report a bounded convention issue if different. |

Exactly one managed Daily Log may claim a date in the supplied scope. One exact start marker must precede one exact end marker outside fenced code blocks:

```text
<!-- compass:daily-log-index:start -->
<!-- compass:daily-log-index:end -->
```

Missing, duplicated, nested, reversed, or malformed markers are issues. Do not modify markers or inspect write-only deduplication, action ordering, backdating, or tombstone behavior.

## Accepted configuration fields

`_compass/config.yaml` requires:

| Field | Accepted rule |
| --- | --- |
| `schemaVersion` | Positive integer; supported value is `1`. |
| `graphId` | Canonical lowercase UUID v4 text with no prefix, braces, or wrapper. |
| `timezone` | Required non-empty IANA-name-shaped stored value. |

A Windows timezone label, numeric offset, abbreviation, empty value, or fuzzy description is not an accepted stored IANA value. Distinguish syntactic shape or exact expected-value comparison from provider-backed IANA verification. When no authoritative provider is available, report provider verification as unavailable.

Do not map Windows IDs, use a provisional timezone, bootstrap configuration, assess graph-copy lineage, or repair an established graph ID.

## Accepted forward relationships

| Source | Field | Target | Cardinality |
| --- | --- | --- | --- |
| Conversation | `trackingTopicId` | Tracking Topic | Zero or one |
| Conversation | `activeParticipantIds` | Person | Zero or many, unique |
| Tracking Topic | `cspId` | CSP | Zero or one |

Every present reference must resolve to exactly one supplied object of the expected type. Missing and wrong-type targets are distinct issues. Reverse membership is derived and is not a second authority.

## Rule identifiers

Use these stable rule components in issue IDs:

| Rule | Meaning |
| --- | --- |
| `SCOPE` | Supplied-root containment or enumeration limitation |
| `YAML` | Frontmatter or safe YAML parse failure |
| `COMMON` | Common required field or type violation |
| `IDENTITY` | Duplicate object ID or source-correlation identity |
| `CONVERSATION` | Conversation-specific field violation |
| `TOPIC` | Tracking Topic-specific field violation |
| `CSP` | CSP-specific accepted-rule violation |
| `PERSON` | Person-specific field violation |
| `REFERENCE` | Missing, duplicate, cardinality, or wrong-type forward relationship |
| `DAILY-LOG` | Date identity or marker structure violation |
| `CONFIG` | Configuration schema, graph ID, or stored timezone violation |
| `CAPABILITY` | Unavailable provider or inspection capability |
| `UNTRUSTED-DATA` | Instruction-like graph content relevant to safety reporting |

Issue IDs identify observations, not repair operations.

## Reporting and outcomes

- `Valid`: complete supplied scope, no accepted-subset issue observed.
- `Issues found`: complete supplied scope, supported issue or issues observed.
- `Partial`: meaningful inspection completed but scope or capability was incomplete.
- `Blocked`: no safe meaningful scan completed.
- `Failed`: scan failed unexpectedly; graph validity is not inferred.

Every report identifies scope, observations, limitations, non-destructive guidance, and effect accounting. Candidate severity prioritizes issues only. It does not authorize action or invalidate unrelated content.

## Explicit exclusions

Do not enforce or imply acceptance of:

- graph writes, pre-write validation, post-write verification, conflict detection, rollback, or recovery;
- live Microsoft 365 source identity or item-ID verification;
- last-activity derivation, staleness, deletion, archival operations, or lifecycle recommendations;
- Daily Log writes, action deduplication, backdating, or tombstones;
- Windows-to-IANA mapping, CLDR behavior, provisional timezone use, or bootstrap;
- connected storage, synchronization, permissions, or persistence;
- automatic repair or any independent modification authority; or
- complete compatibility with the surrounding draft specifications.

## No-change accounting

The Skill creates, modifies, deletes, renames, and moves zero files; performs zero graph writes; and makes zero external changes. Every terminal report includes:

`External changes: 0`
