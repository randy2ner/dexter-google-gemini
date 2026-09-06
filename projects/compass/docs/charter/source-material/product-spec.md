# Product Spec: Compass First Release

Status: Approved
Approved: 2026-08-25

## Problem And Why

The user currently keeps up with work knowledge manually in OneNote. Capturing, organizing, connecting, and recovering context requires continuous effort, while relevant evidence remains fragmented across Microsoft 365 email and chat.

Compass helps the user learn and practice Obsidian-style linked knowledge management with an AI solution partner. It must reduce manual upkeep without replacing the user's judgment or silently turning AI interpretations into authoritative knowledge.

## Goals

- Establish a user-controlled, Obsidian-compatible work-memory graph.
- Help the user transition from manual OneNote knowledge management.
- Teach linked knowledge management through normal use.
- Turn Microsoft 365 evidence into reviewable knowledge proposals.
- Preserve the user's language, decisions, and historical context.
- Complete routine delegated work with minimal interruption.
- Deliver four usable Skills: Installation, Daily Scan, Tracking Topic Conversation, and Lifecycle Management.

## Non-Goals

- A standalone Compass application.
- Automatic promotion of Work IQ findings into authoritative knowledge.
- Raw conversation transcript storage by default.
- Automatic migration of the existing OneNote corpus.
- Destructive deletion as normal CSP or Tracking Topic lifecycle behavior.
- Autonomous changes to user-authored guidance.
- Requiring the user to manage routine execution details.
- Replacing OneNote as a Microsoft product.

## Users And Roles

- **Primary user:** An individual Microsoft 365 Copilot user who manages CSPs, Tracking Topics, people, Conversations, and changing work context.
- **Compass:** An AI solution partner that retrieves evidence, proposes connections, performs authorized routine work, and preserves user authority.
- **Work IQ:** The evidence provider for relevant Microsoft 365 email, chat, and conversation context.

## Knowledge Model

The first release works with CSPs, Tracking Topics, People, Conversations, Daily Logs, relationships among these objects, and supporting evidence for proposed changes.

The authoritative alignment graph is:

```text
Conversation -- zero-or-one --> Tracking Topic -- zero-or-one --> CSP
```

A Conversation with no `trackingTopicId` is in the Parking Lot. Parking Lot is a projection of unaligned Conversations, not a separate stored relationship or container. A Conversation cannot align to more than one Tracking Topic, and a Tracking Topic cannot align to more than one CSP.

Markdown files and YAML frontmatter form the durable, user-controlled representation. The files live in OneDrive and remain usable through Obsidian. User-authored and user-approved knowledge is authoritative. Work IQ evidence remains non-authoritative until approved.

## Scenarios And Flows

### Installation

1. The user invokes the Installation Skill.
2. Compass establishes or validates the graph location in OneDrive.
3. Compass prepares the structures needed by the first-release Skills.
4. Compass checks that the graph can be opened and navigated with Obsidian.
5. Compass reports what was prepared and any unresolved setup problem.

### Daily Scan

1. The user asks Compass to review one calendar day; Compass proposes today by default and interprets the selected date in the signed-in user's local timezone.
2. After the user confirms the displayed read-only plan, Compass discovers email activity in Inbox and Sent Items and Teams chat activity for that day before applying known-customer or Topic relevance.
3. Compass groups evidence into one proposed Conversation per distinct source-proven email thread or Teams chat. Missing conversation-level identity is `Unknown` and never permits an inferred merge.
4. Compass produces one consolidated list of evidence-backed Conversation proposals with a Parking Lot or Tracking Topic review next state.
5. The user assigns Yes or No to every proposal; edits preserve its stable proposal and Conversation IDs and reset it to Pending.
6. Daily Scan creates all confirmed Conversations and no rejected Conversations through the Shared Graph Capability. It creates each Conversation without `trackingTopicId` before any Topic review.
7. Daily Scan hands approved minimized Conversation context to Tracking Topic Conversation when Topic review is selected; Daily Scan performs no Topic mutation or Conversation-to-Topic connection.
8. Compass reports the applied, rejected, pending, unavailable-source, and unresolved results without claiming an incomplete write succeeded.

