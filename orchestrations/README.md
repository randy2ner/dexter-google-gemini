# Orchestrations

This directory provides reusable Orchestration scaffolding and holds patterns intentionally promoted for use across multiple projects. Project-specific Orchestration definitions belong in `projects/<project>/orchestrations/`.

Orchestrations describe workflows that coordinate multiple Skills, supporting tools, and human approvals. Keep each Orchestration in a lowercase kebab-case directory and copy [`_template/`](_template/) into the owning project as a starting point. Do not promote a project definition to this root collection until it has been deliberately generalized and reviewed for reuse.

An Orchestration record should make change impact visible by documenting:

- participating Skills and relevant compatibility conditions;
- sequence, routing, and handoff conditions;
- shared data and outputs;
- human approval boundaries;
- failure and fallback behavior;
- linked Test Plan cases required to confirm the coordinated behavior.

Do not copy Skill source into an Orchestration. Link to the participating project Skills and governing Specifications.

## Creation threshold

Create or update a project Orchestration when an authorized project slice includes coordinated behavior across two or more Skills, tools, or human actors and at least one of these conditions applies:

- ordered execution across participants;
- a data or artifact handoff;
- routing or conditional behavior; or
- a shared approval, failure, or recovery boundary.

Do not create an Orchestration merely because subjects share dependencies, belong to the same project, or might interact later. Start with the smallest real coordination boundary and expand the definition only as accepted scope and evidence make additional workflow behavior necessary.

Creating a draft records an already-authorized workflow slice. It does not authorize Skill implementation, packaging, connected access, execution, deployment, or release.
