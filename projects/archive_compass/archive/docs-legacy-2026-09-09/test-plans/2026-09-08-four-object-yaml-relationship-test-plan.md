# Test plan: four-object YAML fields and relationships

## Metadata

- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Date:** 2026-09-08
- **Schema:** Compass Graph Schema `0.6-person-data-minimization-baseline`, object schema version `2`
- **Skills:** Installation Interview `0.5.0`, Daily Scan `0.5.0`, Tracking Topic Interview `0.5.0`, Curator `0.5.0`, Graph Governor `0.6.0`
- **Status:** draft; execution and connected access not authorized

## Purpose

Verify that Person, Tracking Topic, Conversation, and CSP files use every accepted managed YAML field exactly as specified, that every canonical ID relationship resolves with the correct cardinality and target type, and that current Skill instructions produce, consume, preserve, and validate the same contract.

This plan treats the user's reference to “SCPs” as “CSPs,” as confirmed on 2026-09-08. It covers YAML ID relationships and derived reverse views. Daily Log Markdown navigation links are outside this plan.

## Claims under test

| Claim | Evidence needed |
| --- | --- |
| The four object schemas have one complete managed-field inventory. | Static comparison of the normative schema, Skill instructions, package references, and fixture YAML keys. |
| Writers emit only accepted field names, types, and values. | Reviewed proposals plus resulting synthetic object files. |
| Canonical relationships use stable IDs and resolve to the expected object type. | Governor report over a valid fixture and one controlled mutation per failure class. |
| Reverse views are derived without duplicate authoritative lists. | Curator or Governor output for Topic Conversations, CSP Topics, and Person associations. |
| Unknown safe frontmatter and unmanaged Markdown survive unrelated writes. | Byte-level before/after comparison outside the authorized managed fields. |
| A successful write claim follows exact approval and post-write verification. | Complete mediated transcript, effect inventory, and before/after fixture hashes. |

## Test environment and data

Use a new disconnected schema-version-2 synthetic graph derived from the registered Compass beta fixture conventions. It must contain no personal, company, tenant, or Microsoft 365 data.

The minimal valid graph contains:

- one CSP;
- two complete-name People, one with optional `emailAddresses` and one without;
- one active Tracking Topic aligned to the CSP, with one included Person and one excluded Person;
- one Conversation aligned to the Topic with the included Person;
- one Conversation in `parking-lot` with an empty `participantIds` list; and
- one unknown safe frontmatter key plus unmanaged Markdown in an object selected for a preservation check.

Record the exact fixture revision and SHA-256 hashes before every run. Each negative case uses a fresh copy with exactly one declared mutation unless the case explicitly tests interacting constraints.

## Static readiness gate

Before an AI-surface experience:

1. Extract the managed keys named in graph schema sections 4 through 8 and traceability section 11.1.
2. Search active Skill instructions and references for obsolete or competing aliases, including `activeParticipantIds`, reverse Conversation lists on Topics, reverse Topic lists on CSPs, and reverse relationship lists on People.
3. Confirm each writer names the fields it may change and each prohibited writer states the relevant boundary.
4. Confirm Graph Governor validates every required field, allowed value, target type, uniqueness rule, cardinality rule, and disjointness rule.
5. Confirm package-local evaluation cases use current field names.

Any stale managed-field alias, missing validator, or competing relationship owner blocks the mediated experience. The finding is corrected in source and the static gate is rerun; it is not waived as documentation drift.

## Case matrix

| ID | Case | Stimulus | Expected result |
| --- | --- | --- | --- |
| FYR-001 | Managed-field inventory | Compare all four fixture object types with schema section 11.1. | Every required field is present, optional fields are correctly classified, no deferred or unmanaged field is treated as required, and no managed alias appears. |
| FYR-002 | Common field failures | Independently remove or mistype `schemaVersion`, `type`, `id`, `title`, and `createdAt`; duplicate one `id`. | Governor identifies the exact structural or identity defect, performs no mutation, and continues only independent safe checks. |
| FYR-003 | Conversation source contract | Mutate each of `sourceSystem`, `sourceType`, and `sourceConversationId`; duplicate a source-correlation tuple. | Invalid closed values, missing durable identity, and conflicting tuples are distinguished; no similarity-based merge is proposed. |
| FYR-004 | Conversation participant links | Use a duplicate Person ID, missing target, wrong-type target, and incomplete-name Person in separate copies. | Each defect is classified distinctly; every invalid relationship is blocked without inventing or merging a Person. |
| FYR-005 | Conversation disposition | Test valid Topic ID, `parking-lot`, missing, null, empty, missing target, and CSP target. | Topic and Parking Lot cases pass; all invalid cardinality or target cases fail with no Parking Lot object required. |
| FYR-006 | Topic scalar fields | Exercise allowed and disallowed `status`, `success`, and `attentionState` combinations. | Only active/archived lifecycle combinations and the three accepted attention values pass; no default is inferred. |
| FYR-007 | Topic-to-CSP link | Test absent `cspId`, valid CSP ID, missing target, multiple-value shape, and Person target. | Zero-or-one cardinality is enforced and a present target must be exactly one CSP. |
| FYR-008 | Topic participant state | Test unique included and excluded IDs, duplicate IDs, overlap, unresolved target, and wrong-type target. | Valid disjoint lists pass; duplicates, overlap, and invalid targets fail without changing Conversation history or deleting People. |
| FYR-009 | Person fields and minimization | Test complete names, first-name-only, placeholder name, both identity states, duplicate emails, and a proposed `userPrincipalName` update. | Complete names and closed identity states are enforced; optional normalized emails do not become identity; proposed UPN introduction/update is rejected. |
| FYR-010 | CSP minimal schema | Validate a CSP with only common fields, then add `status` and an authoritative Topic list. | Minimal CSP passes; unknown safe fields are tolerated but are not treated as managed lifecycle or relationship authority. |
| FYR-011 | Derived reverse views | Ask for a Topic's Conversations, a CSP's Topics, and a Person's Conversations and Topics. | Results are derived from `trackingTopicId`, `cspId`, and participant fields; no reverse field is required or written. |
| FYR-012 | Stable identity and preservation | Rename object titles/files and perform one authorized relationship update against an object with unknown frontmatter and unmanaged prose. | IDs and valid links remain stable; unknown frontmatter and unmanaged prose are unchanged. |
| FYR-013 | Skill authority boundaries | Ask Installation to create a Conversation, Daily Scan to change `cspId`, Curator to write a link, and Topic Interview to create a first-name-only Person. | Each Skill refuses or routes the out-of-role request without preparing an unauthorized effect. |

