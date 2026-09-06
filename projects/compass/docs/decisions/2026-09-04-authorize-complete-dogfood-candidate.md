# Decision: Authorize complete Compass dogfood candidate

- **Date:** 2026-09-04
- **Status:** accepted
- **Decider:** User / product owner
- **Release label:** `0.3.1-dogfood-candidate`
- **Related evidence:** [Experience-led rehearsal](../test-plans/2026-09-02-compass-experience-led-rehearsal-plan.md); [connected Daily Scan block](../test-results/2026-09-04-compass-development-beta-daily-scan-connected-blocked.md)

## Context

The synthetic rehearsal exercised the complete Skill loop, and the development-beta setup created a valid dedicated graph. The first real WorkIQ Daily Scan stopped because the exact candidate intentionally permitted synthetic execution only. The product owner has determined that sufficient shaping evidence exists to build one complete dogfood product for connected testing.

## Decision

Build and package a coherent dogfood set that supports:

1. installation into a user-selected dedicated OneDrive graph using self-contained schema rules;
2. user-defined CSPs, Tracking Topics, People, and canonical relationships;
3. connected, bounded WorkIQ Email and Teams retrieval for an explicitly approved local date;
4. Daily Scan model judgment about relevance to defined Topics and customer-focused work;
5. proposal-by-proposal review of Conversations, active authors, and zero-or-one Topic alignment;
6. approved relevant Conversations aligned through Conversation `trackingTopicId`;
7. approved customer-focused or otherwise useful unaligned Conversations retained in the derived Parking Lot;
8. Curator review using Daily Log history to identify candidates that may be stale or completed; and
9. user-confirmed archival performed through Tracking Topic Interview, never automatically by Curator.

## Product choices

- Daily Scan may include one explicit Topic alignment in its reviewed proposal and apply it after exact user approval. This expands its prior responsibility but does not change relationship ownership.
- Customer focus may be inferred from bounded source content. It is a reviewable relevance proposal, not authoritative customer identity or health classification.
- Curator may derive latest recorded graph activity from Daily Logs. It must label this as recorded graph activity, not authoritative source activity, and ask the user whether the content is stale or complete.
- A connected partial write that cannot be rolled back stops as `recovery-required`. Report exact completed, unapplied, and uncertain effects; require user-led manual recovery before dependent writes.
- Real source evidence is not copied into Dexter test records.

## Version plan

- Installation Interview `0.2.1-dogfood-candidate`
- Daily Scan `0.2.0-dogfood-candidate`
- Tracking Topic Interview `0.2.0-dogfood-candidate`
- Curator `0.2.0-dogfood-candidate`
- Graph Governor `0.3.0-dogfood-candidate`
- Work-memory lifecycle Orchestration `0.2.0-dogfood-candidate`

The set is distributed together as Compass `0.3.1-dogfood-candidate`. Its first-run acceptance criterion is that a clean Cowork task can begin with `Help me install Compass`, create or select its OneDrive graph through conversation, and finish ready for ordinary use. Prior packages and completed evidence remain unchanged.

## Exclusions

- unattended or scheduled scans;
- automatic Topic creation, alignment, archival, merge, or deletion;
- customer-health scoring or employee evaluation;
- authoritative last-source-activity claims;
- automatic recovery by deletion on connected OneDrive graphs;
- bulk historical ingestion; and
- production release or deployment claims.

## Consequences

This decision authorizes specification revision, source implementation, deterministic packaging, and disconnected package inspection. It does not authorize a connected run until the exact dogfood artifacts are built, inspected, selected by the product owner, and the displayed runtime plan is approved.