### Tracking Topic Conversation

1. The user discusses a Tracking Topic naturally with Compass.
2. Compass uses authoritative graph context and known preferences.
3. An unambiguous direct user instruction may be applied as user-authored knowledge without redundant confirmation.
4. Ambiguous or consequential changes are summarized for confirmation.
5. Compass creates, updates, connects, or archives the Tracking Topic only when the user confirms, edits, or initiates that change.
6. Compass reports the resulting changes without asking the user to direct routine file operations.

### Conversation Capture

1. Compass identifies a conversation worth preserving.
2. It creates a useful summary rather than storing the raw transcript by default.
3. YAML frontmatter links the Conversation to applicable People and, when known, one existing Tracking Topic.
4. If no appropriate Tracking Topic exists or the relationship remains uncertain, Compass leaves `trackingTopicId` absent so the Conversation appears in Parking Lot.
5. Any interpretation derived from Work IQ follows the scan confirmation model.

### Lifecycle Management

1. The user requests a CSP or Tracking Topic lifecycle change or a graph health check.
2. Compass identifies affected Tracking Topics, Conversations, and historical relationships.
3. Required active Tracking Topics are archived before CSP deactivation.
4. The CSP is deactivated rather than deleted.
5. Historical files and relationships remain navigable.
6. Compass reports completed lifecycle actions, safe deterministic repairs, recovery actions, unresolved ambiguity, and preserved history.

## Functional Requirements And Acceptance Criteria

### FR-1: Portable Cowork Skill Set

Compass must be delivered as portable Microsoft 365 Copilot Cowork Skills.

- Installation and each mandatory Skill can be invoked through the target Cowork environment.
- The first release does not depend on a separately hosted Compass user interface.
- Moving the Skill package through the supported portability mechanism does not require rewriting the user's graph.

### FR-2: User-Controlled Storage

Compass must keep authoritative graph content as Markdown and YAML in a user-controlled OneDrive location.

- A user can inspect graph content without invoking Compass.
- Obsidian can open the graph as ordinary Markdown notes.
- Compass does not require a proprietary database to interpret the authoritative content.
- Existing user-authored content is not overwritten without authorization.

### FR-3: Authority Hierarchy

User-authored and user-approved graph knowledge must outrank scan-derived evidence.

- Conflicting Work IQ evidence produces a proposal rather than silently replacing an approved graph value.
- No scan-derived proposal changes an authoritative file before approval.
- Rejected evidence does not alter authoritative knowledge.
- Applied changes retain provenance that distinguishes approved knowledge from supporting evidence.
- A direct user edit that passes graph validation is authoritative without a second Compass approval.

### FR-4: Consolidated Proposal Review

Daily Scan must present all proposed Conversations as one reviewable list.

- Every proposal has a stable identity, proposed action, affected graph object, and supporting evidence.
- Every proposal requires an explicit Yes or No disposition.
- Review cannot be represented as approved while any item lacks a disposition.
- All Yes items are applied, no No item is applied, and the result accounts for every proposal.

### FR-5: Rejected Proposal Follow-Up

Compass must respond intelligently to rejected proposals.

- Inaccurate content prompts for a correction.
- Evidence that appears valid but unsuitable prompts for an explanation.
- Follow-ups are batched where practical.
- The user may decline to explain without the proposal being applied.
- A supplied correction is treated as user-authored knowledge.

### FR-6: Evidence Presentation

The user must be able to understand why each scan proposal exists.

- Each proposal identifies its supporting email or chat evidence sufficiently for review.
- Unsupported model inference is not presented as source evidence.
- Missing or inaccessible evidence is disclosed.
- Evidence presentation minimizes unnecessary exposure of unrelated content.

### FR-7: Conversation Representation

Stored Conversations must contain a summary and valid graph relationships.

