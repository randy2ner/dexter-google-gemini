# Finding: Prior Skills require reconciliation before Cowork testing

## Metadata

- **First observed:** 2026-08-28
- **Status:** open
- **Severity:** high
- **Owner:** User / product owner
- **Affected skills/versions:** Compass Daily Scan Beta 1; Compass Knowledge Graph Installation Beta 1; Compass Tracking Topic Conversation Beta 2

## Summary

The three supplied artifacts contain substantial reusable interaction and safety material, but none conforms to the current Compass draft contracts and graph schema without revision. The packages encode decisions from the prior effort, depend on undefined prior architecture, or omit newly defined graph consequences. They should remain unchanged as reference specimens and must not yet move to `ready-for-test/`.

This is a static review. No package was imported, activated, or run in Copilot Cowork; no Microsoft 365 or graph data was accessed; and no runtime behavior was observed.

## Evidence

- [Accepted Compass charter version 1.0](../charter/compass-vision-and-scope-charter.md)
- [Compass Shared Contracts Specification](../specifications/compass-shared-contracts-specification.md)
- [Compass Graph Schema Specification](../specifications/compass-graph-schema-specification.md)
- [Graph Governor Skill Specification](../specifications/graph-governor-skill-specification.md)
- [Prior Skill artifact register](../inventory/prior-skill-artifact-register.md)
- Received artifact text and archive metadata identified by the hashes in the artifact register

Internal package references below use `artifact :: member:line-range`. They identify text observed inside the immutable received archive rather than repository files.

## Direct observations

### Compass Daily Scan Beta 1

- The Skill assigns Daily Scan responsibility for discovery, grouping, summaries, proposal review, and approved Conversation creation, while excluding Topic mutation (`compass-daily-scan-beta-1.skill :: SKILL.md:8-14`).
- It confirms one local calendar day and a read-only retrieval plan before evidence access (`SKILL.md:16-33`). It limits retrieval to 25 items per source and 50 total (`SKILL.md:25-31`).
- It separates source Conversation identity from message identity and refuses inferred grouping when source identity is unavailable (`SKILL.md:69-78`).
- It generates `conversation:<ulid>` as Compass identity under prior `ADR-0002` and treats source identity as optional provenance (`SKILL.md:77-82`; `references/behavior-contract.md:26-33`).
- Its proposed Conversation shape does not enumerate the current required `schemaVersion`, `createdAt`, `sourceSystem`, `sourceType`, `sourceConversationId`, and `activeParticipantIds` fields (`SKILL.md:80-88`).
- It requires every write to use a prior `Shared Graph Capability` and cites prior gate `TV-002` (`SKILL.md:106-119`).
- It does not specify the current same-operation Daily Log effect or a Graph Governor validation handoff.
- It includes ten synthetic evaluation cases, but they are expected-behavior definitions rather than executed evidence (`references/synthetic-eval-cases.md:1-109`).

### Compass Knowledge Graph Installation Beta 1

- The package contains only `SKILL.md` and identifies itself as Installation Beta 1 (`compass-knowledge-graph-installation-beta-1.skill :: SKILL.md:1-6`).
- It mandates a seven-day email preview before four setup cards (`SKILL.md:8-14`, `28-76`). The preview reviews mailbox metadata broadly and inspects up to five promising thread bodies (`SKILL.md:34-58`).
- It then performs a separately confirmed Email/Teams scan of up to 25 items per source and 50 total, reviews evidence topic by topic, and hands each topic to Tracking Topic Conversation (`SKILL.md:82-117`, `175-191`).
- It describes installing Compass and creating foundational documents (`SKILL.md:16-26`) but defines no current `_compass/config.yaml`, stable graph UUID, timezone confirmation, object file schema, installation-date Daily Log, or Graph Governor transaction.
- It closes with `External changes: 0` and refuses writes (`SKILL.md:193-225`), so its stated installation outcome and its defined executable effects do not match.
- It contains fixed adaptive-card and exact-message interaction details but no bundled behavior contract or synthetic evaluation cases.

