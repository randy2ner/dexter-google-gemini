---
name: compass-activity-scan
description: "Scan an approved Email and Teams scope for customer work, propose new or updated Compass Activities, and apply reviewed graph changes with validation and read-back. Use for ordinary Compass updates after installation."
---

# Compass Activity Scan

## Version and outcome

- Version: `0.1.0-local-candidate`
- Mode: local candidate; required Copilot Cowork capabilities are unverified

Keep an existing Compass filing cabinet current by interpreting authorized customer-work evidence into reviewable Activities. A scan is complete only when coverage and every claimed graph effect are reported truthfully.

Read [Activity interpretation](references/activity-interpretation.md) and [graph writing](references/graph-write-contract.md) before proposing retrieval or graph changes.

## Start and scope

- Start when the user asks to scan, catch up, refresh customer work, or find recent Activities.
- Ask for the existing Compass graph root. Inspect only that root and validate `_compass/config.yaml` before retrieval.
- State the graph, customer-work purpose, and intended no-write scan effect.
- If the graph is absent or invalid, stop and suggest Installation or Governor review; do not create a replacement implicitly.

## Experience

### 1. Plan retrieval

Propose an editable plan containing:

- Email and Teams chat sources, including group or meeting chats when relevant;
- date range and result limits;
- customer-work purpose;
- continuation or pagination needed for complete-enough coverage; and
- unavailable sources or known host limitations.

Offer `Approve scan`, `Change plan`, and `Cancel`. Approval authorizes only the displayed read-only retrieval.

### 2. Retrieve and interpret

Stay within the approved scope. Apply [Activity interpretation](references/activity-interpretation.md).

- Include only meaningful customer work.
- Group by coherent work, not source containers.
- Compare evidence with existing Activity meaning and stable IDs; weak title, participant, or container similarity does not establish continuity.
- Derive `lastActivityAt` from the newest qualifying individual item.
- Follow available continuation and report source-specific coverage gaps.
- Reuse People only when stable identity is supported. Propose a new Person only with meaningful names and reviewed identity evidence.
- Place each Activity in exactly one Effort or Parking Lot. Ask one focused question when placement or continuity is consequentially ambiguous.

### 3. Review exact graph effects

Present:

- inspected, unavailable, incomplete, and uncertain evidence scope;
- Activities and People to create or update;
- customer significance, relationships, timestamps, and minimized provenance;
- exact graph-relative paths and preserved user content;
- one Daily Log effect per durable object change; and
- Governor preflight blockers or warnings.

Offer `Apply changes`, `Change proposal`, `Pause`, and `Cancel`. Retrieval approval is not write authority.

### 4. Apply and verify

After `Apply changes`:

1. Re-read every target and stop changed or unsafe operations.
2. Apply only reviewed changes using [graph writing](references/graph-write-contract.md).
3. Preserve stable identity, immutable creation time, unknown frontmatter, and user Markdown.
4. Append Daily Log entries for verified object effects.
5. Read back affected objects and logs.
6. Validate observed structure and effects through Governor rules.

Never change or delete source Email or Teams content.

## Authority and privacy

- Scan-plan approval authorizes read-only retrieval only.
- `Apply changes` authorizes only the displayed graph effects.
- Sending, publishing, disclosure, archival, Activity removal, and source mutation are outside this Skill's authority.
- Retain concise Activities and minimized provenance, not raw transcripts or unrelated evidence.

## Completion

Report `completed`, `partial`, `blocked`, `cancelled`, or `uncertain`. Include coverage, verified effects, unapplied proposals, blockers, and unresolved identity, placement, continuity, or recency. Do not report attempted writes as durable effects.

## Package boundary

The runtime candidate consists only of this `SKILL.md` and its files under `references/`. It has no external project-governance or legacy-artifact dependency.