- A captured Conversation contains a useful summary.
- YAML frontmatter links applicable People and zero or one existing Tracking Topic.
- A Conversation without `trackingTopicId` appears in Parking Lot.
- Daily Scan proposes Parking Lot or Tracking Topic review but does not select, create, update, archive, or connect a Tracking Topic.
- When source conversation identity is unavailable, message IDs and other weak metadata do not permit inferred grouping or cross-scan correlation.
- Raw transcripts are not stored by default.
- An empty scan does not fabricate a Conversation or relationship.

### FR-8: Tracking Topic Conversation

The user must be able to manage Tracking Topics through natural conversation.

- The user can initiate creation, update, connection, and archival of a Tracking Topic conversationally.
- Unambiguous direct instructions do not trigger redundant approval prompts.
- Consequential or ambiguous interpretations are confirmed before application.
- Tracking Topic Conversation owns every Tracking Topic mutation and every Conversation-to-Tracking-Topic connection, including requests handed off by Daily Scan.
- When a new Tracking Topic fits a displayed Conversation, the complete Topic proposal and Conversation link are displayed together and one explicit confirmation authorizes both together.
- The combined operation is not reported successful unless both Topic creation and Conversation linking complete and validate; until then the Conversation remains in Parking Lot.
- Tracking Topic updates preserve existing approved guidance unless replacement is explicit.
- Compass reports completed changes in user-facing terms rather than routine file-operation details.

### FR-9: Historical Retention

Lifecycle operations must preserve historical knowledge.

- CSP deactivation does not delete its file or relationships.
- Required active Tracking Topics are archived before deactivation completes.
- Historical Conversations remain connected and navigable.
- Archived Tracking Topics remain available for historical retrieval.
- Lifecycle completion reports what changed and what was retained.

### FR-10: Low-Interruption Delegation

Compass must behave as a solution partner rather than a micromanaged assistant.

- Compass uses approved preferences, graph knowledge, current context, and sensible defaults for routine choices.
- Related approvals and follow-ups are batched where practical.
- Compass asks only about consequential, genuinely ambiguous, or explicitly approval-gated decisions.
- Existing conventions resolve routine file names, ordering, and mechanical operations without user questions.
- A release fails acceptance if normal workflows repeatedly require the user to direct routine execution.

### FR-11: User Language Preservation

Compass must preserve the user's wording and approved guidance.

- Existing user-authored prose is not silently rewritten during unrelated updates.
- A proposed substantive wording change is visible before approval.
- Regeneration or maintenance preserves approved guidance unless replacement is explicit.

### FR-12: Installation Completion

Installation must leave a usable starter graph.

- The folder structure exists and is accessible to the Skills.
- At least one object-type Markdown file exists with valid YAML frontmatter.
- The graph opens and can be viewed in Obsidian.
- A failed or partial setup is reported honestly and is not labeled complete.

### FR-13: Graph Integrity, Concurrency, And Recovery

Every Skill that writes authoritative graph content must use the Shared Graph Capability for validation and persistence.

- Before a write, the capability validates each changed file and every relationship touched by the change.
- A locally valid write may proceed when unrelated graph damage exists; the unrelated damage is reported and is not silently repaired as part of that write.
- Writes use source fingerprints or equivalent version evidence and stop rather than overwrite when a source changes after it was read.
- Concurrent changes are reconciled automatically only when one result is uniquely deterministic; otherwise Compass leaves the files unchanged and requests user reconciliation.
- Multi-file changes are journaled and recoverable. Compass does not claim atomic success unless every intended write is validated and completed.
- A failed or interrupted write is rolled back or left with enough durable recovery state for Lifecycle Management to restore a validated graph.
- Lifecycle Management automatically applies only safe, uniquely determined repairs and reports them; ambiguous repairs do not alter files.

## Approved Technical Boundaries

