# Compass First Release - Technical Spec

Status: Accepted
Date: 2026-08-25
Accepted: 2026-08-25
Product requirements: `docs/product-spec.md`
Architecture decisions: PS-007 through PS-010 in `docs/project-state.md`; `docs/adr/0001-shared-graph-write-boundary.md`; `docs/adr/0002-decouple-conversation-identity-from-work-iq.md`

## Problem And Why Now

Compass needs an implementable contract for four portable Cowork Skills that share a user-editable Markdown/YAML graph in OneDrive. The approved product and architecture define authority, graph cardinality, workflow ownership, local validation, optimistic concurrency, and recovery, but do not yet define file layout, schemas, provenance records, or the transaction protocol.

This specification defines those accepted details before implementation. It does not claim that a Cowork packaging or OneDrive API mechanism has been verified.

## Goals

- Define one portable, human-readable graph contract for all four Skills.
- Preserve stable identity when users rename or move notes.
- Enforce the approved zero-or-one graph relationships without redundant back-references.
- Preserve user-authored Markdown while validating Compass-managed YAML.
- Make approved writes conflict-aware, recoverable, and honestly reportable.
- Retain enough Work IQ provenance to explain approved knowledge without storing raw transcripts by default.
- Provide implementation increments that can be validated independently.

## Non-Goals

- Implementing or packaging any Cowork Skill.
- Selecting an unverified Cowork manifest, runtime, or OneDrive API.
- Requiring an Obsidian community plugin or proprietary database.
- Migrating OneNote data.
- Storing raw email or chat content by default.
- Designing a multi-user service, hosted control plane, or cross-device lock service.
- Defining quantitative product-success baselines.

## Known, Assumed, And Open

### Known

- The authoritative store is Markdown with YAML frontmatter in a user-controlled OneDrive location.
- Obsidian and direct file editing are supported user surfaces.
- Work IQ evidence is provisional until the user approves a proposal.
- A Conversation aligns to zero or one Tracking Topic; a Tracking Topic aligns to zero or one CSP.
- A Conversation without `trackingTopicId` is in the Parking Lot projection.
- Workflow Skills own approved writes through one Shared Graph Capability.
- OneDrive multi-file atomicity is not assumed.

### Assumed For This Proposal

- The runtime can read, create, and conditionally replace files in the selected OneDrive location.
- Work IQ may expose identifiers or locators suitable for optional provenance, but they are not assumed to provide graph identity or cross-scan correlation.
- YAML parsing and deterministic hashing are available in the eventual runtime.
- A single user is the first-release graph owner; simultaneous edits can still occur across devices and applications.

If any assumption is false, the design returns to review before implementation.

### Open Verification Items

| ID | Question | Owner | Blocks |
|----|----------|-------|--------|
| TV-001 | What portable Cowork package and invocation contract is supported in the target tenant? | Product owner and implementation owner | Skill packaging |
| TV-002 | Which OneDrive API exposes content identity, version evidence, conditional replacement, rename, and same-folder staging in the target environment? | Implementation owner | Persistence adapter |
| TV-003 | Which optional stable Work IQ identifiers and evidence locators are available for email threads and chats? | Implementation owner | Automatic cross-scan correlation only; Conversation capture uses generated Compass identity under ADR-0002 |
| TV-004 | Can the target Cowork review surface represent a complete stable Yes/No proposal batch, or is a behaviorally equivalent interaction required? | Product owner and implementation owner | Review adapter |

## Proposed Component Design

```text
Installation Skill -----------+
Daily Scan Skill -------------+--> Shared Graph Capability --> OneDrive Markdown/YAML
Tracking Topic Skill ---------+             ^                         ^
Lifecycle Skill --------------+             |                         |
                                             +---- Obsidian/user edits-+

Work IQ --> Evidence Adapter --> workflow proposal context only
```

