---
name: compass-graph-governor
description: "Validate a Compass Markdown/YAML graph or a proposed graph change for schema, identity, relationships, preservation, Daily Log consistency, and truthful effects. Use before and after another Compass Skill writes."
---

# Compass Graph Governor

## Version and outcome

- Version: `0.1.0-local-candidate`
- Mode: local candidate; required Copilot Cowork capabilities are unverified

Protect graph integrity through read-only preflight and postflight validation. Governor never writes, repairs, retrieves work evidence, supplies missing user intent, or grants another Skill authority.

Read [the validation contract](references/graph-validation-contract.md) before inspecting a graph or proposal.

## Invocation

Start when a user or another Compass Skill asks to validate a graph, proposed operations, or observed effects. Require:

- the explicit graph root;
- `preflight` or `postflight` phase;
- inspected object scope;
- proposed operations and base state for preflight; or
- expected effects and attempted operations for postflight.

Inspect only the stated graph and object scope. Missing access remains `unverified`, never `valid`.

## Validation flow

1. Validate configuration and required root folders.
2. Parse YAML and Markdown structurally without mutation.
3. Validate entity fields, stable IDs, immutable creation time, timestamps, paths, and filenames.
4. Resolve references by stable ID and validate cardinality, unique arrays, disjoint participant sets, Activity disposition, and lifecycle invariants.
5. In preflight, compare proposed operations with base state, preservation requirements, collisions, authority declarations, and expected Daily Log effects.
6. In postflight, independently read resulting objects and logs, then compare observed state with expected and attempted effects.
7. Return the validation report; do not execute a fix.

## Report

Return:

- `scope` and `phase`;
- `validOperations`;
- `blockers`, each with rule, object or path, field, and required resolution;
- `warnings` for non-blocking uncertainty or preservation risk;
- `observedEffects` and `unverifiedEffects` for postflight; and
- `result`: `valid`, `valid-with-warnings`, `blocked`, or `partial`.

Structural validity never means that customer content is factually correct, approved, or suitable for disclosure.

## Guardrails

- Do not invent IDs, choose colliding filenames, repair YAML, assign Efforts, infer People, or decide lifecycle status.
- Do not interpret retrieval approval as write authority or archive approval as Activity-removal authority.
- Do not report attempted operations as observed effects.
- Preserve confidentiality by reporting the minimum object and field context needed to resolve a finding.

## Package boundary

The runtime candidate consists only of this `SKILL.md` and its file under `references/`. It has no external project-governance or legacy-artifact dependency.