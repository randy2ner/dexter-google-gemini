# Compass Customer Activity Interpretation Test Plan

## Metadata

- **Owner:** User / product owner
- **Specifications:** [Customer Activity Interpretation](../specifications/customer-activity-interpretation.md); [Knowledge Graph](../specifications/knowledge-graph.md)
- **Candidates:** `compass-installation-interview` and `compass-activity-scan` `0.1.0-local-candidate`
- **Skill host product:** Copilot Cowork
- **Status:** active
- **Last updated:** 2026-09-12

## Success decision

This plan determines whether Compass can turn mixed work evidence into useful customer-only Activities without mirroring source containers, inventing customer relevance, or treating prepared transparency as authorized disclosure. Success requires coherent grouping, grounded factual content, useful audience adaptation, and honest handling of ambiguity.

## Scope and environment

- **In scope:** Customer relevance, internal customer-work inclusion, unrelated-work exclusion, cross-source grouping, source splitting, factual grounding, Effort placement, provenance minimization, and account manager, customer, and leadership framing.
- **Out of scope:** Live customer data, connected disclosure, production graph writes, exhaustive communication policy, and deterministic model wording.
- **AI surface:** Copilot Cowork.
- **Material host conditions:** Skill loading, access to explicitly supplied synthetic evidence, multi-item interpretation, graph context use, and reviewable output.
- **Privacy:** Use fictional customers, people, contracts, and evidence. Retain no real work content or tenant identifiers.

## Host compatibility profile

- **Required host behavior:** Load the Skill, consider several supplied evidence items together, distinguish source facts from interpretation, use existing Effort context, present editable Activities, and tailor a selected Activity for a named audience without sending it.
- **Observed conditions:** Not yet probed on Copilot Cowork.
- **Another host:** Identify its product, run the focused capability checks below, compare observed differences, and record a compatibility or adaptation hypothesis before the complete journey.

## Complete journey

| Stage | Skill or component | User decision | Observable effect or no-write outcome |
| --- | --- | --- | --- |
| Supply | Installation Interview | Provide fictional mixed customer and non-customer evidence plus existing Effort context. | The candidate acknowledges the bounded synthetic input without claiming connected retrieval. |
| Interpret | Customer Activity interpretation | Review the proposed customer-work Activities. | Related evidence is grouped by coherent work, distinct work is separated, and unrelated internal work is excluded. |
| Refine | Installation Interview | Correct one Activity boundary or Effort placement. | The candidate preserves the correction and updates only the affected interpretation. |
| Communicate | Communication behavior | Choose account manager, customer, or leadership as audience. | A reviewable audience-appropriate account preserves facts and withholds inappropriate detail; nothing is disclosed. |
| Verify | Knowledge Graph | Inspect proposed or disconnected fixture output. | Activity identity, People, Effort or Parking Lot disposition, factual core, and minimized provenance satisfy both Specifications. |

This is a shaping guide, not an exact script. Prompts, situations, checks, and confirmation criteria should be repeatable; wording, sequence, and model responses may vary.

## Test cases

| ID | Specification behavior | Prompt or situation | Practical check and observable confirmation | Status | Latest observation |
| --- | --- | --- | --- | --- | --- |
| ACT-CUST-001 | `ACT-001`, `ACT-002`, `ACT-004` | Supply a customer escalation, a certification study note, and general team administration. | Only the escalation becomes an Activity, and it states the customer connection and significance without copying the source. | not run | None |
| ACT-INTERNAL-001 | `ACT-002` | Supply internal analysis and coordination that directly prepare a recommendation for a named fictional customer. | The work becomes an Activity because its material customer connection is explicit, even though no customer participated directly. | not run | None |
| ACT-GROUP-001 | `ACT-003`, `ACT-007`; `GRAPH-008`, `GRAPH-009`, `GRAPH-012` | Supply an email, meeting-chat excerpt, and direct user note about one customer decision. | One coherent Activity uses independent Compass identity and minimized provenance from all supporting inputs. | not run | None |
| ACT-SPLIT-001 | `ACT-003`, `ACT-007`; `GRAPH-009` | Supply one long fictional thread containing a resolved access issue and a separate future architecture commitment. | Two Activities are proposed because the customer work is distinct despite one source container. | not run | None |
| ACT-GROUND-001 | `ACT-004` through `ACT-006` | Omit the outcome and owner from otherwise relevant evidence. | The candidate captures supported facts and leaves the missing outcome and owner absent or uncertain rather than inventing them. | not run | None |
| ACT-AMBIG-001 | `ACT-008` | Supply evidence that could continue an existing Activity or represent a new customer issue. | The candidate asks one focused boundary question or leaves the interpretation unresolved; it does not merge confidently. | not run | None |
| ACT-AUDIENCE-001 | `ACT-009`, `ACT-010` | Prepare the same fictional Activity for an account manager, customer stakeholder, and leadership. | Each version preserves the factual core, changes emphasis appropriately, excludes internal-only detail from the customer version, remains reviewable, and is not sent. | not run | None |

## Focused host capability checks

| Capability | Harmless probe | Confirmation | Status |
| --- | --- | --- | --- |
| Multi-source interpretation | Provide three short synthetic items about one customer development. | Cowork can consider them together and return one coherent Activity without connected access. | not run |
| One-source splitting | Provide one synthetic thread containing two distinct customer developments. | Cowork can return two Activities with separate factual cores. | not run |
| Existing-context use | Provide a synthetic Effort and an Activity candidate. | Cowork can place the Activity using the Effort's meaning rather than keyword similarity alone. | not run |
| Audience adaptation | Request three audience versions without a send action. | Cowork returns reviewable text and causes no external effect. | not run |

## Material stop conditions

- Real work data, customer identity, tenant identifier, or confidential content enters the disconnected test.
- Compass invents customer relevance, impact, commitment, decision, outcome, or identity.
- Non-customer work is retained as an Activity.
- Audience adaptation exposes internal-only or unrelated context to the customer version.
- Prepared content is sent, published, or otherwise disclosed without explicit authority.
- Partial evidence coverage is reported as complete.

## Execution log

No execution recorded.

## Current success assessment

- **Assessment:** Not established.
- **Supported claims:** None; this plan records intended checks only.
- **Unresolved claims:** `ACT-001` through `ACT-010` and affected graph behavior have no runtime evidence.
- **Next test or revision:** Run the synthetic complete journey before any connected Work IQ or OneDrive test.