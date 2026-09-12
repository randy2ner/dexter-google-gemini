# Confidence Assessments

Confidence in Dexter is an evidence-based readiness statement, not a feeling or permanent score. Assessments are snapshots that apply only to a named version, scope, environment, and date.

Create a standalone assessment only when a release, promotion, closure, or explicit readiness decision needs one. Routine beta cycles may state bounded conclusions directly in the consolidated result. When needed, use [`confidence-assessment-template.md`](../_templates/confidence-assessment-template.md) and name the assessment `YYYY-MM-DD-<skill-or-orchestration>-<version>.md`.

## Rules

- Link every claim to test results or an explicitly identified evidence gap.
- Keep scenario coverage separate from outcome quality.
- State environment and version boundaries.
- Lower or withdraw confidence when a dependency changes until affected scenarios are rerun.
- Add a new dated assessment instead of rewriting historical confidence.
