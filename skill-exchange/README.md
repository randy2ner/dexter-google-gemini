# Skill Exchange

This directory provides the reusable exchange structure and a shared handoff area for intentionally promoted artifacts. Project-specific artifacts belong in `projects/<project>/skill-exchange/`, with editable source in that project's `skills/` directory.

The guidance below can be copied and adapted for a project-local exchange. Store only testable package copies in an exchange; never treat it as editable Skill source.

## Folders

- `incoming/`: received artifacts awaiting inspection or triage.
- `ready-for-test/`: reviewed artifacts ready to import into Cowork.
- `tested/`: exact artifacts used in completed test runs.
- `archive/`: obsolete or superseded artifacts retained for traceability.

## Handoff checklist

Before moving an artifact to `ready-for-test/`:

- Give it an unambiguous skill name and version.
- Preserve the package layout expected by Cowork.
- Confirm it contains no credentials or sensitive production data.
- Identify at least one scenario in the owning project's `docs/scenarios/` directory, or in root `docs/scenarios/` when the scenario is intentionally shared.
- Do not overwrite a previously tested version.

After testing, move the exact artifact to `tested/` and create a dated record in the owning project's `docs/test-results/` directory. For an intentionally shared root artifact, use root `docs/test-results/`. If the import itself fails, record that as a test result rather than modifying the handed-off copy in place.
