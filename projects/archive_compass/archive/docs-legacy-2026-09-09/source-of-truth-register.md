# Compass Source-of-Truth Register

## Document control

- **Status:** living
- **Version:** 8.4
- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Last updated:** 2026-09-09

## Current chain

The living product-document chain is intentionally limited to four layers: Charter → PRD → Specifications → Test Plans. Supporting decisions, scenarios, results, confidence assessments, inventories, Skill source, and packages preserve authority, implementation, and evidence without becoming additional product-planning layers.

Compass uses one Specification artifact type. Each current Specification identifies the Skill or Skills to which it applies; terms such as cross-Skill, schema, and handoff describe subject or applicability rather than separate governance classes. Every product-behavior Scenario names at least one Skill. No-Skill Cowork or OneDrive capability checks are Experiments, with compatibility pointers retained where historical records linked to their former scenario paths.

## Current milestone

Compass entered **production release testing** on 2026-09-08 by accepted [product-owner decision](decisions/2026-09-08-declare-production-release-testing-milestone.md). Its active stage is now [artifact-first production shaping](decisions/2026-09-08-adopt-artifact-first-production-shaping.md): build a useful finished graph through flexible authorized Cowork conversation and manual correction, record successful techniques, then derive Skills from demonstrated outcomes. The exact production-content candidate set is an optional shaping tool and design input until replacement Skills are derived. Synthetic fixtures remain focused regression and destructive-boundary assets. No shaping outcome declares a production release or proves Skill repeatability.

| Role | Current source | Version | Status | Last updated | Notes or gaps |
| --- | --- | --- | --- | --- | --- |
| Charter | [Compass Vision and Scope Charter](charter/compass-vision-and-scope-charter.md) | 1.0 | accepted | 2026-08-28 | Governs direction; contains explicit confirmed and provisional statements. |
| PRD | [Compass Product Requirements Document](requirements/compass-product-requirements.md) | 0.9 | living requirements including production-content and native Work IQ outcomes | 2026-09-08 | Defines desired capabilities and acceptance signals; it does not itself specify implementation. |
| Specifications | [Specifications directory](specifications/); current [Graph Schema](specifications/compass-graph-schema-specification.md), [YAML and links rules](specifications/2026-09-04-compass-yaml-links-and-relationship-rules-review.md), and proposed [Recency and lifecycle review](specifications/recency-and-lifecycle-review-specification.md) | versioned by specification | mixed accepted and proposed | 2026-09-08 | Defines technical behavior and interfaces. Each specification states its own status and implementation authority. |
| Test Plans | [Test plans directory](test-plans/); current [artifact-first shaping plan](specifications/2026-09-08-artifact-first-production-shaping-plan.md), later [production-content release test](test-plans/2026-09-08-production-content-and-native-work-iq-test-plan.md), and [HPI narrative plan](test-plans/2026-09-08-hpi-topic-narrative-and-review-test-plan.md) | dated and version-bound | shaping active; controlled release test planned | 2026-09-08 | Shaping discovers target outcomes; controlled tests later evaluate whether exact Skills reproduce them. Completed test results remain separate immutable evidence. |

## Capability status

| Capability | Source state | Evidence state | Current disposition |
| --- | --- | --- | --- |
| Installation Interview | `0.7.0-production-test-candidate` packaged. | Production-content contract and deterministic package inspection passed; runtime unrun. | Begin production setup from direct answers and all relevant authorized Work IQ without sample substitution or arbitrary caps. |
| Daily Scan | `0.7.0-production-test-candidate` packaged. | Production-content contract and deterministic package inspection passed; runtime unrun. | Observe complete relevant retrieval attempts, continuation, coverage disclosure, review, and durable Conversation proposals. |
| Tracking Topic Interview | `0.7.0-production-test-candidate` packaged. | Production-content contract and deterministic package inspection passed; runtime unrun. | Observe purpose-bound Work IQ retrieval and exact narrative and metadata approval. |
| Curator | `0.6.0-production-test-candidate` packaged without evaluation fixtures. | Production-content contract and deterministic package inspection passed; runtime unrun. | Observe graph review with authorized Work IQ as non-authoritative context. |
| Graph Governor | `0.8.0-production-test-candidate` packaged without evaluation fixtures. | Current production schema-v2 modes unrun; read-only runtime evidence remains bounded to exact `0.1.0-experimental`. | Observe structural authority and effect verification without Work IQ retrieval or meaning judgment. |
| Compass Orchestration | `compass-work-memory-lifecycle` `0.7.0-production-test-candidate` source updated. | No orchestration runtime evidence for current version. | Treat as a shaping input; revise from demonstrated graph outcomes before the controlled repeatability gate. |

## Active gaps and conflicts

