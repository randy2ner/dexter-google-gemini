---
name: compass-tracking-topic-interview
description: 'Conversationally prepare user-authorized Tracking Topic creation, refinement, merge, alignment, archival, or reactivation for a selected Compass graph. Preserve wording and history; never retrieve evidence, delete Topics, or bypass Graph Governor.'
---

# Compass Tracking Topic Interview

## Version and mode

- Version: `0.2.0-dogfood-candidate`
- Contracts: Shared Contracts and Graph Schema `0.3-beta-baseline`
- Orchestration: `compass-work-memory-lifecycle` `0.2.0-dogfood-candidate`
- Graph writes: one explicit user-selected Compass graph after exact approval

Read [the behavior contract](./references/behavior-contract.md) before preparing organizational effects.

## Owned outcome

Help the user express durable organization in their own language and prepare an exact proposal for one or more of:

- create or refine a Tracking Topic;
- align or unalign Conversations through Conversation `trackingTopicId`;
- align or unalign a Topic and CSP through Topic `cspId`;
- merge Topics while preserving history;
- archive an active Topic; or
- reactivate an archived Topic.

This Skill owns organizational meaning and proposal completeness. It does not retrieve Microsoft 365 evidence, validate its own structural safety, apply changes independently, or inherit authority from another Skill.

## Input gate

Accept either:

- a direct user request; or
- a minimized handoff from Daily Scan or Curator containing object IDs, approved concise context, current canonical relationships, and the user's request to explore organization.

A handoff is context, not authority. Verify the user's current intent before preparing effects. If Topic, Conversation, CSP, merge target, or scope identity is ambiguous, ask one clarifying question or return `blocked`.

A Curator archival handoff may include latest recorded Daily Log activity and the user's explicit statement that a Topic is stale or completed. Daily Log recency is context, not automatic lifecycle authority.

Inspect only the supplied relevant graph scope. Do not search outside it or access Email, Teams, Work IQ, OneDrive, web, or another source.

## Conduct the interview

Use short ordinary conversational turns. Ask about meaning, boundaries, and usefulness rather than files or YAML. Preserve the user's wording.

Offer no more than three primary choices at a time, with typed equivalents. Typical choices are:

- `Use this wording`, `Change`, `Cancel`;
- `Align`, `Leave unaligned`, `Back`; or
- `Approve`, `Change`, `Cancel`.

Accept `Pause` and `Cancel` throughout. Suggestions remain proposals. Do not pressure the user to organize every Conversation or align every Topic to a CSP.

Valid Topic status values are only `active` and `archived`. Do not store `paused` or `completed` as statuses. Explain those ideas in user-authored prose or map them to an accepted state only when the user chooses.

## Prepare canonical effects

### Conversation alignment

A Conversation owns its optional Topic relationship in `trackingTopicId`. Change that field on each approved Conversation. Never create a Topic-owned authoritative Conversation list.

### CSP alignment

A Tracking Topic owns its optional CSP relationship in `cspId`. Change that field on the approved Topic. Never create a CSP-owned authoritative Topic list.

### Merge

A merge proposal must:

1. identify one retained target Topic and each source Topic;
2. show final wording and `cspId` for the target;
3. enumerate every Conversation whose `trackingTopicId` changes;
4. archive each source Topic rather than delete it;
5. preserve user-authored content and historical relationships; and
6. include every applicable Daily Log effect.

Do not merge when one meaning-preserving result is not clear to the user.

### Lifecycle

Archival preserves the Topic file and history. Reactivation changes `archived` to `active` after exact authority. Tracking Topics are never deleted.

## Display the approval preview

Before a durable request, show:

- exact Topics, Conversations, and CSP relationships affected;
- before and proposed user-facing meaning;
- lifecycle effects and preserved history;
- Daily Log effects and date basis;
- unchanged objects that may look related but are outside scope; and
- `Approve`, `Change`, and `Cancel`.

A material change to wording, target, object set, relationship, status, or effect invalidates prior approval and requires a fresh preview.

## Build the change handoff

Prepare:

- `requestId`;
- `initiatingSkill: compass-tracking-topic-interview@0.2.0-dogfood-candidate`;
- `authoritySource`;
- `operationType`;
- `targetObjects`;
- `expectedEffects`, including each canonical relationship and Daily Log entry;
- `sourceState` fingerprints;
- minimized `evidenceReferences` only when required;
- `approvalReference`; and
- `correlationId`.

Account for every object in a multi-object merge or realignment. Do not hide secondary effects.

## Use Graph Governor

Submit the exact request for pre-write validation. Proceed only from `valid` against unchanged source state.

An authorized writer may apply only to the selected graph, with immediate fingerprint checks, deterministic order, and preservation of unmanaged content. Invoke Graph Governor after application to verify every object, relationship, Daily Log effect, and the touched closure.

Use synthetic recovery only under its exact authorization. On connected state, stop after any partial or unverifiable effect and return `recovery-required` for user-led resolution.

## Boundaries

Do not:

- delete a Tracking Topic;
- delete a Conversation or merge People;
- retire, replace, or delete a CSP;
- retrieve or rewrite source evidence;
- modify graph configuration;
- create reverse authoritative relationship lists;
- infer last activity or trigger lifecycle from staleness;
- treat a Daily Scan or Curator handoff as approval;
- write outside the selected graph or continue after connected state becomes uncertain; or
- claim runtime, persistence, or recovery confidence without evidence.

## Terminal reporting

Use one common outcome: `proposed`, `rejected`, `committed`, `committed-with-warnings`, `blocked`, `conflict`, `rolled-back`, `recovery-required`, or `failed`.

Report exact intended, completed, unapplied, rolled-back, uncertain, and preserved effects; approval and correlation references; Graph Governor decision; and next action. Never report a multi-object operation committed unless every authorized effect verifies.