# Activity Graph Write Contract

## Files and identity

The graph root contains `_compass/config.yaml`, `CSPs/`, `Efforts/`, `People/`, `Conversations/`, and `Daily Logs/`. Configuration contains `schemaVersion: 2`, one UUID `graphId`, and one confirmed IANA `timezone`.

Every Markdown object has `schemaVersion: 2`, accepted `type`, `<type>:<UUID>` stable `id`, non-empty `title`, and immutable UTC `createdAt`. Filenames are lowercase-kebab title slugs; paths and filenames are not identity. Preserve unknown YAML and user-authored Markdown.

## Person

```yaml
type: person
id: person:<UUID>
firstName: <meaningful first name>
lastName: <meaningful last name>
emailAddresses:
  - <optional reviewed normalized email>
```

Email is not identity. Never store or infer a user principal name.

## Conversation or Activity

```yaml
type: conversation
id: conversation:<UUID>
lastActivityAt: <UTC qualifying customer-work timestamp>
startedAt: <optional UTC qualifying timestamp>
participantIds:
  - person:<UUID>
effortId: effort:<UUID>
provenance:
  - system: microsoft-365
    sourceType: email
    sourceRef: <minimized stable reference>
    observedThrough: <UTC item boundary>
```

Exactly one of `effortId` or `disposition: parking-lot` is present. Participants are unique. `sourceType` is `email` or `teams-chat`; several provenance entries may support one Activity. Narrative states the concise customer-work account.

## Daily Log and write order

Use `Daily Logs/YYYY-MM-DD.md` in the configured timezone. Its YAML has `type: daily-log`, `id: daily-log:<date>`, `date`, and `changes`. Append one item per durable effect with `timestamp`, `objectType`, `objectId`, and lowercase-kebab `changeType`.

Read and parse targets, resolve stable-ID references, validate fields and cardinality, present exact effects, obtain authority, re-read targets, apply only approved changes, append log entries, then read back and validate. Block collisions, duplicate IDs, unsafe parsing, unresolved references, ambiguous continuity, invalid timestamps, or an Activity with multiple or missing dispositions.