| Component | Responsibility | Allowed dependencies | Boundary contract |
|-----------|----------------|----------------------|-------------------|
| Installation Skill | Establish and verify a starter graph | Shared Graph Capability | In-process capability calls; no direct file writes |
| Daily Scan Skill | Review one selected local calendar day, group source-proven email threads and Teams chats, and create approved Conversations | Evidence Adapter, Shared Graph Capability | Read-only evidence calls plus in-process Conversation writes; no Topic mutation |
| Tracking Topic Conversation Skill | Create, update, connect, archive, and discuss Tracking Topics; own every Conversation-to-Topic connection | Shared Graph Capability | In-process capability calls; no direct file writes |
| Lifecycle Skill | Scan graph health, apply deterministic repairs, and recover transactions | Shared Graph Capability | In-process capability calls using repair/recovery operations |
| Evidence Adapter | Translate authorized Work IQ results into provisional source references | Work IQ | External read-only adapter; output is untrusted input |
| Shared Graph Capability | Parse, validate, resolve, plan, fingerprint, persist, recover, and report graph changes | Storage Adapter | Closed typed interface |
| Storage Adapter | List, read, stage, conditionally replace, and remove transaction artifacts | OneDrive | File operations with version/fingerprint evidence |

Dependency direction is from workflow Skills toward the Shared Graph Capability and adapters. The Shared Graph Capability must not invoke a workflow Skill or Work IQ. No workflow Skill may bypass the capability for authoritative writes.

## Vault Layout

```text
Compass/
  CSPs/
  Tracking Topics/
  People/
  Conversations/
  Daily Logs/
  _compass/
    graph.yaml
    transactions/
    quarantine/
```

- Object folders contain user-visible Markdown notes.
- `_compass/graph.yaml` records only graph format metadata, not domain objects.
- `_compass/transactions/` contains short-lived write-ahead transaction artifacts.
- `_compass/quarantine/` contains preserved invalid generated artifacts or recovery material that cannot be safely restored automatically. User-authored object files are reported in place rather than moved automatically.
- Parking Lot is computed by selecting Conversation notes with no `trackingTopicId`. It is not a folder, tag, status, or authoritative file.
- Filenames are presentation labels. Rename and move operations do not change identity.

Recommended filename form is `<readable-slug>--<id-suffix>.md`. Consumers resolve references from YAML `id`, never from a filename or wiki-link label.

## Common Note Contract

Every managed object note begins with YAML frontmatter and continues with user-editable Markdown. Compass owns only documented frontmatter keys and explicitly managed body sections. Unknown frontmatter keys and unmanaged body text are preserved byte-for-byte where the YAML serializer permits; an implementation must prove round-trip preservation before real-graph rollout.

```yaml
---
schemaVersion: 1
type: conversation
id: conversation:01K...
title: Contoso deployment review
createdAt: 2026-08-25T14:00:00Z
---
```

### Common Fields

| Field | Required | Contract |
|-------|----------|----------|
| `schemaVersion` | yes | Positive integer; version of this object schema |
| `type` | yes | Closed enum: `csp`, `tracking-topic`, `person`, `conversation`, `daily-log` |
| `id` | yes | Globally unique, immutable, type-prefixed identifier |
| `title` | yes | Non-empty user-facing label |
| `createdAt` | yes | RFC 3339 UTC timestamp; immutable after creation |

New Compass-created IDs should use a type prefix plus a UUID or another verified collision-resistant identifier supported by the runtime. The exact generator is an implementation verification item; identity semantics do not depend on sortability.

## Object Schemas

### CSP

```yaml
schemaVersion: 1
type: csp
id: csp:01K...
title: Contoso success plan
createdAt: 2026-08-25T14:00:00Z
status: active
```

- `status` is required and one of `active`, `inactive`, or `archived`.
- Deactivation changes status and preserves the note.
- A CSP does not store a reverse list of Tracking Topics.

### Tracking Topic

```yaml
schemaVersion: 1
type: tracking-topic
id: tracking-topic:01K...
title: Production readiness
createdAt: 2026-08-25T14:00:00Z
status: active
cspId: csp:01K...
```

- `status` is required and one of `active`, `paused`, `completed`, or `archived`.
- `cspId` is optional and, when present, resolves to exactly one CSP.
- A Tracking Topic does not store a reverse list of Conversations.

### Person

```yaml
schemaVersion: 1
type: person
id: person:01K...
title: Ada Example
createdAt: 2026-08-25T14:00:00Z
```

