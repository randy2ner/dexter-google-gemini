# Project source-of-truth lifecycle

## Document control

- **Status:** living
- **Version:** 1.0
- **Owner:** Project Dexter
- **Last updated:** 2026-09-01

## Purpose

Define the minimum connected sources of truth Dexter uses to understand a project, build its capabilities, and evaluate evidence without inventing requirements.

## Chain

| Source | Question answered | Required content |
| --- | --- | --- |
| Project Charter | Why does the project exist, and who has authority? | Purpose, boundaries, intended outcomes, stakeholders, authority, non-negotiable principles |
| PRD | What must the product or capability accomplish? | User problem, required capabilities, priorities, success measures, constraints, non-goals |
| Recorded MVP scope | What is the smallest useful learning or delivery step? | Assumptions, included and excluded behavior, success conditions, stopping point |
| Specification | Exactly how must the accepted scope behave? | Interfaces, behavior, interaction qualities, constraints, dependencies, acceptance criteria |
| Test Plan | How will accepted claims be evaluated proportionately? | Claims, risks, scenarios, evidence, entry and exit criteria, stopping rules |
| Test Results | What directly happened? | Immutable observations, exact subject identity, environment, deviations, evidence |
| Confidence Assessment | What conclusions does the evidence support? | Bounded claim, gaps, exclusions, dependency state, reassessment triggers |

## Authority and traceability

- A downstream document may refine an upstream source but may not silently contradict it.
- Every requirement must trace to the Charter, accepted user direction, or an accepted decision.
- Every specification rule must trace to a requirement or explicit constraint.
- Every scored test claim must trace to a requirement or specification acceptance criterion.
- Evidence cannot create a requirement by itself. A finding may motivate a living-document revision under user authority.
- A project maintains a source-of-truth register and a requirements traceability matrix.

## Proportional use

Not every project requires a large standalone document for every link. MVP scope may live in the PRD or an accepted decision. A small capability may use one concise specification. The register must identify where each responsibility is carried.

## Lifecycle

1. Establish the Charter.
2. Record product requirements and unresolved assumptions.
3. Select and record the smallest learning scope.
4. Specify that scope precisely enough to build and evaluate.
5. Design only the tests needed to inform the next decision.
6. Preserve direct results without rewriting history.
7. assess confidence and decide whether to close, revise, expand, or stop.

Passing a test does not automatically authorize the next lifecycle stage.