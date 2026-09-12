# Compass Curator Lifecycle Contract

## Recency

The default stale cutoff is the review instant minus 14 days, presented in the graph's confirmed IANA timezone. Effort last Activity is the greatest reliable `lastActivityAt` among its live Activities and retained archived Activity metadata.

Only meaningful customer-work item timestamps count. Never use file modification, graph maintenance, retrieval, indexing, attention state, Daily Log, container start or modification, or unrelated recent messages. Follow continuation separately for Email and Teams. Incomplete coverage or timestamp ambiguity blocks a confident stale classification.

## Archive schema

An authorized Effort changes from `status: active` to `status: archived` and gains required boolean `success`. Before an Activity can be removed, append:

```yaml
archivedActivities:
  - id: conversation:<UUID>
    title: <title>
    lastActivityAt: <UTC customer-work timestamp>
    startedAt: <optional UTC customer-work timestamp>
    participantIds:
      - person:<UUID>
    summary: <concise customer-work account>
    provenance:
      - system: microsoft-365
        sourceType: email
        sourceRef: <minimized stable reference>
        observedThrough: <UTC item boundary>
```

`startedAt` and `provenance` are optional. The entry is historical metadata, not a live Activity or active relationship.

## Required operation order

1. Approve review criteria; perform read-only classification.
2. Present candidates, evidence, uncertainty, retained metadata, and possible later removals.
3. Obtain exact Effort archive authority, including `success` values.
4. Run Governor preflight, re-read targets, archive authorized Efforts, retain metadata, and append Daily Log effects.
5. Read back Efforts and logs; run Governor postflight.
6. Present exact removable Activity files only after metadata verification.
7. Obtain separate exact removal authority.
8. Re-read and revalidate, remove only approved files, append removal log effects, and run postflight again.

Every object has `schemaVersion: 2`, `<type>:<UUID>` stable `id`, title, and immutable UTC `createdAt`. Preserve unknown frontmatter and user Markdown. References use IDs, not paths. Block unsafe parsing, duplicate identity, unresolved references, collisions, conflicts, incomplete retained metadata, active Efforts, and unverified effects.