### Compass Tracking Topic Conversation Beta 2

- The Skill claims ownership of all Tracking Topic mutation and Conversation-to-Topic connections (`compass-tracking-topic-conversation.skill :: SKILL.md:8-12`).
- It separates handed-off Conversation evidence from authority for Topic interpretation and refuses writes when authoritative state cannot be resolved (`SKILL.md:14-25`).
- It preserves user wording and requires complete previews for inferred or consequential operations (`SKILL.md:27-81`).
- It accepts Topic statuses `active`, `paused`, `completed`, and `archived` (`SKILL.md:50-60`; `references/behavior-contract.md:26-35`). The current graph schema accepts only `active` and `archived`.
- It depends on a prior `Shared Graph Capability`, source fingerprints, journaling, before-images, and conditional persistence (`SKILL.md:83-109`). These outcomes remain required in current contracts, but that exact capability and protocol have not been accepted or implemented in the current project.
- Failure recovery is handed to prior `Lifecycle Management` (`SKILL.md:98-107`; `references/synthetic-eval-cases.md:77-86`) rather than current Graph Governor terminology and boundaries.
- It does not specify the required same-operation Daily Log effect.
- It includes ten synthetic evaluation cases, but they are expected-behavior definitions rather than executed evidence (`references/synthetic-eval-cases.md:1-116`).

## Interpretation

### Daily Scan — revise

Preserve its bounded retrieval, evidence-versus-authority separation, source-identity caution, proposal review, injection resistance, and Topic handoff patterns. Reconcile its Conversation representation with the current required source-correlation fields, graph configuration timezone, Daily Log contract, Graph Governor handoff, and accepted persistence boundary. Prior `ADR-0002` and `TV-002` references cannot govern current Compass.

### Installation — split and revise

Separate installation/bootstrap from broad Daily Scan behavior. Installation should focus on guided setup, graph configuration, foundational objects, timezone confirmation, first Daily Log, and validated bootstrap. Any mailbox preview should be separately bounded and justified; the topic-by-topic Email/Teams scan belongs to Daily Scan. Resolve the mismatch between claiming installation and guaranteeing zero external changes.

### Tracking Topic Conversation — revise

Preserve its natural conversation, exact user wording, authority separation, forward-only relationship ownership, and honest failure patterns. Replace prior lifecycle and persistence dependencies with accepted current boundaries, restrict Topic status to `active` or `archived`, include the Daily Log effect, and define the Graph Governor handoff before authorizing implementation or connected tests.

## Reproduction conditions

The findings result from reading every archive member in the three artifacts identified by SHA-256 in the artifact register and comparing their text to the accepted charter and current draft specifications. They are consistently reproducible from those exact bytes. Runtime behavior is unknown.

## Impact

- Moving these artifacts directly to Cowork testing could test obsolete responsibilities rather than the current Compass design.
- A write-capable path could produce schema-invalid Topics or incomplete graph updates.
- Prior architecture names could be mistaken for currently available capabilities.
- Installation and Daily Scan responsibilities could overlap, making test outcomes and ownership ambiguous.
- Existing synthetic cases are valuable inputs, but treating them as passed evidence would fabricate confidence.

## Proposed action

1. Keep all three received artifacts immutable in `skill-exchange/incoming/`.
2. Use their behavior contracts and synthetic cases as reference inputs while defining the current Installation, Daily Scan, and Tracking Topic Interview responsibility specifications.
3. Decide and version the smallest accepted Graph Governor boundary and shared persistence handoff needed by the first test slice.
4. Create traceable current scenarios by adapting—not silently relabeling—the prior synthetic cases.
5. Author separately versioned Skill candidates only after explicit implementation authorization.
6. Begin Cowork characterization with read-only or write-disabled scenarios before any connected graph write.

## Resolution

Open. No artifact is accepted, rejected, modified, or approved for Cowork testing by this review.
