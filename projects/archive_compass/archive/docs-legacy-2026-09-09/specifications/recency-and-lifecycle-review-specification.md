# Specification: Recency and lifecycle review

## Document control

- **Status:** proposed technical specification
- **Version:** 0.1
- **Owner:** User / product owner
- **Applies to Skills:** Compass Daily Scan, Compass Tracking Topic Interview, Compass Curator, Graph Governor
- **Created:** 2026-09-06
- **Last updated:** 2026-09-06
- **Requirements:** `PR-RECENCY-001`, `PR-REVIEW-001`
- **Implementation authority:** None; this specification does not authorize Skill, schema, package, or graph changes

## Purpose

Define how Compass records the latest durable update to Tracking Topics and Conversations and how it presents items that meet approved criteria for purge or archival evaluation. This specification distinguishes desired technical behavior from current implementation and test evidence.

## Update timestamp

Tracking Topic and Conversation frontmatter includes:

```yaml
updatedAt: 2026-09-06T14:30:00Z
```

`updatedAt` is a timezone-explicit UTC ISO 8601 timestamp representing the most recent successfully verified durable change to that graph object.

Rules:

1. Creation sets `updatedAt` equal to `createdAt`.
2. A successful change to managed frontmatter or retained object content advances `updatedAt` to the operation time.
3. A relationship change advances `updatedAt` on the object whose canonical owner field changed.
4. Topic participant funneling advances the Topic timestamp when it changes `participantIds`.
5. An attempted, rejected, cancelled, blocked, conflicted, rolled-back, or unverifiable write does not advance `updatedAt`.
6. A Daily Log entry, source event, or related-object change does not advance an object timestamp unless that object itself changes.
7. `updatedAt` records graph modification. It does not claim latest Microsoft 365 source activity, latest user attention, or latest Topic Interview engagement.
8. Writers include the proposed timestamp in the approved effect set. Graph Governor validates monotonicity and verifies the exact persisted value after application.

## Evaluation review

Curator owns bounded evaluation review and recommendation. A review request identifies:

- object types in scope: Conversations, Tracking Topics, or both;
- one or more user-approved criteria;
- the evaluation time and timezone;
- exclusions or protected items; and
- the maximum review scope when the request is bounded by count or location.

Criteria may use accepted graph fields such as `updatedAt`, Topic `status`, and canonical relationships. A criterion is disclosed before evaluation and cannot silently become a lifecycle rule. Missing or invalid required timestamps are reported as integrity gaps rather than treated as old items.

The review output separates:

1. directly observed values;
2. whether each item matches the approved criteria;
3. the proposed disposition and rationale; and
4. the user decision still required.

Matching criteria creates no graph authority and no automatic change.

## Conversation purge path

`purge` means permanent removal of a Conversation through the existing explicit deletion contract; it is not a lifecycle status.

- Curator may recommend a Conversation for purge review but cannot delete it.
- The user reviews the exact Conversation or an explicitly bounded set and approves, keeps, or defers each proposed purge.
- The proposal discloses effects on Topic membership, Person relationships, provenance, links, and retained history.
- Graph Governor validates the exact authorized effects before application and verifies them afterward.
- A completed purge writes the required non-navigational Daily Log tombstone. It does not remove People or prune persistent Topic participants.

## Topic archive path

Tracking Topics are never purged. A matching active Topic may be recommended for archival.

- Curator may recommend review but cannot change lifecycle state.
- Tracking Topic Interview confirms the exact Topic, asks whether it succeeded, preserves its accepted `attentionState`, and presents the complete archive proposal.
- The user approves, changes, keeps, or defers the proposal.
- Graph Governor validates and verifies `status: archived`, boolean `success`, timestamp advancement, preserved relationships, and the Daily Log effect.

Archived Topics may still appear in later reviews when the approved criteria explicitly include them, but matching criteria does not reactivate, purge, or otherwise change them.

## Failure and truth rules

- Partial scope is never described as a whole-graph review.
- Items with unavailable or invalid comparison data are reported separately from matching and non-matching items.
- No purge or archive is reported as complete before post-write verification.
- A changed criterion, scope, candidate set, or effect requires renewed review and authority.

## Current implementation gap

The current accepted graph schema does not yet define authoritative Topic or Conversation `updatedAt`. Current Skills and packages therefore do not implement this specification. Schema integration, Skill responsibility changes, packaging, fixture construction, and runtime execution require separate authorization and impact assessment.