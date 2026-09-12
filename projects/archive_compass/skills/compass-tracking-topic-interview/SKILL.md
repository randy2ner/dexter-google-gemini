---
name: compass-tracking-topic-interview
description: 'Conversationally build user-authorized Tracking Topics and narratives from direct input, accepted graph state, and explicitly authorized native Work IQ evidence. Preserve wording and history; never bypass Graph Governor.'
---

# Compass Tracking Topic Interview

## Version and mode

- Version: `0.7.0-production-test-candidate`
- Contracts: Shared Contracts `0.8-production-evidence-baseline` and Graph Schema `0.7-hpi-narrative-baseline` / schema version 2
- Orchestration: `compass-work-memory-lifecycle` `0.7.0-production-test-candidate`
- Graph writes: one explicit user-selected Compass graph after exact approval

Read [the behavior contract](./references/behavior-contract.md) before preparing organizational effects.

## Owned outcome

Help the user express durable organization in their own language and prepare an exact proposal for one or more of:

- create or refine a Tracking Topic;
- set or change whether the user has an action, is waiting, or is observing through Topic `attentionState`;
- align Conversations to a Topic or move them to Parking Lot through Conversation `trackingTopicId`;
- align or unalign a Topic and CSP through Topic `cspId`;
- add, remove, or re-add People through Topic `participantIds` and `excludedParticipantIds`;
- compose or revise a detailed user-approved Topic narrative from offered content or a minimized Daily Scan handoff;
- set or change optional Topic `tags` and `reviewBullet`;
- merge Topics while preserving history;
- archive an active Topic; or
- reactivate an archived Topic.

This Skill owns organizational meaning and proposal completeness. It may retrieve relevant Microsoft 365 evidence when the user explicitly authorizes a Topic-specific production purpose. It does not validate its own structural safety, apply changes independently, or inherit authority from another Skill.

## Input gate

Accept either:

- a direct user request; or
- a minimized handoff from Daily Scan or Curator containing object IDs, approved concise context, current canonical relationships, and the user's request to explore organization.

A handoff is context, not authority. Verify the user's current intent before preparing effects. If Topic, Conversation, CSP, merge target, or scope identity is ambiguous, ask one clarifying question or return `blocked`.

A Curator archival handoff may include latest recorded Daily Log activity and the user's explicit statement that a Topic is stale or completed. Daily Log recency is context, not automatic lifecycle authority.

Inspect only the relevant graph scope. When current evidence would improve the requested Topic, offer `Use Work IQ`, `Continue without retrieval`, or `Cancel`. After `Use Work IQ`, use all relevant Work IQ source types and continuation capabilities Cowork exposes for the authorized Topic purpose without arbitrary numeric caps or sample substitution. Disclose incomplete coverage and keep every derived meaning reviewable.

## Conduct the interview

Use short ordinary conversational turns. Ask about meaning, boundaries, and usefulness rather than files or YAML. Preserve the user's wording.

Offer no more than three primary choices at a time, with typed equivalents. Typical choices are:

- `Use this wording`, `Change`, `Cancel`;
- `Align`, `Move to Parking Lot`, `Back`; or
- `Approve`, `Change`, `Cancel`.

Accept `Pause` and `Cancel` throughout. Suggestions remain proposals. Do not pressure the user to organize every Conversation or align every Topic to a CSP.

Valid Topic status values are only `active` and `archived`. Do not store `paused` or `completed` as statuses. Explain those ideas in user-authored prose or map them to an accepted state only when the user chooses. An archived Topic requires an explicit boolean `success`; an active Topic has null or absent `success`.

Every Topic has one `attentionState`: `action`, `waiting`, or `observing`. Ask in ordinary language whether the user has a next action, is waiting on another person/event/decision/condition, or is retaining awareness without direct involvement. Preserve the exact accepted value until the user changes it. Evidence, participants, recency, lifecycle, and archival success may inform a displayed suggestion but never determine the value.

## Prepare canonical effects

### Conversation alignment

A Conversation owns its required Topic disposition in `trackingTopicId`. Set it to the approved Topic ID or `parking-lot` on each approved Conversation. Never remove, null, or empty the field, and never create a Topic-owned authoritative Conversation list.

When aligning a Conversation, include additions of its accepted `participantIds` to the Topic `participantIds`, except IDs present in that Topic's `excludedParticipantIds`. Moving or reassigning the Conversation does not remove participants from the prior Topic.

### CSP alignment

A Tracking Topic owns its optional CSP relationship in `cspId`. Change that field on the approved Topic. Never create a CSP-owned authoritative Topic list.

### Attention state

Topic creation requires one explicit accepted `attentionState`. A later change shows the current and proposed values and requires exact user authority. Use `action` only when the user has a next action; use `waiting` only when progress depends on someone or something else; use `observing` only when the user is not directly involved and has no current action.

Archival preserves the last accepted value as historical context. Before reactivation, ask whether that value still applies and include the confirmed or changed value in the same exact proposal. Attention-state changes create an `updated` Daily Log effect; they do not change status, success, participants, or relationships unless separately displayed and approved.

### Participant management

A Tracking Topic owns persistent `participantIds` and `excludedParticipantIds`.

- Add: add the confirmed Person ID to `participantIds`; ensure it is absent from `excludedParticipantIds`; log `person-linked`.
- Remove: remove the Person ID from `participantIds`; add it to `excludedParticipantIds`; log `person-unlinked`.
- Re-add: remove the Person ID from `excludedParticipantIds`; add it to `participantIds`; log `person-linked`.

