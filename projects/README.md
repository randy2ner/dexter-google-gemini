# Projects

Each directory under this location is an isolated Dexter laboratory project. Project records, source, test specimens, and evidence stay together so one effort can be shared, archived, or removed without changing Dexter's scaffolding.

This file is the canonical project-layout contract. Other Dexter guidance should link here rather than define a competing structure.

## Canonical layout

```text
projects/<project-name>/
|-- CHARTER.md
|-- PRD.md
|-- specifications/
|   `-- <behavior-or-contract>.md
|-- test-plans/
|   `-- <behavior-or-experience>.md
|-- skills/
|   `-- <skill-name>/
|       |-- SKILL.md
|       `-- references/                 # optional runtime references
|-- orchestrations/                     # when coordination is required
|   `-- <orchestration-name>/
|       |-- ORCHESTRATION.md
|       `-- CHANGELOG.md
|-- skill-exchange/                     # importable .skill files, when needed
`-- test-data/                          # when native fixtures are required
```

Every project requires `CHARTER.md`, `PRD.md`, at least one file under `specifications/`, at least one linked file under `test-plans/`, and source for each Skill it owns. Create the conditional directories only when the project needs them.

## Artifact responsibilities

- `CHARTER.md` preserves the project's vision, purpose, intended users, desired outcomes, scope, boundaries, authority, and the distinction between accepted and provisional direction.
- `PRD.md` is governed by the Charter and defines user problems, priorities, required capabilities, product requirements, acceptance signals, non-goals, constraints, and dependencies.
- `specifications/` contains one Markdown file per coherent behavior or contract. Each Specification identifies the PRD requirements and Skills it applies to and links to its Test Plans.
- `test-plans/` contains practical, reusable ways to evaluate specified behavior. Several Test Plans may reference one Specification, and one Test Plan may verify related behavior from several Specifications.
- `skills/` contains editable Skill source. Runtime references required by a Skill stay beside its `SKILL.md` under that Skill's directory.
- `orchestrations/` contains only real coordination across multiple Skills, tools, or people, including sequence, handoffs, and approval boundaries.
- `skill-exchange/` is a flat exchange area for importable `.skill` files, never editable Skill source. Use clear filenames to distinguish candidates or revisions; do not require lifecycle subdirectories.
- `test-data/` contains fixtures required in their native form. Ordinary observations remain in the relevant Test Plan.

## Sharing a Skill

Share the importable Skill package alongside the concise project documentation and reusable Test Plans needed to understand and evaluate it. The package itself contains only files required by the Skill host, normally root `SKILL.md` and any runtime `references/`. The accompanying material identifies:

- the governing Charter, PRD requirements, and Specifications;
- the Skill's responsibility, dependencies, authority, and known limitations;
- the Test Plans and observable confirmation criteria;
- the tested Skill host product and conditions that materially affected behavior; and
- how a user on another Skill host can identify that product, run focused capability probes, predict adaptation needs, and verify the experience.

## Boundary rules

- Dexter's root documentation defines the laboratory method and reusable templates.
- A project directory contains all subject-specific content.
- Do not place project-specific Skills, Orchestrations, results, or test artifacts in Dexter's root-level working directories.
- Promote material to Dexter's shared scaffolding only when it is intentionally generalized for reuse.
- Links within a project should remain project-relative whenever practical.
- Use lowercase kebab-case for project, Skill, Specification, Test Plan, and Orchestration directory or file names, except the canonical uppercase filenames shown above.
- Do not create separate decision, finding, confidence, impact, status, scenario, or test-result documents. Put product direction in the Charter or PRD, intended behavior in Specifications, and test definitions and observations in Test Plans.

## Graduation and portability

A project is complete only when its directory can stand apart from Dexter. Before graduation:

1. Confirm the directory contains its current Charter, PRD, Specifications, linked Test Plans, Skill source, any required Orchestration and local references, and distributable artifacts.
2. Check project Markdown, manifests, and instructions for required links or dependencies outside the project directory.
3. Replace required Dexter-root references with project-local content. References that are merely historical or informational must be clearly nonessential.
4. Check that credentials, personal data, tenant identifiers, and confidential evidence are absent.
5. Copy or move the directory to a neutral location and verify its links, package layout, instructions, and intended operation there.

Passing this check means Dexter can be removed without removing knowledge or capability the project requires.
