# Test result: Compass 0.4.1 archival-success package inspection

## Metadata

- **Date:** 2026-09-06
- **Status:** complete static package inspection
- **Owner:** Project Dexter laboratory assistant
- **Package set:** [Compass 0.4.1 archival-success candidates](../inventory/compass-0.4.1-archival-success-candidate-package-set.md)

## Direct observations

1. Tracking Topic Interview package size is 4,972 bytes with SHA-256 `b68963ade7e03a83156ec25d9db7742cc66d91c2a1c2b4e0bf467f99f493146c`.
2. Graph Governor package size is 13,312 bytes with SHA-256 `8b659b1f686699cb245998aa8e3667218fab405215ee09c9bcb8b8850902329e`.
3. Independent in-memory rebuilds were byte-identical to both package files.
4. Entries were sorted safe relative paths, DEFLATE-compressed, timestamped `2026-09-04 00:00:00`, and stored with Unix regular-file mode `0644`.
5. Every package entry was byte-equal to its current source file and no extra entry was present.

## Result

Pass for deterministic static packaging of the two revised Skills.

## Interpretation

The packages accurately contain their source. This result does not establish import, activation, conversational behavior, graph mutation, or post-write verification.

## Effects

- Graph effects: none.
- External systems accessed: none.