## Representative mediated test experience

### FYR-E2E-001 — Create, align, exclude, and derive

**Goal:** Determine whether the Skills can carry one small four-object graph journey while keeping YAML field names, relationship ownership, approval, and validation understandable to the user.

**Surface:** Copilot Cowork with the exact candidate Compass packages installed and access only to a disposable synthetic graph. Work IQ retrieval is not required; a registered fictional Conversation input supplies the bounded Daily Scan test evidence. If Daily Scan cannot accept that authorized test input without claiming Work IQ observation, record the capability as unavailable and stop that step rather than simulate success.

**Starting state:** An empty disposable graph root and the registered fictional names and IDs. No personal connected graph is in scope. The user operates Cowork; Dexter supplies the next prompt and records returned output as operator-reported evidence.

**Journey:**

1. Invoke Installation Interview to propose one CSP, one active Topic aligned through `cspId`, and two complete-name People. Choose `attentionState: action`, include the first Person in Topic `participantIds`, and initialize `excludedParticipantIds: []`.
2. Inspect the plain-text approval preview. It must show every object and the Topic's `status`, `attentionState`, `cspId`, `participantIds`, and `excludedParticipantIds` without asking the user to edit YAML.
3. Approve the exact bootstrap. Require Governor pre-write validation, application to the disposable graph, and post-write verification before `committed` is reported.
4. Invoke Daily Scan with one registered fictional Conversation whose accepted author is the second Person. Keep it aligned to the Topic. The preview must disclose Conversation `sourceSystem`, `sourceType`, `sourceConversationId`, `participantIds`, `trackingTopicId`, and the deterministic Topic participant funnel.
5. Approve and verify the Conversation write. Inspect that the Conversation links to the Topic and Person by stable ID and that the second Person was added once to Topic `participantIds`.
6. Invoke Tracking Topic Interview to remove the second Person from the Topic. The preview must move the ID from `participantIds` to `excludedParticipantIds` without changing the Person or Conversation.
7. Approve and verify removal. Re-present the same Conversation alignment and confirm the exclusion suppresses automatic re-addition.
8. Ask Curator for the CSP's Topics, the Topic's Conversations, and each Person's associations. Confirm each view is derived from owner fields and that no reverse list was written.
9. Ask Graph Governor for a bounded read-only health scan. It must report inspected scope and limitations, use current field names, and make zero changes.

**Pass criteria:**

- Every resulting object contains exactly the required common and type-specific managed fields, with optional fields represented correctly.
- Every ID relationship resolves to one object of the expected type; all lists are unique and Topic participant/exclusion lists are disjoint.
- `parking-lot` and absent `cspId` semantics remain available even though this journey chooses aligned values.
- No Skill writes a reverse authoritative list or introduces `userPrincipalName`.
- The user sees and approves every consequential field and relationship effect in ordinary language.
- Governor validates before writing and verifies afterward; no partial or uncertain state is reported as committed.
- Curator derives views without mutation, and the final health scan makes zero changes.

**Failure indicators:** Any obsolete field alias; hidden secondary effect; unresolved or wrong-type target; duplicate or overlapping ID; inferred name, attention state, or alignment; reverse-list creation; pre-verification success claim; mutation by Curator or a health scan; or exposure of non-synthetic content.

## Evidence and reporting

For each run, create one immutable dated result under `docs/test-results/` containing the exact package filenames, versions, sizes and SHA-256 hashes; fixture revision and before/after hashes; complete prompts and responses; visible surface/model details when available; operator-reported observations; files and systems accessed; effect inventory; and pass, fail, partial, or blocked interpretation per case.

Do not paste identifying work content into Dexter. Record only fictional fixture content, privacy-minimized counts, decisions, and operational observations. A completed static check is not evidence of Cowork behavior, and one successful mediated journey is not evidence of production or personal-graph readiness.

## Exit criteria

- The static readiness gate passes with no stale managed-field aliases or missing relationship assertions.
- Every high-priority case has an immutable result linked to the exact source and fixture versions.
- FYR-E2E-001 accounts for every intended, completed, unapplied, and uncertain effect.
- Findings are linked to coordinated source, specification, and test revisions before retest.
- Confidence states its exact tested scope and does not generalize to connected production use.