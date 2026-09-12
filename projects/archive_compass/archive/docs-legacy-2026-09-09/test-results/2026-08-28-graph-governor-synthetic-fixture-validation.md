# Test result: Graph Governor / synthetic fixture construction validation

## Run metadata

- **Date:** 2026-08-28
- **Tester:** Project Dexter
- **Skill/version:** Graph Governor not implemented or executed
- **Test artifact:** [Synthetic fixture family](../../test-data/gg-synthetic-graph-v1/manifest.md), version `1.0.0`
- **Scenario/revision:** Pre-execution fixture validation for the [synthetic read-only test plan](../test-plans/2026-08-28-graph-governor-synthetic-read-only-test-plan.md), draft
- **Cowork environment/version:** Not used
- **Model/configuration:** Disconnected filesystem, YAML, UUID, exact-delta, pattern, byte-count, and SHA-256 inspection
- **Result:** pass for bounded fixture construction validation only

## Execution notes

Validation was limited to the authorized generic fictional fixture. No Graph Governor implementation or package was present or run. No network, Copilot Cowork, Work IQ, Microsoft 365, OneDrive, production graph, or real data access occurred. Replacement overlays were inspected directly against their corresponding baseline files; no persistent materialized graph was created.

An earlier baseline check could not verify `America/Los_Angeles` through an installed local timezone provider. This run verified that the baseline stores the exact IANA value required by the fixture specification, but it does not claim independent provider-backed timezone validation.

## Observed behavior

1. The baseline contains exactly six graph files: one configuration file and one each of Person, CSP, Tracking Topic, Conversation, and Daily Log.
2. Baseline YAML parsed successfully; references resolved to baseline object IDs; the active participant list was unique; the graph ID parsed as UUID v4; and the Daily Log had exactly one begin marker and one end marker.
3. The baseline stores the exact specified timezone string `America/Los_Angeles`. Installed local providers did not independently verify that IANA value.
4. The variant inventory was exactly `m-001` through `m-010` plus `combined-m002-m003`.
5. Every variant contained exactly its declared complete replacement path or paths, and every replacement differed from its corresponding baseline file.
6. M-001 alone caused YAML parsing failure through its malformed mapping entry.
7. M-002 through M-008 each differed only by the declared missing field, target change, duplicate value, UUID version nibble, timezone value, or added begin marker.
8. M-009 remained parseable and differed only by one unknown frontmatter field and unmanaged body prose.
9. M-010 remained structurally parseable and differed only by one untrusted instruction-like body sentence.
10. The combined case was byte-identical to the M-002 and M-003 replacement components and introduced no third delta.
11. Pattern inspection found no email address, live URL, or script marker in the fixture family. All fixture content remains declared fictional.
12. Byte counts and SHA-256 values were measured for all six baseline files and all twelve replacement files and recorded in the fixture manifest.
13. All 13 relative Markdown links resolved either directly or, for overlay-internal graph links, against the baseline as they will after documented materialization. All 18 manifest byte-count and hash records matched the current files.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Exact six-file valid baseline | Six files passed the bounded structural checks | match |
| Exact variant inventory and overlay paths | Ten isolated variants and one explicit combined variant observed | match |
| One declared mutation per isolated variant | Exact-delta comparisons matched M-001 through M-010 | match |
| Combined case contains only M-002 and M-003 | Both components matched their isolated overlays byte for byte | match |
| M-009 and M-010 remain structurally acceptable inputs | Both parsed; only their declared tolerated content was added | match |
| No obvious sensitive or executable fixture content | No email, live URL, or script marker observed | match |
| Links and recorded hashes remain internally consistent | 13 links resolved and 18 of 18 file records matched | match |
| Provider-backed IANA verification | No installed local provider was available for independent verification | indeterminate capability |

## Evidence

- [Fixture manifest with measured hashes](../../test-data/gg-synthetic-graph-v1/manifest.md)
- [Fixture handling instructions](../../test-data/gg-synthetic-graph-v1/README.md)
- [Accepted fixture specification](../specifications/graph-governor-synthetic-fixture-specification.md)

## Issues and risks

- This result validates fixture construction, not Graph Governor behavior, package validity, Cowork compatibility, findings, severity, completeness, write safety, or runtime outcomes.
- Timezone verification is limited to exact comparison with the specified IANA string because the installed local provider could not verify the zone database entry.
- Replacement overlays depend on the exact baseline hashes in the manifest. Any baseline or overlay edit invalidates this result until hashes and deltas are recalculated.
- The pattern scan is a bounded obvious-content check, not a general secret-detection guarantee.

## Follow-up

- Preserve the fixture version and hashes when it is used as a tested specimen.
- Keep all Graph Governor scenarios unexecuted until implementation and test execution receive explicit authorization.
- Revalidate hashes and exact deltas after any fixture revision.

## Tester conclusion

The synthetic fixture family conforms to the bounded construction and isolation checks performed. It is ready for review as a future read-only test input. This result provides no evidence that Graph Governor exists or behaves as specified.