- Person identity is independent from display name.
- External contact identifiers are optional adapter-specific additions and must be reviewed for privacy before adoption.

### Conversation

```yaml
---
schemaVersion: 1
type: conversation
id: conversation:01K...
title: Contoso deployment review
createdAt: 2026-08-25T14:00:00Z
occurredAt: 2026-08-25T13:00:00Z
trackingTopicId: tracking-topic:01K...
personIds:
  - person:01K...
evidence:
  - source: workiq
    kind: teams-chat
    sourceId: <optional-opaque-message-or-conversation-id>
    sourceIdScope: message
    locator: <optional-source-locator>
    observedAt: 2026-08-25T13:15:00Z
    approvedAt: 2026-08-25T14:00:00Z
    approvalId: proposal:01K...
---
## Summary

Approved summary without a raw transcript.
```

- `occurredAt` is required.
- `trackingTopicId` is optional. Absence means Parking Lot; an empty string or sentinel value is invalid.
- `personIds` is optional, contains unique Person IDs, and is sorted for deterministic serialization.
- `evidence` is optional and records approved provenance only. It does not make Work IQ authoritative.
- Every Conversation receives a generated Compass ID in the form `conversation:<ulid>`, including a Conversation captured from Work IQ evidence.
- `sourceId` and `locator` are optional provenance and are retained only when policy permits. Neither determines graph identity.
- `sourceIdScope` is required when `sourceId` is present and is one of `message` or `conversation`; unknown scope is rejected rather than inferred.
- Automatic cross-scan correlation is allowed only when a separately verified adapter contract supplies a stable opaque conversation-scoped key. Without that key, Compass cannot automatically merge, update, attach, or suppress a Conversation.
- Weak metadata may be displayed as non-authoritative review context, but the user must choose create, attach to a named existing Conversation, or reject when correlation is ambiguous.
- A manually initiated Conversation may have no evidence entry.
- Evidence stores identifiers, kind, observation time, approval time, and proposal identity. It does not store message bodies, raw transcripts, participant addresses, or unrelated content by default.

### Daily Log

```yaml
---
schemaVersion: 1
type: daily-log
id: daily-log:2026-08-25
title: 2026-08-25
createdAt: 2026-08-25T23:59:00Z
date: 2026-08-25
---
```

- `date` is required and uses ISO 8601 calendar-date form.
- Daily Log body links are navigational, not authoritative relationship edges.
- Daily Logs do not duplicate Conversation, Tracking Topic, or CSP ownership fields in YAML.

## Relationship Ownership And Validation

| Relationship | Authoritative owner | Cardinality | Validation |
|--------------|---------------------|-------------|------------|
| Conversation to Tracking Topic | Conversation `trackingTopicId` | zero or one | Target exists and has type `tracking-topic` |
| Tracking Topic to CSP | Tracking Topic `cspId` | zero or one | Target exists and has type `csp` |
| Conversation to People | Conversation `personIds` | zero or many | Every unique target exists and has type `person` |

Reverse relationships are queries, never duplicated arrays. This prevents two files from claiming different versions of the same edge.

Validation has three levels:

1. **File validation:** parse YAML, validate common and type-specific schema, reject duplicate keys and duplicate list entries, preserve the Markdown body.
2. **Touched-closure validation:** validate every changed file, each outbound reference it owns, each current target, and every existing file whose owned reference the operation changes or invalidates.
3. **Health scan:** inspect the whole graph for duplicate IDs, unresolved references, schema violations, transaction residue, and lifecycle inconsistencies.

A workflow write requires levels 1 and 2. Unrelated failures found outside the touched closure are reported but do not block the write. Lifecycle health checks use level 3.

## Proposal And Authority Contract

Each scan proposal has:

```yaml
proposalId: proposal:01K...
action: create-conversation
targetId: conversation:01K...
baseFingerprints:
  <relative-path>: sha256:<digest>
evidenceRefs:
  - source: workiq
    kind: teams-chat
    sourceId: <optional-opaque-message-or-conversation-id>
    sourceIdScope: message
    locator: <optional-source-locator>
```

