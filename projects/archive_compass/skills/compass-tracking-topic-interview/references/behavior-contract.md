# Tracking Topic Interview behavior contract

## Identity

- Skill: `compass-tracking-topic-interview`
- Version: `0.7.0-production-test-candidate`
- Shared contract/schema: `0.8-production-evidence-baseline` / `0.7-hpi-narrative-baseline` / schema version 2
- Orchestration: `compass-work-memory-lifecycle` `0.7.0-production-test-candidate`

## Required invariants

1. User meaning and exact displayed authority govern every organizational effect.
2. A handoff supplies context, never inherited authority.
3. Topic status is only `active` or `archived`.
4. Tracking Topics are never deleted.
5. Conversation `trackingTopicId` is required and contains one Topic ID or `parking-lot`.
6. Topic `cspId` owns Topic-to-CSP alignment.
7. Merge retains one target, realigns only approved Conversations, and archives source Topics.
8. Every change includes applicable Daily Log effects.
9. Graph Governor validates before and verifies after application.
10. Material proposal changes require renewed approval.
11. Daily Log-derived recency may inform review but never triggers archival without user confirmation and exact approval.
12. Production partial or unverifiable writes stop as `recovery-required`; this version performs no automatic rollback or repair.
13. Topic `participantIds` owns persistent participant links; Topic `excludedParticipantIds` owns explicit suppression state, and the lists are disjoint.
14. Topic Interview never requests, infers, retrieves for retention, adds, or updates Person `userPrincipalName`; existing values remain unmanaged and preserved unless separately authorized for removal.
15. Add, remove, and re-add require exact user authority and use `person-linked` or `person-unlinked` Daily Log effects.
16. A first-name-only Person request requires last-name and identity confirmation before any Person or relationship write.
17. Conversation lifecycle or reassignment never prunes Topic participants.
18. Every archived Topic has a user-approved boolean `success`; active Topics have null or absent success, and reactivation removes the field.
19. Success is never inferred from completion language, staleness, recency, merge, or graph content.
20. Every Topic has exactly one user-authorized `attentionState`: `action`, `waiting`, or `observing`.
21. Attention state is independent of lifecycle, archival success, participation, and relationships; evidence may support a proposal but never silently determines it.
22. Archival retains attention state, and reactivation requires confirmation or change of that retained value.
23. Topic Interview owns user-approved narrative composition and optional `tags` and `reviewBullet` changes from offered content or minimized handoffs.
24. Topic tags are unique lowercase kebab-case strings; `reviewBullet` is boolean; neither silently determines lifecycle, success, or attention.
25. Follow-up ideas may remain archived context but never trigger another Topic prompt unless the user initiates it.
26. User-authorized Topic evidence retrieval uses all relevant Work IQ capability Cowork exposes without arbitrary numeric caps or sample-data substitution and reports incomplete coverage.
27. Reviewed normalized email addresses are retained in Person proposals and handoffs when supplied by the user or exposed by authorized Work IQ; they never replace complete name or stable Compass ID.
28. Every approved OneDrive file write uses its declared graph-root-relative path, never a OneDrive item ID; this transport rule does not concern source Conversation IDs.

## Interaction contract

- Interpret direct input, accepted graph context, and authorized Work IQ into the best useful editable artifact suggestion before asking for confirmation; ask a follow-up only for material ambiguity that cannot be represented safely.
- Ask about meaning, not storage mechanics.
- Preserve user wording.
- Offer at most three primary choices with typed equivalents.
- Accept `Back`, `Pause`, and `Cancel` where meaningful.
- Display all consequential effects before approval.

## Forbidden behavior

- Evidence retrieval without an explicit Topic purpose or user authority.
- Topic deletion, Person merge, Conversation deletion, or CSP retirement.
- Reverse authoritative relationship lists.
- Staleness-driven automatic lifecycle changes.
- Writes outside the selected graph or after connected state becomes uncertain.
- False committed outcome after partial or uncertain effects.
- Sample-data substitution, arbitrary Work IQ result caps, raw evidence retention, or unapproved narrative and review-metadata changes.
