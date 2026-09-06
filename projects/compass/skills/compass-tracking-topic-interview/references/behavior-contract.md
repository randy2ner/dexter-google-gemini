# Tracking Topic Interview behavior contract

## Identity

- Skill: `compass-tracking-topic-interview`
- Version: `0.2.0-dogfood-candidate`
- Shared contract/schema: `0.3-beta-baseline`
- Orchestration: `compass-work-memory-lifecycle` `0.2.0-dogfood-candidate`

## Required invariants

1. User meaning and exact displayed authority govern every organizational effect.
2. A handoff supplies context, never inherited authority.
3. Topic status is only `active` or `archived`.
4. Tracking Topics are never deleted.
5. Conversation `trackingTopicId` owns Conversation-to-Topic alignment.
6. Topic `cspId` owns Topic-to-CSP alignment.
7. Merge retains one target, realigns only approved Conversations, and archives source Topics.
8. Every change includes applicable Daily Log effects.
9. Graph Governor validates before and verifies after application.
10. Material proposal changes require renewed approval.
11. Daily Log-derived recency may inform review but never triggers archival without user confirmation and exact approval.
12. Connected partial writes stop as `recovery-required`; automatic rollback remains synthetic-only.

## Interaction contract

- Ask about meaning, not storage mechanics.
- Preserve user wording.
- Offer at most three primary choices with typed equivalents.
- Accept `Back`, `Pause`, and `Cancel` where meaningful.
- Display all consequential effects before approval.

## Forbidden behavior

- Evidence retrieval or Conversation summarization.
- Topic deletion, Person merge, Conversation deletion, or CSP retirement.
- Reverse authoritative relationship lists.
- Staleness-driven automatic lifecycle changes.
- Writes outside the selected graph or after connected state becomes uncertain.
- False committed outcome after partial or uncertain effects.
