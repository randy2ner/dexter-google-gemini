# Test result: Compass 0.5.0 attention-state package inspection

## Metadata

- **Date:** 2026-09-06
- **Status:** complete static package inspection
- **Owner:** Project Dexter laboratory assistant
- **Package set:** [Compass 0.5.0 attention-state candidates](../inventory/compass-0.5.0-attention-state-candidate-package-set.md)

## Direct observations

1. Five new package files were built from current Skill source; all prior package files remained unchanged.
2. Installation Interview is 7,791 bytes with SHA-256 `26edb2814dfdf5bacda414174e3250852c1e8ab94e05362cd09229aa87541d5e`.
3. Daily Scan is 5,150 bytes with SHA-256 `1ea4e4df421dc1cca0b68c99556b6309493e308aa855ade06ae0da5bb46a6dca`.
4. Tracking Topic Interview is 5,538 bytes with SHA-256 `e86389fd5de080985d862624a5a8baa9898384d528271ace1ead49d5a77b2f50`.
5. Curator is 3,932 bytes with SHA-256 `8c14d0b4daf99c6452f9e8189451abfc6878fd06bb977671f6e694bf8b936f9a`.
6. Graph Governor is 13,539 bytes with SHA-256 `135378988643603bbe5b1fee316ea8753ee860cfd2ba68a9a0e9c4fdbf8ce38c`.
7. Independent in-memory rebuilds were byte-identical. Every entry was source-byte-equal, sorted, safe, DEFLATE-compressed, timestamped `2026-09-04 00:00:00`, and stored with Unix regular-file mode `0644`.

## Result

Pass for deterministic static packaging of the five attention-state candidates.

## Interpretation

The packages accurately contain current source. This does not establish import, activation, conversational behavior, graph mutation, or verification behavior.

## Effects

- Graph effects: none.
- External systems accessed: none.