- A proposal is provisional and cannot be written as graph knowledge.
- A direct file edit that passes file and touched-relationship validation is authoritative without a second Compass approval.
- The review batch is complete only when every proposal has Yes or No.
- Yes authorizes only that proposal's displayed write set. Editing a proposal replaces its payload and records the user-authored correction.
- No causes no graph write. Follow-up explanation remains optional.
- Daily Scan creates an approved Conversation without `trackingTopicId`, then either leaves it in Parking Lot or hands its approved minimized context to Tracking Topic Conversation.
- Daily Scan has no `create-tracking-topic`, Topic-mutation, or Conversation-link operation.
- Tracking Topic Conversation may connect the displayed Conversation to an existing Topic or propose a new Topic and link. For a new Topic, one explicit confirmation authorizes the complete displayed Topic and Conversation link together.
- The combined create-and-link write set contains the new Topic file and the Conversation file whose `trackingTopicId` will change. The Shared Graph Capability prepares, validates, and journals both; applies the Topic first and Conversation link last; and reports success only after both effects validate.
- Until both effects complete, the Conversation remains without `trackingTopicId` and appears in Parking Lot. A rollback or `recovery-required` outcome is never reported as combined success.
- Before applying a Yes item, the capability recomputes and displays any material write-set change rather than extending the old approval silently.

## Persistence And Recovery Protocol

Multi-file changes are journaled and recoverable; they are not assumed to be atomic.

Every mutation is a transaction with a generated `transactionId` and these states:

```text
planned -> prepared -> applying -> committed
                            \-> rolling-back -> rolled-back
                            \-> recovery-required
```

### Prepare

1. Resolve the touched closure and read every source file.
2. Record relative paths, base content fingerprints, and storage version evidence when available.
3. Produce complete candidate bytes without modifying authoritative files.
4. Validate candidate files and touched relationships.
5. Write a transaction manifest and before-images under `_compass/transactions/<transactionId>/`.
6. Stage candidate files in the same transaction directory and verify their fingerprints.

### Apply

1. Immediately before each replacement, compare the authoritative file with its recorded base fingerprint and storage version.
2. On mismatch, do not replace that file. Begin rollback of already applied files.
3. Replace files in deterministic relative-path order and append each result to the manifest.
4. Re-read and validate every applied file and the touched closure.
5. Mark committed only after all intended replacements and post-write validation succeed.

### Rollback And Recovery

- Restore an applied file only if its current fingerprint still equals the transaction's recorded applied fingerprint. This prevents rollback from overwriting a later user edit.
- If a safe restore is impossible, mark `recovery-required`, preserve before-images and candidates, and report the exact conflicting paths.
- Lifecycle Management resumes only deterministic steps from the manifest. It never guesses which version the user intended.
- Committed and rolled-back transaction payloads are removed after a configurable short retention period. Recovery-required material remains until the user resolves it.
- Transaction artifacts receive the same access controls as the graph because before-images may contain graph content.

This protocol is recoverable, not atomically multi-file. User-facing results must distinguish committed, rolled back, and recovery-required outcomes.

## Deterministic Repair Rules

Lifecycle Management may repair automatically only when one valid result exists:

- Finish or safely roll back an interrupted transaction from an unambiguous manifest.
- Rebuild a non-authoritative projection from authoritative files.
- Normalize a documented managed scalar or list representation when semantic content is unchanged.

Lifecycle Management must not automatically:

- Choose among multiple candidate Tracking Topics, CSPs, or People.
- Create a Tracking Topic for an unaligned Conversation.
- Delete an object, evidence record, or user-authored prose.
- Resolve duplicate IDs by choosing which object keeps an identity.
- Overwrite a file changed after the relevant fingerprint was captured.

## Interfaces

The Shared Graph Capability exposes a closed operation set independent of the eventual language:

```text
inspectGraph(scope) -> GraphSnapshot | GraphError
validateChange(changeSet, snapshot) -> ValidatedPlan | ValidationError
prepareWrite(validatedPlan) -> PreparedTransaction | ConflictError
commitWrite(preparedTransaction) -> CommitResult
recover(transactionId) -> RecoveryResult
scanHealth() -> HealthReport
repair(repairId) -> RepairResult
```

