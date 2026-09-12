# Compass Graph Validation Contract

## Root and shared header

Required root: `_compass/config.yaml`, `CSPs/`, `Efforts/`, `People/`, `Conversations/`, and `Daily Logs/`. Configuration contains `schemaVersion: 2`, UUID `graphId`, and confirmed IANA `timezone`.

Every Markdown object contains `schemaVersion: 2`, accepted `type`, `<type>:<UUID>` stable `id`, non-empty `title`, and immutable UTC `createdAt`. Managed names are camelCase. Optional fields are omitted when absent. Unknown frontmatter and user Markdown survive managed updates.

## Entity invariants

- `csp`: no managed status or reverse Effort list.
- `effort`: `status: active|archived`; `attentionState: action|waiting|observing`; optional one `cspId`; optional unique, disjoint `participantIds` and `excludedParticipantIds`; optional unique lowercase-kebab `tags`; optional boolean `reviewBullet`. `success` is absent while active and required boolean while archived.
- `person`: meaningful `firstName` and `lastName`; optional unique reviewed normalized `emailAddresses`. Email and user principal name are not identity.
- `conversation`: required reliable UTC `lastActivityAt`; optional UTC `startedAt`; unique `participantIds`; exactly one `effortId` or `disposition: parking-lot`; optional minimized `provenance`. Activity identity follows coherent customer work, not a source container.
- `daily-log`: path `Daily Logs/YYYY-MM-DD.md`; matching `id: daily-log:<date>` and `date`; append-only `changes` with exactly `timestamp`, `objectType`, `objectId`, and `changeType` per durable object effect.

## Provenance and archive metadata

Each provenance entry uses `system`, `sourceType`, `sourceRef`, and `observedThrough`. It contains no raw transcript. `observedThrough` records inspected coverage and does not replace `lastActivityAt`.

An archived Effort may contain `archivedActivities`. Each entry requires Activity `id`, `title`, `lastActivityAt`, `participantIds`, and concise `summary`; `startedAt` and minimized `provenance` are optional. The entry is historical metadata, not a live object. Activity-file removal is valid only after this metadata and archived Effort state are read back and the exact removal is separately authorized.

## Blockers

Block the affected operation for invalid configuration; unsafe parsing; malformed or duplicate IDs; unsupported types or values; missing required fields; changed immutable fields; unresolved or type-mismatched references; duplicate or overlapping arrays; invalid Activity disposition; unreliable Activity recency; wrong object folder; filename collision; incomplete archive metadata; unpreserved unknown content; or missing, duplicate, or false Daily Log effects.

Warnings do not conceal blockers. Unavailable files or partial inspection are `unverified`, not valid. Postflight success requires independent read-back of every affected object and Daily Log.