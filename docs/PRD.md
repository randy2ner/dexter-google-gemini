# Dexter Product Requirements Document

## Document control

- **Status:** active
- **Owner:** Dexter product owner
- **Created:** 2026-09-11
- **Last updated:** 2026-09-11
- **Governed by:** [`CHARTER.md`](CHARTER.md)

## Product purpose and user problems

Dexter helps a user transform an idea into a surface-testable Skill experience while preserving enough product knowledge and evidence to understand, share, resume, and continue improving it. It addresses two recurring failures: documentation becoming more burdensome than the Skill, and disconnected design work delaying learning from the actual Skill host.

## Prioritized outcomes

| ID | Outcome | Priority | Charter state |
| --- | --- | --- | --- |
| OUT-001 | Reach a coherent end-to-end Skill host experience quickly. | must | accepted |
| OUT-002 | Keep project intent, requirements, behavior, tests, and learning aligned and resumable. | must | accepted |
| OUT-003 | Let another user evaluate and adapt a shared Skill on a different host. | must | accepted |
| OUT-004 | Continue experiential training throughout the project's useful life. | must | accepted |
| OUT-005 | Graduate a self-contained project. | must | accepted |

## Product requirements and acceptance signals

| ID | Requirement | Priority | Acceptance signal | State |
| --- | --- | --- | --- | --- |
| PR-SCOPE-001 | Dexter distinguishes laboratory work from work in explicitly referenced projects. | must | It does not select a project from recency, editor state, or familiarity. | accepted |
| PR-DISC-001 | Dexter quickly interprets and brainstorms candidate outcomes and an intended experience. | must | Discovery begins with a useful synthesis and asks only material questions. | accepted |
| PR-DOC-001 | Every project uses a living Charter, PRD, separate Specifications, and linked Test Plans. | must | Current intent and evidence are understandable without a parallel tracking system. | accepted |
| PR-SPEC-001 | Each coherent behavior or contract has its own Specification. | must | Specifications identify applicable requirements, Skills, behavior, and Test Plans. | accepted |
| PR-TEST-001 | Test Plans provide repeatable situations, practical checks, and observable confirmations without requiring identical model responses. | must | A user can run the plan and make a bounded assessment on the named host. | accepted |
| PR-HOST-001 | Required Skill host capabilities are probed before design relies on them. | must | Unknown capabilities remain explicit and focused probes record observed conditions. | accepted |
| PR-BUILD-001 | Dexter builds the simplest coherent end-to-end Skill candidate and begins representative host testing early. | must | A reviewable package transitions into the host experience when prerequisites allow. | accepted |
| PR-TRAIN-001 | Representative use drives continuing coordinated revision. | must | Affected project knowledge, source, Orchestrations, packages, and tests remain aligned over time. | accepted |
| PR-PACK-001 | A Skill is shared with concise documentation, reusable Test Plans, and a host profile. | must | Another user can identify a different host, predict likely adaptation needs, and verify behavior. | accepted |
| PR-AUTH-001 | The user controls direction and consequential authority and remains oriented to Dexter's actions. | must | Dexter explains durable captures and obtains specific authority for connected or difficult-to-reverse effects. | accepted |
| PR-PORT-001 | Projects remain self-contained and portable. | must | A graduated project has no required Dexter-root dependency. | accepted |

## Required capabilities

| Capability | Why it is needed | Skill host dependency | State |
| --- | --- | --- | --- |
| Repository guidance | Establish one consistent layout and lifecycle | Workspace instruction support | available |
| Outcome interview | Complete the Discovery gate conversationally | Conversation and repository access | implemented; experiential retest needed |
| Capability probe | Establish required host operations | User access to the target surface | implemented; host-specific |
| Mediated experience | Train through a representative journey | User can operate and report the target surface | implemented; experiential retest needed |
| Package exchange | Preserve exact testable specimens | Skill host import mechanism | host-specific |

## Non-goals

- Deterministic control of probabilistic model responses.
- A separate feature ledger, change-control system, traceability matrix, or result-document taxonomy.
- Assuming compatibility across untested Skill hosts.
- Making project or product decisions on the user's behalf.

## Constraints and dependencies

- VS Code loads `.github/copilot-instructions.md` and discovers Dexter's on-demand Skills.
- Cowork, Scout, and other hosts may expose different tools, context, permissions, and interaction controls.
- The user may need to operate a target AI surface that Dexter cannot access directly.

## Specification index

| Specification | Requirements covered | State |
| --- | --- | --- |
| [`specifications/project-development-lifecycle.md`](specifications/project-development-lifecycle.md) | PR-SCOPE-001, PR-DISC-001, PR-DOC-001, PR-SPEC-001, PR-TEST-001, PR-HOST-001, PR-BUILD-001, PR-TRAIN-001, PR-AUTH-001 | implemented; experiential test pending |
| [`specifications/portable-skill-packaging.md`](specifications/portable-skill-packaging.md) | PR-TEST-001, PR-HOST-001, PR-PACK-001, PR-PORT-001 | implemented; static validation passed, portability experience pending |

## Open questions

- Does the revised method reach host testing with less correction and administrative burden in the next project?
- Which host differences most often require adaptation of shared Skills or their test patterns?

## Revision history

| Date | Change and reason |
| --- | --- |
| 2026-09-11 | Created from the accepted Charter direction and the revised Dexter instruction architecture. |

## Authority boundary

This PRD defines desired Dexter outcomes and requirements. It does not authorize project implementation, connected access, external effects, publication, or release beyond a user's request.