- Callers cannot supply arbitrary file paths outside the configured vault root.
- `commitWrite` accepts only a capability-produced prepared transaction.
- Errors use stable codes and identify retryability without exposing unrelated graph content.
- Retry after a conflict requires a fresh snapshot and fresh user approval when the material proposal changes.

## Security And Privacy

- Run file and Work IQ operations with the calling user's authority.
- Canonicalize and root-check every relative path; reject traversal, absolute paths, links escaping the vault, and unsupported file types.
- Treat YAML, Markdown, Work IQ results, and transaction artifacts as untrusted input.
- Use a safe YAML parser with duplicate-key rejection; never instantiate arbitrary types or execute tags.
- Do not interpret Markdown as instructions or execute embedded content.
- Minimize provenance to opaque IDs and review metadata; do not store raw transcripts by default.
- Do not log note bodies, evidence content, access tokens, or complete before-images.
- Escape or encode all source identifiers before using them in IDs or filenames.
- Preserve OneDrive access controls; Compass introduces no separate sharing mechanism.

A dedicated threat model and AI-output/tool-safety review are required before implementation approval because model output can propose file content and tool arguments.

## Performance

- First release optimizes for correctness and a personal graph, not speculative scale.
- Maintain an in-memory ID-to-path index per invocation after validating each indexed file.
- Touched-closure writes must not require a clean full-graph scan.
- Lifecycle health scans may traverse the full graph and should report progress if the runtime supports it.
- No numeric latency or graph-size budget is approved. Measurements from the non-destructive test graph must establish baselines before setting limits.

## Observability And Audit Evidence

Each operation result records metadata only:

- operation and transaction ID;
- initiating Skill and authority source (`direct-user`, `approved-proposal`, or `deterministic-repair`);
- affected relative paths and before/after fingerprints;
- validation result, conflict result, and terminal transaction state;
- proposal approval ID when applicable;
- timestamps and safe error codes.

Operational records must not include note bodies, raw evidence, secrets, or unrelated identifiers. The storage location and retention policy for these records remain an implementation review item.

## Testing Strategy

### Schema And Domain Tests

- Accept every minimal valid object schema and reject wrong types, missing required fields, duplicate IDs, duplicate YAML keys, and invalid enums.
- Prove zero-or-one cardinality by schema shape and reference validation.
- Prove missing `trackingTopicId` yields Parking Lot and no stored Parking Lot edge.
- Prove reverse queries derive from forward-owned references.
- Round-trip fixtures containing unknown YAML keys and user-authored Markdown without unintended edits.

### Transaction Tests

- Create, update, rename, and multi-file changes commit only from matching base fingerprints.
- A change between prepare and commit stops without overwrite.
- Failure after each apply step either restores before-images or yields `recovery-required` without data loss.
- Rollback refuses to overwrite a later user edit.
- Re-running recovery is idempotent.

### Workflow Contract Tests

- A Work IQ result alone cannot invoke a write.
- Weak or message-scoped Work IQ metadata cannot automatically merge, update, attach, or suppress a Conversation across scans.
- A create proposal reserves one generated Conversation ID before review; edits and dispositions preserve that target ID.
- An ambiguous possible duplicate requires an explicit create, attach-to-named-existing, or reject disposition.
- Every proposal in a batch receives a disposition before apply.
- No items produce no graph changes.
- Daily Scan can select Parking Lot or Tracking Topic review but cannot perform a Topic mutation or Conversation-to-Topic connection.
- Tracking Topic Conversation can connect a displayed Conversation to an existing Topic or create a new Topic and link it under one complete explicit confirmation.
- A fault after either step of combined create-and-link rolls back both effects or yields durable `recovery-required` state without false success.
- Direct user creation and corrected rejected proposals receive user-authored authority.
- Partial and uncertain outcomes are reported without false success.

### Adapter And End-To-End Tests

- Use a fake Storage Adapter for deterministic fault injection and contract tests.
- Run integration tests against a non-production OneDrive test location after TV-002 is resolved.
- Run all four Skills against representative non-sensitive fixtures before using the owner's real graph.
- Verify resulting files open as ordinary Markdown in Obsidian without required plugins.

