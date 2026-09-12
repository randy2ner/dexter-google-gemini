# Test result: Compass 0.6.0 Person data-minimization package inspection

## Metadata

- **Date:** 2026-09-06
- **Status:** complete static package and source inspection
- **Owner:** Project Dexter laboratory assistant
- **Package set:** [Compass 0.6.0 Person data-minimization candidates](../inventory/compass-0.6.0-person-data-minimization-candidate-package-set.md)
- **Test plan:** [Person UPN removal test plan](../test-plans/2026-09-06-person-upn-removal-test-plan.md)

## Direct observations

1. Current schema-version-2 Person YAML examples and field tables do not define `userPrincipalName`.
2. No fixture under `projects/compass/test-data/` contains `userPrincipalName`.
3. Installation Interview, Daily Scan, and Tracking Topic Interview source and package-local behavior contracts prohibit requesting, inferring, retrieving UPN for retention, adding it, or updating it. They require pre-existing values to remain unmanaged and preserved unless removal receives separate authority.
4. Graph Governor source and its current beta contract reject proposed schema-version-2 effects that introduce or update `userPrincipalName` while preserving a pre-existing value outside the requested effect.
5. The Graph Governor `0.1.0-experimental` read-only contract still describes optional UPN for historical schema-version-1 scans. Current Graph Governor source limits that reference to explicitly requested historical schema-version-1 fixture scans; the prior contract was not rewritten.
6. Installation Interview is 7,989 bytes with SHA-256 `28d3078a0d78574e3c002d0a39c5f5b0e47a5c1e5beeb1ff73e5f66a5d054091`.
7. Daily Scan is 5,357 bytes with SHA-256 `1853e3c4abf0bb44b8c057da816cc5aa6d60f1cc0f0c8b233d0b819d20797aed`.
8. Tracking Topic Interview is 5,745 bytes with SHA-256 `a5aa03d60efdd701c33ae6114dba61e92ceac448f8bb32d399133110eb814a4b`.
9. Graph Governor is 13,763 bytes with SHA-256 `762154e199e648692c00c735ebc91e8a79ca21e9b49641de175e4de87c29ef15`.
10. Curator remained byte-identical at 3,932 bytes with SHA-256 `8c14d0b4daf99c6452f9e8189451abfc6878fd06bb977671f6e694bf8b936f9a`.
11. Independent in-memory rebuilds of the four changed packages were byte-identical. Every package entry was source-byte-equal, sorted, safe, DEFLATE-compressed, timestamped `2026-09-04 00:00:00`, and stored with Unix regular-file mode `0644`.
12. Repository whitespace, current version dependencies, and links among the decision, impact assessment, plan, package set, profiles, requirements, and source register passed static checks after this result was added.

## Result

Pass for static source omission, explicit current-Skill prohibitions, fixture absence, historical-contract separation, deterministic packaging, and traceability.

## Interpretation

The current candidate sources and packages encode the accepted intent not to collect or persist Person UPN as managed schema-version-2 data. This static result does not establish Cowork prompting, Microsoft 365 retrieval minimization, validator behavior, graph writes, existing-value preservation, cleanup, or connected behavior at runtime.

## Effects

- Graph effects: none.
- Existing UPN values removed: none.
- External systems accessed: none.