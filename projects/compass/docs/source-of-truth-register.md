# Compass Source-of-Truth Register

## Document control

- **Status:** living
- **Version:** 3.3
- **Owner:** User / product owner
- **Prepared with:** Project Dexter
- **Last updated:** 2026-09-04

## Current chain

| Role | Current source | Version | Status | Last updated | Notes or gaps |
| --- | --- | --- | --- | --- | --- |
| Charter | [Compass Vision and Scope Charter](charter/compass-vision-and-scope-charter.md) | 1.0 | accepted | 2026-08-28 | Governs direction; contains explicit confirmed and provisional statements. |
| PRD | [Compass Product Requirements Document](requirements/compass-product-requirements.md) | 0.1 | living synthesis; not separately accepted | 2026-09-01 | Preserves Charter authority classifications; provisional requirements remain provisional. |
| MVP scope | [Compass MVP Scope](mvp/compass-mvp-scope.md) | 1.0 | closed first slice | 2026-09-01 | Graph Governor read-only synthetic scope only. |
| Shared contracts | [Compass Shared Contracts Specification](specifications/compass-shared-contracts-specification.md) | 0.3-beta-baseline | accepted | 2026-09-02 | Governs common identity, authority, handoff, validation, Daily Log, outcome, and disposable-beta recovery rules; production transaction design remains deferred. |
| Graph schema | [Compass Graph Schema Specification](specifications/compass-graph-schema-specification.md) | 0.3-beta-baseline | accepted | 2026-09-02 | Governs schema version 1 common objects, configuration, relationships, and Daily Logs; item evidence, last activity, and transaction schemas remain deferred. |
| Skill responsibility set | [Slice B compatibility assessment](specifications/2026-09-02-slice-b-skill-responsibility-compatibility-assessment.md) | accepted set | accepted | 2026-09-02 | Installation, Daily Scan, Tracking Topic Interview, Curator, and Graph Governor boundaries govern Slice C. |
| Graph Governor specification | [Graph Governor Skill Specification](specifications/graph-governor-skill-specification.md) | 0.2-beta-responsibility | accepted responsibility | 2026-09-02 | Preserves bounded read-only evidence separately; added write-validation and synthetic recovery responsibilities remain untested. |
| Perspective Discovery specification | [Installation Interview Perspective Discovery Specification](specifications/installation-interview-perspective-discovery-skill-specification.md) | 1.1 | accepted revision | 2026-09-01 | Progressive three-choice review and disclosed UTC fallback authorized for `0.1.2-experimental`. |
| Test strategy and plans | [Clean first-run session](scenarios/compass-dogfood-clean-first-run.md); [protected-source support impact](specifications/2026-09-04-protected-source-support-impact-assessment.md); [package set](inventory/compass-0.3.3-dogfood-candidate-package-set.md) | 0.3.3 and dated | Protected-source candidate packaged; connected retest pending | 2026-09-04 | Begin with `Help me install Compass`, then use the selected protected Loop page as foundational evidence inside the signed-in Cowork context. |
| Evaluation standard | [Shaping-first vibe-coding decision](decisions/2026-09-04-adopt-shaping-first-vibe-coding-standard.md) | 1.0 | accepted | 2026-09-04 | Representative experience and user correction govern low-consequence variation; only material trust, privacy, identity, history, effect, and recovery failures block progress. |
| Beta candidate assembly | [Full-beta candidate assembly plan](specifications/2026-09-02-compass-full-beta-candidate-assembly-plan.md); [Slice D construction plan](specifications/2026-09-02-slice-d-beta-candidate-construction-plan.md); [Gate 0 compatibility result](test-results/2026-09-02-compass-gate-0-candidate-compatibility.md) | 1.0 | Gate 0 disconnected construction complete | 2026-09-02 | Five exact inspected packages, Orchestration, profiles, and restorable fictional fixture registered; rehearsal execution and development beta remain separately authorized steps. |
| Test results | [Test results directory](test-results/) | dated evidence | Gate 0 complete; prior Graph Governor slice complete; Installation experience in progress; Perspective Discovery partial | 2026-09-04 | Completed results remain immutable; in-progress observations are not confidence claims. |
| Confidence | [Graph Governor confidence assessment](confidence/2026-09-01-graph-governor-v0-1-0-experimental.md) | 1.0 | complete for exact bounded scope | 2026-09-01 | No Perspective Discovery confidence assessment. |

## Capability status

| Capability | Source state | Evidence state | Current disposition |
| --- | --- | --- | --- |
| Installation Interview | Protected-source correction `0.2.3-dogfood-candidate` packaged; prior packages preserved. | First `0.2.1` run blocked after protected Loop input; `0.2.2` avoidance response rejected; `0.2.3` runtime untested. | Run one protected-Loop first-run retest; classification alone must not block, and actual output capability is probed before managed structure. |
| Daily Scan | `0.2.0-dogfood-candidate` source/package inspected; `0.1.0-beta-candidate` package and evidence preserved. | Connected behavior implemented but not executed; prior connected attempt remains honestly blocked for `0.1.0`. | Upload the exact dogfood set and run one bounded selected-day experience. |
| Tracking Topic Interview | Source/package `0.1.0-beta-candidate` inspected. | User-approved alignment added `trackingTopicId: topic-validation-work` only to the email Conversation; external inspection confirmed the forward relationship and preservation of the unaligned Teams Conversation. | Continue to Curator review without manufacturing another alignment. |
| Daily Scan | Source/package `0.1.0-beta-candidate` inspected; prior package remains immutable input. | Static Gate 0 evidence only; retrieval and runtime untested. | Include in the experience-led rehearsal with fixed fictional input. |
| Tracking Topic Interview | Source/package `0.1.0-beta-candidate` inspected; prior package remains immutable input. | Static Gate 0 evidence only; runtime untested. | Include in the experience-led rehearsal. |
| Curator | Source/package `0.1.0-beta-candidate` inspected. | Static Gate 0 evidence only; runtime untested. | Include in the experience-led rehearsal. |
| Graph Governor | Source/package `0.2.0-beta-candidate` inspected; prior tested specimen preserved. | Candidate modes untested; read-only evidence remains bounded to exact `0.1.0-experimental`. | Include in the rehearsal without transferring prior confidence. |
| Compass Orchestration | Accepted `compass-work-memory-lifecycle` `0.1-beta-candidate` definition is statically compatible with the five package set. | No orchestration runtime evidence. | Observe continuity and handoffs within the rehearsal. |

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

## Change and evidence controls

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

Completed test records are not revised when living intent changes. Material source changes require impact assessment against specifications, source, packages, scenarios, evidence, and confidence.