- Installation, Daily Scan, and Tracking Topic Conversation own their authorized workflow writes. Daily Scan owns Conversation creation; Tracking Topic Conversation owns all Topic activity and Conversation-to-Topic connections. Lifecycle Management owns graph health scans, deterministic repair, recovery, and reporting.
- All four Skills depend on one Shared Graph Capability for schema and domain validation, reference checks, source fingerprints, conditional writes, journaling, rollback, and recovery.
- Work IQ supplies provisional evidence only. It does not write authoritative graph state or decide graph relationships.
- OneDrive hosts the Markdown/YAML files, and Obsidian is a user editing and navigation surface. The design does not assume OneDrive provides atomic multi-file transactions.
- Validation and persistence rules are centralized in the Shared Graph Capability even though workflow ownership remains distributed among the Skills.

## Edge And Error Behavior

- Empty scans return an honest no-proposals result and create no fabricated knowledge.
- Inaccessible Work IQ evidence is reported and cannot support an authoritative update.
- Partial proposal-application failure identifies each applied, unapplied, and uncertain item; uncertain writes are not reported as successful.
- Invalid or conflicting graph content is preserved for user recovery and surfaced rather than silently discarded.
- Permission failures leave authoritative graph content unchanged.
- A source-version change after review stops the write unless reconciliation is uniquely deterministic.
- Unrelated graph damage is reported but does not block a valid write whose changed files and touched relationships pass validation.
- Error taxonomy and user-facing error-state design remain technical-design work.

## Dependencies

- Microsoft 365 Copilot Cowork support for portable Skills.
- Work IQ access to the user's authorized Microsoft 365 evidence.
- OneDrive storage and permissions.
- Obsidian compatibility with selected Markdown and YAML conventions.
- Adaptive Card capabilities for consolidated review where supported.
- Detailed Markdown/YAML schemas and file conventions consistent with the approved graph and write boundaries.

## Rollout Intent

The first release begins with the product owner using a non-destructive test graph and representative, non-sensitive sample evidence. It progresses to the owner's real graph only after installation, authority, review, retention, and recovery criteria are demonstrated.

Broader use waits until all four mandatory Skills pass their acceptance criteria and excessive-questioning behavior has been evaluated across complete workflows. Detailed rollout mechanics remain future design work.

## Success Metrics And Guardrails

Initial success is demonstrated when the user:

- Completes installation and opens the resulting graph in Obsidian.
- Uses all four mandatory Skills successfully.
- Transitions recurring work-knowledge maintenance away from manual OneNote-only practices.
- Can trace every scan-derived authoritative update to an explicit approval.
- Experiences no silent loss of historical knowledge during lifecycle operations.
- Completes routine workflows without repeatedly directing mechanical choices.
- Finds the graph useful enough to continue practicing linked knowledge management.

No numeric adoption or time-saving target has been approved. Baselines may be established during the owner rollout rather than invented in advance.

Guardrails:

- Zero unapproved scan-derived authoritative changes.
- Zero normal lifecycle deletions of retained historical knowledge.
- Zero falsely reported successful writes.
- No release acceptance when routine workflows exhibit approval fatigue or micromanagement.

## Known, Assumed, And Open

### Known

- OneNote is the current manual workaround.
- Learning Obsidian-style knowledge management is a product goal.
- Compass is intended to be an AI solution partner.
- Cowork, Work IQ, OneDrive, Markdown/YAML, and Obsidian define the product boundary.
- The four mandatory Skills and authority rules are approved.
- The review, Conversation, lifecycle, and delegation behaviors are approved.
- The Tracking Topic domain model and Shared Graph Capability architecture are approved.

### Assumed

- Adaptive Cards can support the desired consolidated review, or an equivalent Cowork-native interaction can preserve the behavior.
- The user can access relevant Work IQ evidence and write to the selected OneDrive location.
- OneNote migration is unnecessary for first-release value.

### Open, Non-Blocking For Product Scope

- Exact Markdown/YAML schemas and folder conventions.
- Provenance representation for approved Work IQ evidence.
- Quantitative success baselines.

These are inputs to technical planning, not permission to begin implementation. Remaining technical choices will be handled by the appropriate design owner and recorded before implementation.