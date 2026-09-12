---
name: compass-installation-interview
description: "Set up Compass from a natural request such as 'Help me install Compass.' Interview the user about current customer Efforts, propose a bounded Microsoft 365 evidence scan, and create a reviewed OneDrive Markdown knowledge graph."
---

# Compass Installation Interview

## Version and outcome

- Version: `0.1.0-local-candidate`
- Mode: local candidate; required Copilot Cowork capabilities are unverified

Help the user establish one useful Compass filing cabinet containing current customer Efforts and grounded Activities. Setup is complete only when the reviewed Markdown/YAML graph and Daily Log effects are verified.

Read [the graph contract](references/graph-contract.md) and [the Activity interpretation contract](references/activity-interpretation.md) before proposing graph content.

## Invocation and starting context

- Start when the user asks to install, set up, or begin Compass.
- Explain briefly that Compass turns customer-work evidence into an editable OneDrive filing cabinet.
- Ask whether to create a new Compass graph or use an existing OneDrive folder. Accept `Cancel`.
- Before any access or write, state the human-readable target and intended effect.
- Inspect only the selected graph root. Do not search for other graphs or follow paths outside it.

## Experience

### 1. Understand the work

Ask one meaningful question at a time. Learn:

- the user's role and what customer work they want Compass to help remember;
- their current Efforts, using their terminology while representing each as an Effort;
- any Customer Success Plans that provide customer outcomes or strategic context;
- People who meaningfully participate in those Efforts; and
- the user's confirmed IANA timezone.

Do not ask the user to design files, YAML, IDs, or relationships. Ask a focused follow-up only when customer relevance, identity, Activity boundaries, Effort placement, privacy, or a consequential effect remains materially ambiguous.

### 2. Plan evidence retrieval

Propose one bounded plan before using Work IQ. State:

- Email and Teams chat sources to inspect, including group or meeting chats when relevant;
- date range;
- customer-work purpose;
- continuation or pagination needed for complete-enough coverage; and
- limits or known unavailable sources.

Offer `Approve plan`, `Change plan`, and `Cancel`. Approval authorizes only the displayed read-only retrieval. Do not retrieve before approval.

### 3. Interpret customer Activities

Use only direct user input and evidence inside the approved plan. Apply [the Activity interpretation contract](references/activity-interpretation.md).

- Create Activities only for meaningful customer work.
- Group by coherent customer work rather than thread, chat, meeting, or message boundaries.
- Preserve minimized provenance and distinguish evidence from interpretation.
- Derive `lastActivityAt` from the newest qualifying individual item, never the source-container start or generic modification time.
- Follow available continuation. If item-level timestamps or coverage are incomplete, leave recency uncertain rather than inventing a value.
- Relate each Activity to exactly one Effort or Parking Lot and include only meaningfully participating People.

### 4. Review the proposed filing cabinet

Present a concise, editable summary of:

- graph location and configuration;
- CSPs, Efforts, People, and Activities to create or update;
- each Activity's customer significance, Effort or Parking Lot placement, People, `lastActivityAt`, and minimized provenance;
- exact graph-relative file paths;
- Daily Log changes; and
- preserved existing or user-authored content.

Offer `Create`, `Change`, `Pause`, and `Cancel`. A changed target, object, relationship, filename, or effect requires an updated review. Do not expose implementation details that do not help the user understand an effect.

### 5. Create and verify

After explicit `Create` authority:

1. Re-read affected files and stop on conflict, ambiguous identity, unsafe parsing, or filename collision.
2. Create or verify `_compass/config.yaml` and the required object folders.
3. Apply only reviewed graph changes using [the graph contract](references/graph-contract.md).
4. Preserve unrecognized frontmatter and user-authored Markdown.
5. Add one Daily Log entry for each durable graph change.
6. Read back every affected file and validate identity, relationships, timestamps, paths, and expected content.

Never report an attempted or unverified write as successful.

## Required Skill Host capabilities

- Multi-turn conversation with correction, pause, and cancellation.
- User-authorized Work IQ retrieval from Email and Teams chat.
- Message-level content timestamps and continuation sufficient to distinguish source-container start from newest qualifying customer Activity.
- OneDrive folder selection plus Markdown/YAML create, update, read-back, and conflict-visible behavior.

If a capability is unavailable or unverified, state the exact limitation. Continue only where the remaining experience is useful and truthful; do not substitute sample data or hidden state.

## Authority, privacy, and safety

- Retrieval requires approval of its sources, date range, purpose, and limits.
- Graph creation or update requires review of the proposed durable effects and explicit `Create` authority.
- Do not send, publish, disclose, delete, or alter source email or chat.
- Retain summaries and minimized provenance rather than raw transcripts or unrelated content.
- Do not infer customer identity, People identity, commitments, outcomes, or source coverage.
- Do not overwrite conflicts, unsafe content, or colliding filenames.

## Partial, blocked, and failure behavior

- Before retrieval, cancellation causes no retrieval and no graph write.
- Missing or incomplete evidence access produces a bounded partial result and visible coverage gap.
- Uncertain Activity recency remains uncertain; source-container time is not a fallback.
- A blocked or conflicting write stops only the affected change unless continuing would make the graph inconsistent.
- Report `completed`, `partial`, `blocked`, `cancelled`, or `failed` with intended, verified, unapplied, and uncertain effects.

## Completion

Say `Compass is installed` only when configuration, reviewed objects, relationships, Activity timestamps, and Daily Log entries have been read back and verified. Otherwise state what remains incomplete and why.

## Package boundary

The runtime candidate consists only of this `SKILL.md` and its two files under `references/`. It has no external project-governance or legacy-artifact dependency.