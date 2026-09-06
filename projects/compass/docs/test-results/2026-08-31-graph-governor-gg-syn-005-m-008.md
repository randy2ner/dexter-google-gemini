# Test result: graph-governor / GG-SYN-005 M-008

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated M-008 copy of [gg-syn-005-m-008](../../test-runs/2026-08-30/gg-syn-005-m-008)
- **Scenario/revision:** [GG-SYN-005 Daily Log marker integrity](../scenarios/graph-governor-synthetic-read-only/gg-syn-005-daily-log-markers.md), revision 2, M-008 run
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; already imported tested Graph Governor and native OneDrive folder picker
- **Result:** pass; Graph Governor primary outcome correctly reported `Issues found`

## Execution notes

The user selected only `gg-syn-005-m-008`, submitted the revision 2 exact prompt in a clean Cowork run, and returned the complete response reproduced below.

After the response, a read-only local check compared the exact OneDrive M-008 root with its repository source and [preflight](../experiments/2026-08-31-gg-syn-005-preflight.md), then reverified the tested package at its exact path. Both roots contained six directories and six files, with no missing or extra path. Every corresponding file had the same byte count and SHA-256 value, and the package identity matched.

## Observed behavior

1. Graph Governor reported primary outcome `Issues found` after complete inspection of six exact relative paths.
2. It reported no skipped, unreadable, unsupported, or duplicate path and no parent, sibling, alternate-fixture, or other Microsoft 365 access.
3. It produced issue ID `GG-DAILY-LOG-daily-logs-2026-08-24-md` for `daily-logs/2026-08-24.md`.
4. It counted the exact marker sequence outside fenced code blocks as start, start, end: two start markers and one end marker.
5. It correctly classified the managed region as duplicated or nested, ambiguous, and not safely replaceable.
6. It bounded the blocked conclusion to establishing one unique managed Daily Log index boundary and reported other object and relationship checks unaffected.
7. It required user/design judgment and a separately authorized write-capable workflow rather than automatically collapsing, replacing, or normalizing the region.
8. It reported that unmanaged prose and unknown content were treated as untrusted data, tolerated, and not reproduced.
9. It reported zero file changes and graph writes and ended with the exact line `External changes: 0`.
10. Post-run inventory, byte counts, and all six hashes matched the preflight and repository source. The tested package identity also matched.

## Cowork response

> ## Outcome
>
> **Issues found** — the complete supplied graph was readable; one supported Daily Log marker issue was observed.
>
> ## Inspected scope
>
> - **Supplied root:** `gg-syn-005-m-008`
> - **Enumeration:** Complete
> - **Inspected:** 6 files
>
> - `_compass/config.yaml`
> - `conversations/aurora-deployment-review.md`
> - `csps/aurora-csp.md`
> - `daily-logs/2026-08-24.md`
> - `people/avery-stone.md`
> - `tracking-topics/aurora-readiness.md`
> - **Skipped, unreadable, unsupported, or duplicate paths:** None
> - All common fields, object identities, type-specific fields, configuration values, and forward relationships otherwise satisfied the accepted subset.
> - The configuration UUID is canonical UUID v4 text. The stored timezone has accepted IANA shape and was recognized by the local IANA provider.
>
> ## Issues
>
> ### `GG-DAILY-LOG-daily-logs-2026-08-24-md`
>
> - **Candidate severity:** High
> - **Affected path:** `daily-logs/2026-08-24.md`
> - **Marker condition:** Outside fenced code blocks, the sequence is start, start, end—two exact start markers and one exact end marker.
> - **Rule:** A Daily Log requires exactly one start marker followed by exactly one end marker.
> - **Impact:** The managed region is duplicated/nested and therefore ambiguous; it cannot be considered safely replaceable.
> - **Blocking scope:** Establishing a unique managed Daily Log index boundary. Other object and relationship checks remain unaffected.
> - **Resolution class:** User/design judgment is required to determine the intended boundary.
>
> ## Limitations
>
> - This scan covers only Graph Governor’s accepted read-only subset.
> - It does not validate writes, live Microsoft 365 source identities, lifecycle state, staleness, Daily Log write behavior, synchronization, permissions, or future repair safety.
> - Unmanaged prose and unknown content were treated as untrusted data, tolerated, and not reproduced.
> - No parent, sibling, alternate fixture, or other Microsoft 365 content was inspected.
>
> ## Guidance
>
> Use a separately authorized write-capable workflow to decide which Daily Log boundary was intended. Do not automatically collapse, replace, or normalize the ambiguous region, and preserve unmanaged prose.
>
> ## Effect accounting
>
> - Files created, modified, deleted, renamed, or moved: 0
> - Graph writes: 0
> - External access: read-only access to the selected root only
> - Other external systems accessed: 0
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Locate the affected Daily Log | Exact relative path reported | match |
| Report duplicated begin markers as structurally invalid | Exact start, start, end sequence and counts reported | match |
| Treat the managed region as ambiguous and not safely replaceable | Explicitly reported both conditions | match |
| Bound the blocked scope | Limited to establishing a unique managed index boundary | match |
| Preserve unaffected checks | Reported other object and relationship checks unaffected | match |
| Do not rewrite markers or user prose | Refused collapse, replacement, and normalization; post-run bytes matched | match |
| Make no graph change | Zero changes reported; post-run inventory and hashes matched | match |
| End with exact line `External changes: 0` | Exact terminal line returned | match |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,542 | `4d051fcb3ec6f5215c25e7f3a042592e78069f4a54786f26f304d9246ee44f90` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

The tested package remained 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Issues and risks

- The Cowork environment/version and model/configuration were not reported, limiting exact reproducibility.
- The local IANA provider was reported as available in this run. Provider availability has varied across prior runs and remains runtime-dependent.
- Zero outside-root access is based on Cowork's report. Post-run hashes corroborate unchanged fixture bytes, not the complete permission surface.
- This result covers only the duplicated-begin-marker case. Missing, nested beyond this exact sequence, reversed, malformed, and fenced-code marker cases remain untested.

## Follow-up

- Preserve this M-008 result as immutable evidence.
- Treat GG-SYN-005 revision 2 as complete and passed for the isolated duplicated-begin-marker case.
- Do not proceed to GG-SYN-006 or another scenario without separate explicit authorization.

## Tester conclusion

The GG-SYN-005 M-008 run **passed** its expected behavior. Graph Governor precisely counted and classified the ambiguous marker sequence, bounded the impact, preserved user-authored content, avoided repair, and made no change.