| Gap or conflict | Consequence | Next decision |
| --- | --- | --- |
| PRD requirements inherit mixed confirmed and provisional Charter states. | The synthesis cannot be treated as wholesale accepted requirements. | User may confirm or revise provisional requirements when they become decision-relevant. |
| Perspective Discovery `0.1.0-experimental` candidate review was too technical and interrogation-like. | Privacy-safe output did not establish comprehension and trust. | Preserve the `0.1.1-experimental` partial result; do not resolve until the full review interaction is observable. |
| Perspective Discovery `0.1.1-experimental` Adaptive Card controls became inaccessible. | The user could not reach required candidate navigation or skip controls, so review and handoff could not complete. | `0.1.2-experimental` progressive correction is authorized; inspect it and run PD-UI-001 once before considering resolution. |
| Connected storage and write contracts remain untested. | Read-only synthetic confidence cannot support persistence or repair claims. | Select a future bounded slice only after contracts and authority are accepted. |
| Prior Installation, Daily Scan, and Tracking Topic artifacts are not Dexter baselines. | Imported behavior and claims cannot be assumed current. | Keep them immutable; use only the registered candidate packages for future proposals. |
| The five candidate packages and Orchestration have no complete-candidate runtime evidence. | Static compatibility cannot establish interaction, application, persistence, conflict, or recovery behavior. | Use the accepted [experience-led rehearsal](test-plans/2026-09-02-compass-experience-led-rehearsal-plan.md); authorize execution separately. |
| Integrated browser access is blocked by organizational Conditional Access. | The laboratory assistant cannot directly automate Cowork import or interaction in that client context. | Product owner operates the authorized rehearsal in an approved managed client; record results without weakening policy. |
| `C:\Users\randt\OneDrive - Microsoft\SampleCompass` matches the fictional baseline and is the accepted synchronized rehearsal graph. | Approved fictional graph effects may synchronize externally within this exact folder. | Resume Installation Interview; stop on any scope expansion, real content request, or unexplained effect. |
| Installation `0.1.0` bootstrap preview was not practically reviewable in its rendered Adaptive Card. | The user could not reach Change; installation cancelled safely. | Observe the corrected `0.1.1-beta-candidate` naturally in the active rehearsal and batch any remaining interaction feedback. |
| Testing guidance overemphasized deterministic fixture details such as timezone. | Laboratory intervention interrupted useful product shaping without protecting a material boundary. | Apply the shaping-first standard and batch only recurring non-blocking themes for later instruction revision. |
| Schema-version-2 participant behavior has static package evidence only. | No claim is supported for runtime prompting, participant qualification, funneling, exclusions, or explicit Parking Lot writes. | Execute the planned disconnected scenario, then separately authorize the smallest Cowork interaction set. |
| Schema-version-1 migration is not specified. | Current schema-v2 Skills must not mutate an existing v1 graph. | Design, review, and test an explicit migration before personal-graph use. |
| Topic archival-success behavior has static evidence only. | Prompting, exact authority, invalid-case rejection, merge-source handling, and reactivation removal are not runtime-proven. | Execute `CTAS-V2-001` only after separate authorization. |
| Topic attention-state behavior has static evidence only. | Initial choice, change, cancellation, non-inference, invalid-case rejection, archival retention, and reactivation confirmation are not runtime-proven. | Execute `CTAS-V2-002` only after separate authorization. |
| Person UPN removal has static evidence only. | Source text and packages cannot prove runtime omission, retrieval minimization, rejection, preservation, or cleanup behavior. | Execute only the focused fictional checks after separate authorization; cleanup requires its own approval. |
| HPI Topic narrative and review metadata have static evidence only. | Correct fixture YAML and package bytes cannot prove interview quality, Curator output, Governor decisions, writes, or preservation at runtime. | Run `HPI-NARR-001` with the exact registered packages in an approved Cowork client. |
| Native Work IQ production behavior has static instruction evidence only. | Source and package inspection cannot prove which capabilities Cowork exposes, retrieval completeness, pagination, ranking, permissions, or durable effects. | During shaping, record privacy-minimized successful techniques and gaps; after Skill revision, run controlled `PROD-WIQ-001` through `PROD-WIQ-008`. |

## Change and evidence controls

- [Historical Graph Governor first-slice closure summary](test-results/2026-09-01-graph-governor-first-slice-closure-summary.md)

