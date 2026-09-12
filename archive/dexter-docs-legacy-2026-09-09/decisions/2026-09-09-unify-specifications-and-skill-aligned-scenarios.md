# Decision: Unify specifications and Skill-aligned scenarios

- **Date:** 2026-09-09
- **Status:** accepted
- **Decider:** Dexter product owner
- **Applies to:** Dexter project governance, templates, and future project records

## Context

Dexter has described Skill specifications, shared contracts, schema specifications, and other behavioral records as if they were different artifact types. This adds administrative distinctions that do not improve the project instruction manual. The runtime solution is ultimately delivered through one or more Skills consumed by Cowork or another AI surface, so specifications and scenarios need clear Skill applicability without separate governance systems.

Some prior scenarios instead test a host surface, transport, package, or dependency without invoking a Skill. Assigning those checks to a Skill would misrepresent what was tested.

## Decision

1. Core Tenets belong in the Project Charter. They state durable principles governing product and development choices. Workspace instructions, Skills, and procedures may operationalize them but do not replace the Charter as their authority source.
2. Dexter recognizes one **Specification** artifact type. A Specification may describe behavior, interaction, schema, interfaces, handoffs, validation, or constraints without becoming a separately governed Skill, shared, schema, or orchestration specification type.
3. Every Specification identifies `Applies to Skills` with one or more exact Skill names, or `project-wide` while Skills are not yet identified. Before implementation, every implementable rule must resolve to one or more Skills.
4. A rule needed by multiple Skills remains in one Specification and lists all affected Skills. “Shared” describes applicability, not an artifact type.
5. Every Scenario identifies one or more exact Skills covered. A Scenario evaluates behavior delivered by those Skills, including their coordination when more than one is named.
6. A check that invokes no Skill and evaluates only a host surface, transport, package, dependency, or tool is an Experiment or static validation record, not a Scenario. It must not be assigned to a Skill merely to satisfy traceability.
7. Test Plans select complete journeys and focused Scenarios. Skills remain the runtime delivery artifacts; Specifications and Scenarios guide how Dexter builds and evaluates them.
8. Existing dated evidence remains unchanged. Living no-Skill scenario definitions may be reclassified incrementally when next used; until then, they are legacy records and do not establish the new pattern.

## Consequences

- The living chain remains Charter -> PRD -> Specifications -> Test Plans.
- Specification filenames may remain subject-oriented; applicability metadata replaces artifact-type prefixes and separate handling.
- Cross-Skill rules do not require a distinct “Shared Contract” lifecycle.
- Scenario-to-Skill traceability becomes direct and testable.
- Host-capability work remains truthful by using Experiment records when no Skill runs.
