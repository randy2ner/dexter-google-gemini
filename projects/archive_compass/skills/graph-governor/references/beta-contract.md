# Graph Governor beta behavior contract

## Identity

- Skill: `graph-governor`
- Version: `0.8.0-production-test-candidate`
- Shared contract/schema: `0.8-production-evidence-baseline` / `0.7-hpi-narrative-baseline` / schema version 2
- Orchestration: `compass-work-memory-lifecycle` `0.7.0-production-test-candidate`

## Modes

1. Pre-write validation of an accepted ten-field change handoff.
2. Post-write verification against the original request and current state.
3. Bounded read-only production graph health scan under the preserved read-only contract.

## Required invariants

1. Graph Governor never chooses user meaning or originates semantic change.
2. `valid` applies only to the exact request, authority, effects, and source state checked.
3. Material change requires renewed user approval and validation.
4. Every durable update includes its required Daily Log effect.
5. Canonical relationship owner fields are the only authoritative direction.
6. Unknown safe frontmatter and unmanaged user content remain preserved.
7. Only verified complete effects may be `committed` or `committed-with-warnings`.
8. Every other outcome accounts for unapplied, rolled-back, uncertain, and preserved effects as applicable.
9. A production partial or unverifiable application returns `recovery-required` and blocks dependent writes pending user-led resolution; this version performs no automatic rollback or repair.
10. Every Conversation has one approved `trackingTopicId`: a valid Topic ID or reserved `parking-lot`; missing, null, and empty are invalid.
11. Conversation `participantIds` contains only accepted authors/responders or user-confirmed authored-content mentions, and every target Person has meaningful `firstName` and `lastName`.
12. Topic `participantIds` and `excludedParticipantIds` are unique and disjoint; automatic funneling honors exclusions and never prunes Topic participants from Conversation lifecycle changes.
13. Topic participant add/remove/re-add authority belongs to Tracking Topic Interview; deterministic Daily Scan funnel effects must be disclosed in the approved Conversation write.
14. First-name-only mentions cannot create or bind a Person or participant relationship without user confirmation of last name and identity.
15. Every archived Topic has boolean `success`; active Topics permit only absent or null success, and a reactivation request removes the field.
16. Archival success must be covered by exact user authority and cannot be inferred by Graph Governor.
17. Every Topic has exactly one `attentionState`: `action`, `waiting`, or `observing`; missing, null, empty, and unknown values are invalid.
18. Topic creation, attention-state change, and reactivation attention confirmation require exact user authority; Graph Governor never infers the value.
19. Schema-version-2 Person effects never introduce or update `userPrincipalName`; pre-existing UPN remains unmanaged frontmatter preserved until separately authorized removal.
20. Optional Person `emailAddresses` is a unique list of reviewed normalized strings and never replaces stable Compass identity or authorizes UPN collection.
21. Optional Topic `tags` is a unique lowercase kebab-case string list and optional `reviewBullet` is boolean.
22. Changes to Topic tags, review behavior, or material narrative require exact Tracking Topic Interview authority and complete expected effects.
23. Governor never infers `status`, `success`, `attentionState`, tags, review behavior, or narrative truth from another field.
24. Unrelated operations preserve Topic narrative, review metadata, and user-authored content.
25. Every create or replace effect names a normalized graph-root-relative target path. A handoff prescribing OneDrive item-ID write addressing is invalid; graph-root resolution and source Conversation identity are unaffected.

## Change handoff

Require `requestId`, `initiatingSkill`, `authoritySource`, `operationType`, `targetObjects`, `expectedEffects`, `sourceState`, `evidenceReferences`, `approvalReference`, and `correlationId`.

## Forbidden behavior

- Direct graph writes or independent repair.
- Approval broadening or inferred consequential intent.
- Similarity-based identity recovery.
- Reverse authoritative relationship lists.
- Authoritative last-activity enforcement before contract acceptance.
- Introduction or update of Person UPN in a schema-version-2 effect.
- Malformed, inferred, or unauthorized Topic review metadata or narrative effects.
- Runtime, persistence, provider, package, or connected-capability claims without evidence.
