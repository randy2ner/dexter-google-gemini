# Decision: Accept participant and Topic management

- **Date:** 2026-09-06
- **Status:** accepted
- **Deciders:** User / product owner
- **Related review:** [Compass YAML, links, and relationship rules](../specifications/2026-09-04-compass-yaml-links-and-relationship-rules-review.md)

## Context

Email threads and Teams chats may include many passive recipients or roster members. Treating all of them as active graph participants creates bloat and implies involvement that is not supported. The graph also needs intentional Parking Lot state and durable Topic participant memory that survives Conversation lifecycle changes.

## Decision

1. Schema version 2 replaces Conversation `activeParticipantIds` with `participantIds`.
2. Qualifying Conversation participants are the initial author, later authors/responders, and People named in authored content after user-confirmed identity binding.
3. Passive recipients, roster-only members, reactions, signatures, quoted history, automated footers, disclaimers, and distribution-list names do not qualify by themselves.
4. Every Person requires meaningful `firstName` and `lastName`. A first-name-only mention prompts for last name and existing-or-new identity confirmation before any Person or relationship write.
5. Conversation `trackingTopicId` is required and contains either a valid Tracking Topic ID or reserved value `parking-lot`. Missing, null, and empty values are invalid.
6. Topic `participantIds` persists non-excluded participants funneled from aligned Conversations and People added through Topic Interview.
7. Conversation staleness, removal, deletion, or reassignment does not prune Topic participants.
8. Topic Interview removal moves a Person ID to `excludedParticipantIds`; automatic funneling cannot re-add it. Explicit re-add reverses both fields.
9. Topic participant add/remove history uses `person-linked` and `person-unlinked` Daily Log labels.
10. Schema-version-1 artifacts and completed evidence remain unchanged. Migration requires a separately reviewed and tested operation.

## Alternatives considered

- **Store every recipient or roster member:** Rejected because it creates bloat and confuses visibility with participation.
- **Keep `activeParticipantIds` plus another involvement list:** Rejected because two Conversation participant meanings would be difficult to explain and maintain.
- **Represent Parking Lot by an absent field:** Rejected because absence does not express intentional disposition.
- **Allow automatic re-add after Topic removal:** Rejected because automation would silently reverse explicit user intent.
- **Put reverse Topic IDs on Person:** Rejected because it creates a second relationship authority.

## Consequences

- Shared contracts, schema, five Skill responsibilities, Skill source, Orchestration, fixtures, and tests require coordinated versioning.
- Graph Governor must validate complete names, participant qualification, explicit Topic disposition, funneling, and disjoint Topic participant/exclusion lists.
- Existing schema-version-1 graphs cannot be mutated by schema-v2 behavior until migration is authorized and validated.
- Runtime confidence remains unchanged until planned scenarios produce recorded results.

## Follow-up

- Project Dexter: complete the accepted source updates and static validation.
- User / product owner: separately authorize runtime tests and any personal-graph migration.