# Contributing

## Choose the correct boundary

- Put project-specific work under `projects/<project-name>/`.
- Keep its documentation, source, test artifacts, and evidence within that directory.
- Use root-level collections only for reusable Dexter templates or material intentionally promoted for use by multiple projects.
- Generalize and review content before promoting it; do not merely copy project assumptions into the scaffolding.

## Add or update a skill

1. Work in the owning project's `skills/<skill-name>/` directory and keep its `SKILL.md` current.
2. Add or update the project's inventory; document dependencies and consumers.
3. Use a clear version in the skill metadata or changelog.
4. Add an importable copy to the project's `skill-exchange/ready-for-test/` without overwriting a prior version.
5. In the change description, identify affected Orchestrations, intended scenarios, and notable changes.

## Add or update an Orchestration

1. Work in the owning project's `orchestrations/<orchestration-name>/` directory and use the root template as a starting point.
2. Add or update the project's inventory.
3. Link every Skill dependency and state compatible versions or constraints.
4. Identify scenarios that validate handoffs, routing, approvals, and failure behavior.
5. Reassess impacted confidence records when a dependency changes.

## Add a scenario

1. Copy the root `docs/_templates/scenario-template.md` into the owning project's `docs/scenarios/<scenario-name>.md`.
2. Make prerequisites, inputs, steps, and expected behavior reproducible.
3. Avoid real secrets and sensitive data; use clearly marked synthetic values.

## Record a test run

1. Copy the root `docs/_templates/test-result-template.md` into the owning project's `docs/test-results/YYYY-MM-DD-<skill>-<scenario>-<environment>.md`.
2. Record the exact skill version, Cowork environment/version when visible, scenario revision, and result.
3. Separate direct observations from interpretation.
4. Link follow-up findings or decisions using repository-relative links.

## Assess confidence

1. Start from the root `docs/_templates/confidence-assessment-template.md` and save the assessment in the owning project's `docs/confidence/` directory.
2. Scope the assessment to an exact subject version, environment, and date.
3. Link each supported claim to direct test evidence and name all evidence gaps.
4. Add a new assessment after material changes; never overwrite the historical state.

## Review expectations

- Confirm the artifact can be imported before marking it ready.
- Do not claim a result that was not observed.
- Preserve failed runs; they are useful evidence.
- Treat dependency changes as a reason to identify and rerun affected scenarios.
- Do not describe confidence as validated without linked passing evidence for the stated scope.
- Redact secrets, personal data, tenant identifiers, and confidential content.
- Prefer small changes that update related documentation together.
