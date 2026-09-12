# Decision: Stop collecting Person UPN

- **Date:** 2026-09-06
- **Status:** accepted
- **Deciders:** User / product owner
- **Related assessment:** [Person UPN removal impact assessment](../specifications/2026-09-06-person-upn-removal-impact-assessment.md)

## Context

Compass does not need a Microsoft 365 user principal name to represent a Person or their relationships in the graph. Retaining that directory attribute adds personal data without supporting the graph's intended context. Compass already uses its own stable Person ID as identity and may use a normalized email address only when source correlation requires it.

## Decision

Remove `userPrincipalName` from the current schema-version-2 Person contract. Compass Skills must not request, infer, retrieve for retention, add, or update a Person UPN.

Person identity remains the Compass `id`. Meaningful `firstName` and `lastName` remain required, `identityState` remains required, and optional normalized `emailAddresses` remain available only as source-correlation signals.

If a current graph already contains `userPrincipalName`, Skills treat it as unmanaged existing frontmatter and preserve it during unrelated writes. Removal from an existing graph requires a separately disclosed and authorized cleanup; this decision does not authorize mutation of any graph.

The preserved schema-version-1 Graph Governor contract, prior packages, fixtures, and completed test evidence remain unchanged historical records.

## Alternatives considered

- **Keep UPN as an optional field:** Rejected because optional collection still retains personal data that is unnecessary for Compass graph context.
- **Replace Compass identity with UPN:** Rejected because Microsoft 365 directory identity must not replace stable graph identity.
- **Delete existing UPN values automatically:** Rejected because this request changes future collection and managed schema intent but does not authorize undisclosed graph mutation.
- **Remove email correlation too:** Rejected as out of scope; normalized email remains an accepted fallback for source correlation, especially for external participants.

## Consequences

- Current Person examples and field tables omit `userPrincipalName`.
- Person-creating Skills prohibit collecting or persisting UPN.
- Graph Governor rejects proposed schema-version-2 effects that introduce or update UPN while preserving unknown existing frontmatter outside the requested effect.
- No object schema-version increment is required because the removed field was optional.
- Prior packages and completed evidence remain exact and version-bound.

## Follow-up

- Statically inspect revised sources and deterministic packages.
- Test prompting, retrieval minimization, validation, and existing-value preservation only after separate authorization.