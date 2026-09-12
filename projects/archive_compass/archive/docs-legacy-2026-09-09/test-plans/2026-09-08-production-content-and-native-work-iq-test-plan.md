# Test plan: Production content and native Work IQ

## Metadata

- **Owner:** User / product owner
- **Date:** 2026-09-08
- **Status:** planned controlled release gate; artifact-first production shaping now precedes execution
- **Milestone:** [Transition from synthetic testing to production release testing](../decisions/2026-09-08-declare-production-release-testing-milestone.md)
- **Sequencing decision:** [Build target artifacts before deriving and testing final Skills](../decisions/2026-09-08-adopt-artifact-first-production-shaping.md)
- **Requirements:** `PR-WIQ-001`
- **Contract:** `SC-EVID-001` in Shared Contracts `0.8-production-evidence-baseline`
- **Baseline package set:** [Production-content candidates](../inventory/compass-production-content-candidate-package-set.md); the controlled run uses the later derived or explicitly reaffirmed exact set

## Goal

Determine whether the exact derived production candidate set is releasable by evaluating how it reproduces accurate, useful Compass objects from real user-authorized work evidence while using Cowork's relevant Work IQ capability without artificial source restrictions, numeric result caps, sample-data substitution, or undeclared shaping assistance.

## Claims

| ID | Claim | Required observation |
| --- | --- | --- |
| PROD-WIQ-001 | Installation uses direct answers and all relevant authorized Work IQ exposed for setup. | Cowork identifies the source types and retrieval paths it used, attempts continuation where exposed, and reports unavailable or incomplete coverage. |
| PROD-WIQ-002 | Daily Scan seeks complete relevant coverage for the approved period, purpose, and work scope. | No arbitrary per-source or total cap appears; retrieved candidates are deduplicated and coverage gaps are disclosed. |
| PROD-WIQ-003 | Topic Interview can retrieve current evidence for an explicit Topic purpose. | Retrieved evidence remains provisional until the user reviews the proposed narrative, metadata, People, and links. |
| PROD-WIQ-004 | Curator uses authorized Work IQ only as non-authoritative current context. | Curator distinguishes graph observation, source context, and interpretation, then routes proposals without writing. |
| PROD-WIQ-005 | Governor preserves role separation. | Governor retrieves no Work IQ, judges no narrative truth, and validates only authority, schema, identity, preservation, and declared effects. |
| PROD-WIQ-006 | Production evidence is never replaced with sample content. | Missing or inaccessible evidence produces an explicit limitation, `Partial`, or `Blocked`, never fictional, fixture, synthetic, or sample objects. |
| PROD-WIQ-007 | Durable content remains user-controlled. | Cowork shows a reviewable proposal and obtains exact approval before writes; post-write verification accounts for every intended, completed, unapplied, uncertain, and preserved effect. |
| PROD-WIQ-008 | No training or export authority is inferred. | The run creates only approved Compass graph content and performs no automatic export, dataset publication, or model-training submission. |
| PROD-WIQ-009 | Artifact building interprets before it asks the user to author structure. | Each artifact-producing Skill offers a useful Work IQ-grounded suggestion for content, fields, and relationships, and the user can confirm or revise it before writing. |
| PROD-WIQ-010 | Installation verifies writing without disposable deletion. | No probe is created; the approved configuration is written and verified first, and refusal or uncertainty stops later writes with accurate effect accounting. |
| PROD-WIQ-011 | Person email addresses are useful reviewed attributes. | A user can add a Person using an email address; Compass suggests the complete name when available, previews the normalized address, retains it after confirmation, and does not collect UPN. |
| PROD-WIQ-012 | OneDrive graph writes use reliable path addressing. | Each approved create or replace targets the displayed graph-root-relative path rather than a OneDrive item ID; graph-root resolution and Conversation identity remain unchanged. |

## Entry criteria

- Artifact-first shaping has produced a useful target graph and a reviewed set of reusable techniques.
- Requirements, specifications, and Skills have been revised from the demonstrated outcomes.
- An exact derived package set and hashes have replaced or explicitly reaffirmed the current package baseline.
- Import only that exact release-test set into an approved company-managed Cowork client.
- Select the intended production Compass graph root and confirm the purpose and work scope in Cowork.
- Review source results privately under company security guidance.
- Do not paste or describe identifying work content to Dexter. Report only privacy-minimized decisions, counts, capability observations, coverage status, interaction issues, and effect accounting.

## Journey

1. Run Installation Interview against the selected production root and approve Work IQ use only for the displayed purpose and scope.
2. Privately inspect whether Cowork used every relevant source type and continuation capability it exposed. Record only source-type names, approximate counts, continuation behavior, and gaps.
3. Review Compass's suggested foundational CSPs, Topics, People with normalized email addresses when known, links, and YAML. Correct or decline any unsupported identity, relationship, title, state, tag, or narrative.
4. Approve the exact proposal only when it reflects intended production content; otherwise continue review or cancel.
5. Run one representative Daily Scan and one Topic Interview on current work, preserving the same evidence and review controls.
6. Run Curator, then allow Governor validation and post-write verification through the accepted orchestration.
7. Independently inspect the resulting graph for the approved objects and effects. Record a privacy-minimized outcome without content excerpts.

## Stop conditions

- Cowork requests broader access than the displayed purpose or work scope.
- A Skill imposes an unexplained numeric retrieval cap, skips an exposed relevant source type, or fails to attempt exposed continuation.
- A Skill substitutes sample, fictional, fixture, or synthetic evidence for unavailable production evidence.
- A proposed Person, Topic, CSP, Conversation, relationship, status, attention state, success value, tag, review flag, or narrative is unsupported or not reviewable.
- A Skill makes the user translate ordinary work intent into schema fields instead of offering an editable interpretation, rejects a reviewed Person email as unimportant, treats it as UPN, or creates a disposable installation probe.
- A write begins without exact approval, becomes partial or unverifiable, or differs from the approved effects.
- A writer addresses a graph file by OneDrive item ID instead of its declared graph-root-relative path.
- Curator writes, Governor retrieves Work IQ or chooses meaning, or any component exports content for training without separate authority.
- The experience exposes identifying work content outside the approved managed surface.
- The run relies on undeclared manual correction or ad hoc Cowork guidance; stop and return the behavior to shaping rather than crediting the packaged Skills.

## Evidence record

Record only:

- exact package hashes;
- Cowork capability and source-type names observed;
- approximate candidate and accepted-object counts;
- whether continuation was available and attempted;
- complete, partial, or blocked coverage with reason categories;
- user decisions and interaction observations without work content;
- Governor outcomes and effect counts; and
- independent confirmation of durable effects.

## Exit criteria

The journey supports a production release-test conclusion only when all twelve claims have operator-reported evidence and durable effects are independently inspected. A separate product-owner decision is required to release or deploy Compass. Any conclusion remains bounded to the exact packages, date, approved scope, permissions, exposed Cowork capabilities, and observed graph state.
