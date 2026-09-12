# Contributing

## Choose the correct boundary

- Follow the canonical project layout in [`projects/README.md`](projects/README.md).
- Put project-specific work under `projects/<project-name>/`.
- Keep its documentation, source, test artifacts, and evidence within that directory.
- Put Dexter's own on-demand Skills under `.github/skills/`.
- Do not promote a project Skill into a universal root collection. If a reusable Skill becomes its own product, give it an independent project boundary.

## Add or update a skill

1. Work in the owning project's `skills/<skill-name>/` directory and keep its `SKILL.md` current.
2. Update the relevant Specifications with its responsibility, dependencies, host needs, authority, and implementation status; update the PRD when outcomes or requirements change.
3. Add an importable `.skill` file directly to the project's `skill-exchange/` without overwriting a prior specimen.
4. Update every affected Test Plan and begin the representative Skill host experience when prerequisites allow.

## Add or update an Orchestration

1. Work in the owning project's `orchestrations/<orchestration-name>/` directory and use the root template as a starting point.
2. Record sequence, dependencies, handoffs, approvals, and failure behavior in the relevant Specifications and Orchestration.
3. Add or update linked Test Plans for routing, handoffs, approvals, and failure behavior.

## Add a test case

1. Add one row or section to the relevant file under the owning project's `test-plans/` directory.
2. Link every Specification behavior it verifies and make prompts or situations, checks, and observable confirmation criteria repeatable.
3. Avoid real secrets and sensitive data; use clearly marked synthetic values where production content is unnecessary.

## Record a test run

1. Append a dated execution entry to the relevant Test Plan.
2. Record the candidate, Skill host product, materially relevant conditions, exercised case IDs, direct or operator-reported observations, independent effect checks, and limitations.
3. Update case statuses and the current success assessment without rewriting prior observations.

## Record a decision or defect

1. Put product direction and rationale in the Charter or PRD and intended behavioral changes in the relevant Specifications.
2. Put observed defects, limitations, and their test disposition in the relevant Test Plans.
3. Create no separate decision, finding, confidence, impact, status, or result document.

## Review expectations

- Confirm the artifact can be imported before marking it ready.
- Do not claim a result that was not observed.
- Preserve failed runs as dated Test Plan observations.
- Treat meaningful product, dependency, host, or experience changes as a reason to identify and rerun affected cases.
- Do not describe success without passing observations for the exact stated scope.
- Redact secrets, personal data, tenant identifiers, and confidential content.
- Keep affected Charter, PRD, Specifications, Test Plans, Skill source, Orchestrations, and packages aligned.
