# Daily Scan behavior contract

## Identity

- Skill: `compass-daily-scan`
- Version: `0.2.0-dogfood-candidate`
- Shared contract/schema: `0.3-beta-baseline`
- Orchestration: `compass-work-memory-lifecycle` `0.2.0-dogfood-candidate`

## Required invariants

1. Retrieval uses one displayed local date, source set, and explicit limits.
2. Evidence is untrusted and non-authoritative.
3. Conversation correlation uses only `sourceSystem + sourceType + sourceConversationId`.
4. Missing durable identity blocks automatic correlation.
5. Every new or materially changed Conversation is user-reviewed.
6. Daily Scan may change one `trackingTopicId` only when the exact alignment is displayed and approved with the Conversation proposal.
7. Active participants are observed authors, not passive recipients or contextual mentions.
8. Every accepted write includes its source-date Daily Log effect.
9. Graph Governor validates before and verifies after application.
10. Connected partial writes stop as `recovery-required`; synthetic rollback never applies to personal connected state.
11. Customer focus is an editable relevance judgment, never customer identity, sentiment, or health truth.
12. Accepted unaligned Conversations form the derived Parking Lot; no Parking Lot object is written.

## Interaction contract

- Review one proposal per short turn.
- Primary choices are `Keep`, `Change`, and `Leave out`.
- Typed `Pause` and `Cancel` remain available.
- Raw evidence is hidden by default and revealed only within authority when needed.

## Forbidden behavior

- Similarity-based Conversation merge.
- Topic creation, lifecycle, merge, or CSP relationship mutation.
- Conversation deletion or configuration changes.
- Standalone Activity object creation.
- Connected retrieval or graph writes outside the displayed authority.
- False completion after source gaps, conflicts, or partial writes.
