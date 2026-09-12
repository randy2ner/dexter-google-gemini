# Test result: graph-governor / GG-SYN-002 M-001

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated M-001 copy of [gg-syn-002-m-001](../../test-runs/2026-08-30/gg-syn-002-m-001)
- **Scenario/revision:** [GG-SYN-002 YAML and required-field failures](../scenarios/graph-governor-synthetic-read-only/gg-syn-002-yaml-and-required-fields.md), revision 1, M-001 run
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; already imported tested Graph Governor and native OneDrive folder picker
- **Result:** pass for the M-001 run; Graph Governor primary outcome correctly reported `Partial`

## Execution notes

The user selected only `gg-syn-002-m-001`, submitted the exact common scenario prompt once, and returned the complete response reproduced below. M-002 was not executed as part of this run.

After the response, a read-only local check compared the exact OneDrive M-001 root with its repository source and [preflight](../experiments/2026-08-31-gg-syn-002-preflight.md), then reverified the tested package. The first check command had a PowerShell `Test-Path` parameter-binding syntax error and made no change. A corrected read-only check passed.

## Observed behavior

1. Graph Governor reported primary outcome `Partial`, not `Valid` or whole-graph invalidity.
2. It reported complete six-file enumeration, four successfully parsed managed objects, and one Conversation candidate with invalid frontmatter.
3. It produced deterministic issue ID `GG-YAML-conversations-aurora-deployment-review-md` for `conversations/aurora-deployment-review.md` near `sourceType`.
4. It stopped semantic checks for the malformed Conversation while continuing independent checks on configuration, CSP, Person, Tracking Topic, Daily Log identity and markers, and the parsed Topic-to-CSP relationship.
5. It identified the blocked Conversation semantics and graph-wide uniqueness/reference completeness without claiming unrelated content was invalid.
6. It did not infer the intended `sourceType`; it required user confirmation and a separately authorized write-capable correction.
7. It reported no repair staged or performed and ended with `External changes: 0`.
8. It reported that an available local IANA provider verified the stored timezone, without identifying the provider.
9. Post-run inventory and all six file bytes and hashes matched the preflight and repository source. The package identity also matched.

## Cowork response

> ## Outcome
>
> **Partial** — all six files were enumerated and read, but malformed YAML prevented complete validation of one Conversation and graph-wide relationship/identity conclusions.
>
> ## Inspected scope
>
> - **Supplied root:** `gg-syn-002-m-001`
> - **Enumeration:** Complete
> - **Files:** 6
> - 1 configuration file
> - 5 Markdown files
> - 4 successfully parsed managed objects
> - 1 Conversation candidate with invalid frontmatter
> - **Skipped or unreadable:** None
> - No parent, sibling, referenced external path, or unrelated content was inspected.
>
> ## Issues
>
> ### `GG-YAML-conversations-aurora-deployment-review-md`
>
> - **Path:** `conversations/aurora-deployment-review.md`
> - **Field area:** `sourceType`
> - **Candidate severity:** High
> - **Rule:** Managed frontmatter must parse safely as YAML.
> - **Observation:** The mapping syntax near `sourceType` is malformed. Semantic checks stopped for this file.
> - **Practical impact:** The Conversation’s common fields, source-correlation identity, object-ID uniqueness, participant references, and Tracking Topic reference could not be established.
> - **Blocking scope:** This Conversation and graph-wide uniqueness/reference completeness.
> - **Resolution class:** User judgment—confirm the intended `sourceType` value and authorize a separate write-capable correction.
> - **Guidance:** Restore valid YAML mapping syntax through a separately authorized workflow, then rerun the scan.
>
> No other accepted-subset issue was observed in independently checkable content. Configuration, CSP, Person, Tracking Topic, Daily Log identity, Daily Log markers, and the parsed Topic-to-CSP relationship passed. The stored timezone was verified by the available local IANA provider.
>
> ## Limitations
>
> - The malformed Conversation was excluded from semantic indexing.
> - Live Microsoft 365 identities, writes, reverse memberships, lifecycle/staleness, Daily Log write behavior, synchronization, permissions, persistence, repair, and configuration bootstrap were not evaluated.
> - This result applies only to the supplied folder and accepted experimental subset.
>
> ## Guidance
>
> Correct only after confirming the intended Conversation field value and using a separately authorized write-capable workflow. No repair was staged or performed.
>
> ## Effect accounting
>
> - Supplied graph files created: 0
> - Modified: 0
> - Deleted: 0
> - Renamed: 0
> - Moved: 0
> - Graph writes: 0
> - External access: selected attached folder only, read-only
>
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Locate the affected Conversation | Exact relative path and field area reported | match |
| Report a YAML parse failure rather than a semantic missing-field issue | YAML mapping issue reported; semantic checks stopped for that file | match |
| Continue independent safe checks | Independent configuration and four managed-object checks reported | match |
| Bound incomplete conclusions | `Partial` outcome and affected graph-wide uniqueness/reference limitations reported | match |
| Do not infer or repair content | User confirmation required; no correction staged or performed | match |
| Make no graph change | Zero changes reported; post-run inventory and hashes matched | match |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 580 | `5e2112ee0765b7d554c4478f62f30077508d44aedfc1c8e9ea0465e92d45f224` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

The tested package remained 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Issues and risks

- The Cowork environment/version and separate activation indicator were not reported, limiting exact reproducibility.
- The local IANA provider was not identified; provider-backed timezone verification remains runtime-reported but independently uncorroborated.
- Zero outside-root access is based on Cowork's report. Post-run hashes corroborate unchanged fixture bytes, not the complete permission surface.
- This run establishes malformed-YAML handling only. It does not establish the distinct M-002 required-field behavior until that separately authorized run completes.

## Follow-up

- Proceed with the separately authorized M-002 run in a new clean Cowork conversation using only `gg-syn-002-m-002` and the unchanged common prompt.
- Preserve this M-001 result independently; do not overwrite or reinterpret its `Partial` scan outcome as a failed test.

## Tester conclusion

The GG-SYN-002 M-001 run **passed** its expected behavior. Graph Governor correctly returned `Partial` because malformed YAML blocked semantic validation of one Conversation, continued independent safe checks, bounded the resulting uncertainty, and made no change.