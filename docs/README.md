# Dexter documentation

This area contains reusable project-lifecycle methodology, source-of-truth templates, laboratory inventory, plans, scenarios, evidence, confidence assessments, findings, and decisions.

## Source-of-truth lifecycle

Dexter projects maintain a connected chain:

> Project Charter → PRD → recorded MVP scope → Specifications → Test Plan → Test Results → Confidence Assessment

Charters, PRDs, MVP scopes, specifications, and test plans are living statements of current intent. Completed test results are immutable observations. Dated confidence assessments state only what linked evidence supports for an exact scope.

- [`methodology/`](methodology/): reusable lifecycle, living-document, impact, testing, and human-centered guidance.
- [`inventory/living-project-status.md`](inventory/living-project-status.md): Dexter-wide index of project source-of-truth registers.
- [`_templates/`](./_templates/): starting points for upstream sources of truth and downstream laboratory records.

## Record types

- `inventory/`: Skill and Orchestration ownership, versions, dependencies, and status.
- `test-plans/`: coordinated test scope across skills or releases.
- `scenarios/`: stable, reusable test cases with expected behavior.
- `experiments/`: hypotheses, variables, direct observations, and interpretations.
- `test-results/`: immutable records of individual executions.
- `confidence/`: dated, evidence-based readiness assessments for an exact version and scope.
- `findings/`: patterns, defects, risks, and improvement opportunities spanning runs.
- `decisions/`: accepted choices and rationale.
- `_templates/`: starting points for Charters, PRDs, MVP scopes, specifications, implementation plans, traceability, impact assessments, and laboratory records.

Use relative links to connect each accepted claim to its source, specification, scenario, tested artifact, result, confidence, finding, and decision. Do not revise an old result or assessment to match later behavior; revise living intent and add new dated evidence or reassessment records.
