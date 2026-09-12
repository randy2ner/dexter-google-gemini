# Project source-of-truth lifecycle

## Document control

- **Status:** living
- **Version:** 3.0
- **Owner:** Project Dexter
- **Last updated:** 2026-09-09

## Purpose

Define the two living documents Dexter uses to understand, build, and test a project without creating a documentation system around the work.

## Project record

Each project maintains exactly two living governance documents:

| Document | Required content |
| --- | --- |
| Specification | Purpose, user outcomes, scope, authority, requirements, applicable Skills and Orchestrations, required behavior, dependencies, accepted decisions, implementation status, and success criteria |
| Test Plan | Test cases mapped to Specification criteria, test method and environment, execution status, dated observations, defects or limitations, and the current success assessment |

The Specification is the complete current description of what the project is and must do. The Test Plan is the complete current description of how that Specification is tested and what the latest testing established. Update the pair directly as the project changes.

Do not create separate Charters, PRDs, Scenarios, decisions, findings, confidence assessments, traceability matrices, status ledgers, or test-result documents for new work. Put information needed to understand or govern the project in the Specification. Put test design, execution evidence, and conclusions in the Test Plan.

Source files, packages, fixtures, and generated artifacts remain where the implementation needs them. A separate attachment is justified only when its native format or size cannot be usefully contained in one of the two documents; link it from the owning section and do not introduce another governance category.

## Authority and traceability

- The user's accepted direction controls the Specification. Record unresolved choices without inventing an answer.
- Give each testable requirement or success criterion a stable ID only when the Test Plan needs to reference it.
- Every implementable behavior identifies the Skills or Orchestrations that carry it into the target AI surface.
- Every Test Plan case identifies the Specification criterion it tests.
- Test observations may prompt a Specification change but do not silently redefine intended behavior.
- Record consequential authority, privacy, identity, durable-effect, and release boundaries in the Specification beside the behavior they constrain.

## Proportional use

Keep both documents concise. Use tables only when they make requirements or test status easier to scan. Avoid repeating the same statement in multiple sections, and remove obsolete detail when its historical value does not affect present behavior, authority, maintenance, or confidence.

## Lifecycle

1. Create or update the project Specification from the user's direction, asking only questions that resolve material ambiguity or authority.
2. Add or update the corresponding Test Plan cases for the Specification's success criteria.
3. Build and package the smallest coherent candidate.
4. Execute the relevant Test Plan cases and record dated observations and limitations in that same Test Plan.
5. Stop immediately only for material authority, privacy, identity, history, recovery, or effect-truth risk; otherwise complete the bounded test.
6. Revise the Specification and implementation from what was learned, then rerun affected Test Plan cases.
7. Before completion, verify that the project directory contains its two living documents, source, dependencies, and usable artifacts and can operate after removal from Dexter.

Documentation completion does not prove behavior. Only recorded execution of the Test Plan provides evidence that the Specification succeeds.