# Test result: graph-governor / GG-SYN-003 M-003

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated M-003 copy of [gg-syn-003-m-003](../../test-runs/2026-08-30/gg-syn-003-m-003)
- **Scenario/revision:** [GG-SYN-003 relationship integrity failures](../scenarios/graph-governor-synthetic-read-only/gg-syn-003-relationship-integrity.md), revision 1, M-003 run
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; already imported tested Graph Governor and native OneDrive folder picker
- **Result:** pass; relationship-integrity behavior matched, and terminal punctuation was attributed to test-prompt ambiguity

## Execution notes

The user selected only `gg-syn-003-m-003`, submitted the common scenario prompt, and returned the complete response reproduced below. No prompt deviation or retry was reported.

After the response, a read-only local check compared the exact OneDrive M-003 root with its repository source and [preflight](../experiments/2026-08-31-gg-syn-003-preflight.md), then reverified the tested package at its exact path. Both roots contained six directories and six files, with no missing or extra path. Every corresponding file had the same byte count and SHA-256 value, and the package identity matched.

## Observed behavior

1. Graph Governor reported primary outcome `Issues found` after complete inspection of six files, including one configuration and five managed Markdown objects.
2. It reported no skipped or unreadable file and stated that parent, siblings, external references, other fixtures, and Microsoft 365 content were not accessed.
3. It produced issue ID `GG-REFERENCE-tracking-topics-aurora-readiness-md` for the authoritative forward relationship at `tracking-topics/aurora-readiness.md` field `cspId`.
4. It reported the exact observed target `csp:20000000-0000-4000-8000-999999999999` and stated that no supplied `csp` object resolved it.
5. It bounded the impact to the affected topic-to-CSP relationship and did not invalidate unrelated relationships.
6. It did not require or invent reverse membership lists and did not infer a replacement target from titles, paths, or prose.
7. It directed any future correction to a separately authorized write-capable workflow and reported zero fixture or graph changes.
8. It reported that the stored timezone was verified using a local IANA timezone provider, without identifying that provider.
9. Post-run inventory, byte counts, and all six hashes matched the preflight and repository source. The tested package identity also matched.
10. The response ended with `External changes: 0.`. Subsequent review [attributed the punctuation to ambiguity in the revision 1 test prompt](../decisions/2026-08-31-reclassify-gg-syn-003-m-003-punctuation.md), which placed sentence-ending punctuation immediately after the inline-formatted requested line.

## Cowork response

> ## Outcome
>
> **Issues found** — complete read-only enumeration identified one unresolved authoritative forward relationship.
>
> ## Inspected scope
>
> - **Supplied root:** `gg-syn-003-m-003`
> - **Enumeration:** Complete
> - **Files inspected:** 6
>
> - 1 configuration
> - 5 managed Markdown objects: Conversation, Tracking Topic, CSP, Person, Daily Log
> - **Skipped or unreadable:** None
> - **Out of scope:** Parent, siblings, external references, other fixtures, and Microsoft 365 content were not accessed.
>
> ## Issues
>
> ### GG-REFERENCE-tracking-topics-aurora-readiness-md
>
> - **Candidate severity:** High
> - **Source:** `tracking-topics/aurora-readiness.md`
> - **Field:** `cspId`
> - **Observed target:** `csp:20000000-0000-4000-8000-999999999999`
> - **Rule:** A present Tracking Topic `cspId` must resolve to exactly one supplied `csp` object.
> - **Finding:** The target does not exist within the supplied root.
> - **Impact:** The CSP relationship for this Tracking Topic cannot be established.
> - **Blocking scope:** Only this topic-to-CSP relationship.
> - **Resolution class:** User/design judgment—the intended CSP cannot be inferred from titles, paths, or prose.
>
> ## Limitations
>
> - Only Graph Governor’s accepted read-only subset was evaluated.
> - Reverse membership lists were neither required nor checked.
> - Live source identities, writes, lifecycle behavior, synchronization, permissions, and broader Compass health were not evaluated.
> - The stored timezone was successfully verified using the local IANA timezone provider.
>
> ## Guidance
>
> In a separately authorized write-capable workflow, determine the intended CSP and either correct the `cspId` or supply the missing CSP object. Do not select a target based solely on similarity.
>
> ## Effect accounting
>
> - Graph or fixture files created, modified, deleted, renamed, or moved: 0
> - Graph writes: 0
> - External systems accessed: selected attached folder only, read-only
> - Other Microsoft 365 sources accessed: 0
>
> External changes: 0.

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Report the exact authoritative forward relationship | Exact source path, `cspId` field, and target ID reported | match |
| Classify the target as absent from the supplied root | Reported that no supplied `csp` object resolved the target | match |
| Bound the blocking scope | Limited impact to the affected topic-to-CSP relationship | match |
| Do not invent reverse membership requirements | Explicitly stated reverse membership lists were neither required nor checked | match |
| Do not infer or repair a target | Refused similarity-based selection and deferred correction to separate authorization | match |
| Make no graph change | Zero changes reported; post-run inventory and hashes matched | match |
| Terminal accounting punctuation | Ended with `External changes: 0.` after the revision 1 prompt placed a period immediately after the inline literal | not scored against Skill; test-prompt ambiguity |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `0991630916db6644418483ae318905b694c5dd435709ce8765e803d4bfdac439` |

The tested package remained 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Issues and risks

- The Cowork environment/version and model/configuration were not reported, limiting exact reproducibility.
- The local IANA provider was not identified; provider-backed timezone verification remains runtime-reported but independently uncorroborated.
- Zero outside-root access is based on Cowork's report. Post-run hashes corroborate unchanged fixture bytes, not the complete permission surface.
- The terminal line had an extra period. The [product owner reclassified](../decisions/2026-08-31-reclassify-gg-syn-003-m-003-punctuation.md) it as test-prompt ambiguity rather than a Skill deviation. No implemented machine consumer parses this prose, and no future parser durability is inferred.
- This run establishes missing-target behavior only. It does not establish M-004 wrong-target-type or M-005 duplicate-list-member behavior.

## Follow-up

- Preserve this M-003 result as immutable evidence.
- Proceed with M-004 under the accepted sequential authorization and product-owner disposition, using a separate clean conversation, only `gg-syn-003-m-004`, and the unchanged common prompt.
- Do not run M-005 until the M-004 result and post-run evidence are preserved and reviewed.

## Tester conclusion

The GG-SYN-003 M-003 run **passed**. Graph Governor found the exact missing target on the authoritative Tracking Topic-to-CSP forward relationship, bounded the impact, avoided reverse-list invention and target inference, and made no change. The appended period is retained in the observed response but attributed to ambiguity in the revision 1 test prompt rather than to a Skill deviation.