## Rollout And Reversal

1. **Contract fixtures:** publish schemas and fixture notes; verify parser, round-trip preservation, and graph rules. Stop on any content churn or ambiguous schema rule.
2. **Storage simulation:** implement the capability against a fault-injecting local adapter; verify every interruption point. Stop if any failure can silently lose or overwrite content.
3. **OneDrive test graph:** verify the storage adapter and version behavior with non-sensitive data. Stop if conditional replacement or recovery assumptions fail.
4. **Workflow integration:** connect one Skill at a time, beginning with Installation and read-only health inspection. Stop if any Skill bypasses the Shared Graph Capability.
5. **Owner pilot:** use representative evidence, then the owner's real graph only after explicit implementation and rollout approval.

Before real-graph rollout, reversal means removing the Skill package and test graph. After real-graph writes begin, reversal means disabling writes, preserving ordinary Markdown files, recovering any incomplete transaction, and removing Compass metadata only after export and user approval.

## Alternatives Considered

| Criterion | Proposed: YAML-owned forward references and journaled capability | Lifecycle as sole writer | Direct workflow file writes |
|-----------|---------------------------------------------------------------|--------------------------|-----------------------------|
| Complexity | One shared parser, validator, and transaction protocol | Adds command handoff and central workflow orchestration | Lowest initial code, duplicated rules later |
| Delivery | Capability can be built and tested before Skills | Every workflow depends on Lifecycle routing first | Fast first write, slow integrity fixes |
| Operability | One recovery and error model | One writer but a larger availability bottleneck | Conflicts and recovery vary by Skill |
| User editing | Fingerprints detect and preserve direct edits | Same capability possible, but indirect workflow ownership | High overwrite risk without shared protocol |
| Reversibility | Files remain ordinary Markdown; capability can be disabled | Similar file reversibility, harder workflow decoupling | Hard once incompatible writers exist |
| Failure mode | Transaction may require explicit recovery | Lifecycle outage blocks all writes | Silent drift or overwrite across writers |

The proposed design follows approved PS-009 and PS-010. Revisit the boundary if the target Cowork runtime cannot share a packaged capability or if verified OneDrive behavior cannot support compare-before-replace and durable recovery artifacts.

## Risks And Mitigations

| Risk | Consequence | Mitigation |
|------|-------------|------------|
| YAML serializer rewrites user formatting | User trust and reviewability loss | Fixture-based round-trip gate; patch managed keys or use a preservation-capable parser |
| OneDrive exposes insufficient conditional-write semantics | Lost-update risk | Resolve TV-002 before adapter implementation; fail closed and require reconciliation |
| Stable Work IQ correlation is unavailable | Duplicate Conversations or added review effort | Use generated Compass identity; forbid automatic correlation from weak metadata; require explicit create, attach, or reject when ambiguity matters |
| Transaction before-images increase sensitive-data copies | Privacy and retention exposure | Same ACLs, minimal retention, no body logging, explicit recovery cleanup |
| Full health scans become slow | Lifecycle workflow delay | Per-invocation index, progress reporting, measured limits before optimization |
| User edits managed YAML incorrectly | Invalid local graph region | Preserve file, report actionable errors, allow unrelated valid writes |
| Generated proposal contains unsafe paths or references | File or relationship corruption | Closed schemas, root-checking, reference validation, capability-produced plans only |

## Review And Sign-Off

Required reviewers:

- **Product owner:** confirms the object schemas, Parking Lot behavior, provenance minimum, and user-authority flow.
- **Implementation owner:** verifies TV-001 through TV-004 and confirms the contracts are implementable in the target environment.
- **Security/privacy reviewer:** reviews Work IQ data minimization, model-output handling, path safety, transaction artifacts, and logging.
- **Test owner:** confirms fault-injection, round-trip, workflow, and OneDrive integration coverage.

Approval means the schema and protocol become implementation constraints. It does not authorize implementation, package installation, access to real Work IQ data, writes to a real graph, deployment, or publication. Material changes to relationship ownership, authority, or conflict behavior require a new decision record.