Interpret direct input, accepted graph context, and authorized Work IQ into the best useful editable Topic and participant suggestion before asking for confirmation. Ask a follow-up question only when a material ambiguity cannot be represented safely. If the user supplies an email address, propose the matching complete name when available and include the normalized address for confirmation. If only a first name is available, ask for the last name and whether the request refers to an existing Person or a new Person. Require meaningful first and last names before creating or binding the Person. Do not infer identity from display-name similarity. Participant removal never deletes the Person, changes Conversation `participantIds`, or rewrites prior Daily Logs.

Do not request, infer, retrieve for retention, add, or update a Person `userPrincipalName`. Omit UPN from every Person proposal and handoff. A reviewed email address is accepted Person data, not UPN collection. Preserve a pre-existing value as unmanaged frontmatter during unrelated writes unless the user separately authorizes its removal.

### Topic narrative and review metadata

Accept narrative material from direct user input, accepted graph content, a minimized Daily Scan handoff, or Work IQ evidence explicitly authorized for the current Topic purpose. Use relevant email, chats, meetings, calendar, files, pages, transcripts, and people context when Cowork exposes them. Attempt complete relevant coverage through native continuation, report gaps, and never substitute sample, fictional, fixture, or synthetic evidence. Content remains optional; do not block Topic creation, alignment, or archival when retrieval is declined or unavailable.

Compose only applicable sections: `Summary`, `Impact`, `Troubleshooting Logic`, `Evidence Considered`, `Resolution`, `Outcome and Contribution`, `Lessons`, `Follow-Up Outside This Topic`, and `Review Bullet`. Distinguish observed facts, interpretation, disproved hypotheses, confirmed cause, and user reflection. Minimize raw evidence and unnecessary identity or operational detail.

`tags` is an optional unique lowercase kebab-case list. `reviewBullet` is an optional boolean. The accepted `hpi` and `solved` tags classify an HPI and resolved outcome but never determine `status`, `success`, or `attentionState`. Show every proposed tag, review flag, and material narrative section in the approval preview.

When the user keeps follow-up ideas only as archived context, preserve them under `Follow-Up Outside This Topic`. Do not suggest, ask about, create, or hand off another Topic unless the user initiates that work.

### Merge

A merge proposal must:

1. identify one retained target Topic and each source Topic;
2. show final wording, `attentionState`, and `cspId` for the target;
3. enumerate every Conversation whose `trackingTopicId` changes;
4. show the target Topic's proposed participant and exclusion lists; exclusions win over automatic funneling unless the user explicitly re-adds a Person;
5. archive each source Topic rather than delete it, with an explicit user-approved `success: true` or `success: false` for each source;
6. preserve user-authored content and historical relationships; and
7. include every applicable Daily Log effect.

Do not merge when one meaning-preserving result is not clear to the user.

### Lifecycle

Archival preserves the Topic file and history. Before proposing archival, ask whether the Topic was successful and translate only the user's answer into `success: true` or `success: false`. Include that value in the exact approval preview and write handoff. Do not infer success from completion language, staleness, recency, or other graph content.

Reactivation changes `archived` to `active` after exact authority, removes the `success` field rather than retaining or nulling it, and confirms or changes the Topic's retained `attentionState`. Tracking Topics are never deleted.

## Display the approval preview

Before a durable request, show:

- exact Topics, Conversations, People, attention-state values, participant/exclusion changes, and CSP relationships affected;
- exact Topic tags, review-bullet value, and material narrative additions or revisions;
- before and proposed user-facing meaning;
- lifecycle effects, archival success values or success removal, and preserved history;
- Daily Log effects and date basis;
- unchanged objects that may look related but are outside scope; and
- `Approve`, `Change`, and `Cancel`.

A material change to wording, target, object set, relationship, status, or effect invalidates prior approval and requires a fresh preview.

## Build the change handoff

Prepare:

- `requestId`;
- `initiatingSkill: compass-tracking-topic-interview@0.7.0-production-test-candidate`;
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

An authorized writer may apply only to the selected graph. Address every created or replaced file by its declared graph-root-relative path, never by OneDrive item ID. Use immediate fingerprint checks, deterministic order, and preservation of unmanaged content. Invoke Graph Governor after application to verify every object, relationship, Daily Log effect, and the touched closure.

On production content, stop after any partial or unverifiable effect and return `recovery-required` for user-led resolution.

## Boundaries

Do not:

- delete a Tracking Topic;
- delete a Conversation or merge People;
- remove or re-add a Topic participant without exact user authority;
- create or bind a Person from a first name alone;
- prune Topic participants because a Conversation becomes stale, is deleted, moves to Parking Lot, or is realigned;
- retire, replace, or delete a CSP;
- retrieve evidence without an explicit Topic purpose or retain raw source content by default;
- substitute sample, fictional, fixture, or synthetic evidence or impose arbitrary Work IQ result caps;
- modify graph configuration;
- create reverse authoritative relationship lists;
- infer last activity or trigger lifecycle from staleness;
- treat a Daily Scan or Curator handoff as approval;
- write outside the selected graph or continue after connected state becomes uncertain; or
- claim runtime, persistence, or recovery confidence without evidence.

## Terminal reporting

Use one common outcome: `proposed`, `rejected`, `committed`, `committed-with-warnings`, `blocked`, `conflict`, `rolled-back`, `recovery-required`, or `failed`.

Report exact intended, completed, unapplied, rolled-back, uncertain, and preserved effects; approval and correlation references; Graph Governor decision; and next action. Never report a multi-object operation committed unless every authorized effect verifies.