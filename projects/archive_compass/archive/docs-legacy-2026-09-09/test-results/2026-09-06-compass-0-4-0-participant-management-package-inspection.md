# Test result: Compass 0.4.0 participant-management package inspection

## Metadata

- **Date:** 2026-09-06
- **Status:** complete
- **Owner:** Project Dexter laboratory assistant
- **Scope:** Static deterministic package construction and archive inspection only
- **Package set:** [Compass 0.4.0 participant-management candidate](../inventory/compass-0.4.0-participant-management-candidate-package-set.md)

## Direct observations

1. Five new `.skill` archives were created from the current source directories; no prior package was changed.
2. Every archive used sorted forward-slash relative file paths, DEFLATE compression, fixed timestamp `2026-09-04 00:00:00`, Unix regular-file mode `0644`, and no directory entries.
3. Archive paths were relative and safe, with no duplicates.
4. Every archived file was byte-equal to its corresponding source file.
5. An independent rebuild of every package was byte-identical.

| Package | Entries | Size | SHA-256 | Result |
| --- | ---: | ---: | --- | --- |
| `compass-installation-interview-v0.3.0-participant-management-candidate.skill` | 2 | 7,564 | `936e65cd63f4dc196595817d1315583d8f99cf1de7f92b91788b6a66c6307eff` | Pass |
| `compass-daily-scan-v0.3.0-participant-management-candidate.skill` | 2 | 5,030 | `d16dc8f4017bd3fa67309ffbfe7daf01c290059ba722547355543abe13b56087` | Pass |
| `compass-tracking-topic-interview-v0.3.0-participant-management-candidate.skill` | 2 | 4,642 | `08e1a16a879a3becec522f9454d4336320b8512d1d1878b3129117d2d01dcb70` | Pass |
| `compass-curator-v0.3.0-participant-management-candidate.skill` | 2 | 3,798 | `152ebaac902c2d04075a872c2c96f4d9548bcda80ac0edda6e83c524e03380ca` | Pass |
| `graph-governor-v0.4.0-participant-management-candidate.skill` | 4 | 13,017 | `4df11e7dec20839d2ca58ed7fa476f8fc9139d09d01812ea876943cb089b025f` | Pass |

## Interpretation

The exact package bytes faithfully contain the updated source and are reproducible. This result supports package integrity only.

## Limitations

- No package was imported or invoked in Cowork.
- No Microsoft 365 source was accessed.
- No Compass graph was modified or migrated.
- No schema-v2 behavior, conversational interaction, connected write, or Graph Governor runtime claim was tested.
- The planned participant-management scenario remains unexecuted.

## Effects

- Created the five listed candidate packages.
- Modified no prior package, historical fixture, or completed test result.
- External systems accessed: none.