- [Experience-led rehearsal plan](test-plans/2026-09-02-compass-experience-led-rehearsal-plan.md)
- [Experience-led beta route decision](decisions/2026-09-02-adopt-experience-led-beta-route.md)
- [Cowork experience rehearsal kit](scenarios/compass-experience-led-rehearsal.md)
- [Superseded compact full-beta test strategy](test-plans/2026-09-02-compass-compact-full-beta-test-strategy.md)
- [Beta contract baseline acceptance](decisions/2026-09-02-accept-compass-beta-contract-baseline.md)
- [Slice B responsibility compatibility assessment](specifications/2026-09-02-slice-b-skill-responsibility-compatibility-assessment.md)
- [Compass lifecycle Orchestration acceptance](decisions/2026-09-02-propose-acceptance-of-compass-lifecycle-orchestration.md)
- [Slice D construction impact assessment](specifications/2026-09-02-slice-d-beta-candidate-construction-impact-assessment.md)
- [Full-beta candidate assembly plan](specifications/2026-09-02-compass-full-beta-candidate-assembly-plan.md)
- [Full-beta assembly impact assessment](specifications/2026-09-02-full-beta-candidate-assembly-impact-assessment.md)
- [Requirements traceability matrix](requirements/requirements-traceability-matrix.md)
- [Prior artifact register](inventory/prior-skill-artifact-register.md)
- [Perspective Discovery usability finding](findings/2026-09-01-perspective-discovery-candidate-review-is-too-technical.md)
- [Perspective Discovery Adaptive Card accessibility finding](findings/2026-09-01-perspective-discovery-adaptive-card-controls-are-inaccessible.md)
- [Perspective Discovery 0.1.1 cancelled connected-run result](test-results/2026-09-01-perspective-discovery-v0-1-1-pd-lean-001-cancelled.md)
- [Perspective Discovery conversational-review impact assessment](specifications/2026-09-01-perspective-discovery-conversational-review-impact-assessment.md)
- [Perspective Discovery 0.1.1 source and package inspection](test-results/2026-09-01-perspective-discovery-v0-1-1-source-and-package-inspection.md)
- [Graph Governor closure decision](decisions/2026-09-01-close-graph-governor-v0-1-0-experimental-test-slice.md)
- [Beta-candidate source and package inspection](test-results/2026-09-02-compass-beta-candidate-source-and-package-inspection.md)
- [Beta fixture construction validation](test-results/2026-09-02-compass-beta-graph-v1-construction-validation.md)
- [Gate 0 candidate compatibility](test-results/2026-09-02-compass-gate-0-candidate-compatibility.md)
- [Participant-management decision](decisions/2026-09-06-accept-participant-and-topic-management.md)
- [Participant-management impact assessment](specifications/2026-09-06-participant-management-impact-assessment.md)
- [Participant-management package inspection](test-results/2026-09-06-compass-0-4-0-participant-management-package-inspection.md)
- [Participant-management schema-v2 fixture validation](test-results/2026-09-06-compass-participant-management-v2-fixture-validation.md)
- [Topic archival-success decision](decisions/2026-09-06-record-topic-archival-success.md)
- [Topic archival-success impact assessment](specifications/2026-09-06-topic-archival-success-impact-assessment.md)
- [Topic archival-success package inspection](test-results/2026-09-06-compass-0-4-1-archival-success-package-inspection.md)
- [Topic archival-success fixture validation](test-results/2026-09-06-compass-topic-archival-success-v2-fixture-validation.md)
- [Topic attention-state decision](decisions/2026-09-06-add-topic-attention-state.md)
- [Topic attention-state impact assessment](specifications/2026-09-06-topic-attention-state-impact-assessment.md)
- [Topic attention-state package inspection](test-results/2026-09-06-compass-0-5-0-attention-state-package-inspection.md)
- [Topic attention-state fixture validation](test-results/2026-09-06-compass-topic-attention-state-v2-fixture-validation.md)
- [Person UPN removal decision](decisions/2026-09-06-stop-collecting-person-upn.md)
- [Person UPN removal impact assessment](specifications/2026-09-06-person-upn-removal-impact-assessment.md)
- [Person UPN removal test plan](test-plans/2026-09-06-person-upn-removal-test-plan.md)
- [Person data-minimization package inspection](test-results/2026-09-06-compass-0-6-0-person-data-minimization-package-inspection.md)
- [HPI narrative decision](decisions/2026-09-08-accept-hpi-topic-narrative-and-review-metadata.md)
- [HPI narrative test plan](test-plans/2026-09-08-hpi-topic-narrative-and-review-test-plan.md)
- [HPI narrative package set](inventory/compass-hpi-narrative-candidate-package-set.md)
- [HPI narrative static validation](test-results/2026-09-08-hpi-narrative-static-validation.md)
- [Fresh installation package-set validation](test-results/2026-09-08-fresh-installation-package-set-validation.md)
- [Production Work IQ decision](decisions/2026-09-08-use-production-content-and-native-work-iq-capability.md)
- [Production release-testing milestone](decisions/2026-09-08-declare-production-release-testing-milestone.md)
- [Artifact-first production shaping decision](decisions/2026-09-08-adopt-artifact-first-production-shaping.md)
- [Artifact-first production shaping plan](specifications/2026-09-08-artifact-first-production-shaping-plan.md)
- [Production graph shaping technique ledger](experiments/production-graph-shaping-technique-ledger.md)
- [Production-content test plan](test-plans/2026-09-08-production-content-and-native-work-iq-test-plan.md)
- [Production-content package set](inventory/compass-production-content-candidate-package-set.md)
- [Production-content package-set validation](test-results/2026-09-08-production-content-package-set-validation.md)

Completed test records are not revised when living intent changes. Material source changes require impact assessment against specifications, source, packages, scenarios, evidence, and confidence.