# Decision: Authorize ODT-002 scenario creation

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [ODT-001 partial result](../test-results/2026-08-31-odt-001-isolated-folder-enumeration.md)

## Context

ODT-001 produced partial native OneDrive picker evidence through a procedure deviation. Cowork returned all six expected basenames and the isolated fixture remained byte-identical, but the response omitted directory components and did not independently demonstrate file readability. The user then explicitly authorized creation of an ODT-002 native-picker hierarchy and readability scenario.

## Decision

Authorize creation and repository registration of [ODT-002](../scenarios/onedrive-transport/odt-002-native-picker-hierarchy-and-readability.md).

This authorization permits documentation only. It does not authorize executing ODT-002, selecting the OneDrive object again, invoking Cowork, uploading or invoking Graph Governor, accessing another folder, changing permissions, modifying files, retrieving Microsoft 365 evidence, or advancing Graph Governor's lifecycle.

ODT-002 must use the same isolated fictional baseline and must distinguish API-exposed relative paths from paths inferred from filenames or file contents. Readability probes must be minimal, deterministic, fictional, and read-only.

## Alternatives considered

- **Treat the ODT-001 basename list as hierarchy evidence:** Rejected because no directory component was returned.
- **Proceed directly to Graph Governor:** Rejected because hierarchy-preserving graph input remains unestablished.
- **Use a broader OneDrive parent:** Rejected because it would expose unrelated mutation fixtures and weaken isolation.
- **Authorize scenario execution implicitly:** Rejected because scenario design review and runtime authority are separate lifecycle gates.

## Consequences

- ODT-002 can be reviewed as an exact reproducible proposal before connected execution.
- ODT-001 remains an immutable partial result rather than being retried or rewritten.
- No new runtime evidence exists until ODT-002 receives separate execution authorization and is run.

## Follow-up

- User / product owner: review ODT-002 and explicitly authorize, revise, or defer its execution.
- Project Dexter: do not provide the folder to Cowork under ODT-002 until execution is separately authorized.