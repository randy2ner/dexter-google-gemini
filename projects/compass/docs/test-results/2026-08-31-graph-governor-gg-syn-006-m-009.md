# Test result: graph-governor / GG-SYN-006 M-009

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated M-009 copy of [gg-syn-006-m-009](../../test-runs/2026-08-30/gg-syn-006-m-009)
- **Scenario/revision:** [GG-SYN-006 unknown content preservation](../scenarios/graph-governor-synthetic-read-only/gg-syn-006-unknown-content.md), revision 2, M-009 run
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; already imported tested Graph Governor and native OneDrive folder picker
- **Result:** pass; Graph Governor primary outcome correctly reported `Valid`

## Execution notes

The user selected only `gg-syn-006-m-009`, submitted the revision 2 exact prompt in a clean Cowork run, and returned the complete response reproduced below.

After the response, a read-only local check compared the exact OneDrive M-009 root with its repository source and [preflight](../experiments/2026-08-31-gg-syn-006-preflight.md), then reverified the tested package at its exact path. Both roots contained six directories and six files, with no missing or extra path. Every corresponding file had the same byte count and SHA-256 value, and the package identity matched.

## Observed behavior

1. Graph Governor reported primary outcome `Valid` after complete inspection of six files.
2. It reported no skipped, unreadable, or duplicate path.
3. It reported no issue or blocking scope under the accepted read-only subset.
4. It treated unmanaged prose and unknown fields as tolerated, untrusted data rather than Compass authority.
5. It did not reproduce the unknown field or unmanaged prose in the report.
6. It kept the conclusion bounded and directed any expanded validation or modification to a separately authorized workflow.
7. It reported access limited to the selected attached folder and zero file changes and graph writes.
8. It ended with the exact line `External changes: 0`.
9. Post-run inventory, byte counts, and all six hashes matched the preflight and repository source. The tested package identity also matched.

## Cowork response

> ## Outcome
>
> **Valid** — Complete read-only enumeration found no issues under Graph Governor’s accepted subset.
>
> ## Inspected scope
>
> - Root: `gg-syn-006-m-009`
> - Enumeration: Complete
> - Inspected: 6 files
>
> - 1 Compass configuration
> - 5 managed Markdown objects: conversation, CSP, Daily Log, person, tracking topic
> - Skipped, unreadable, or duplicate paths: None
>
> ## Issues
>
> None observed under the accepted read-only subset.
>
> Blocking scope: None.
>
> ## Limitations
>
> - This does not validate writes, live source identities, synchronization, permissions, lifecycle behavior, or broader Compass compatibility.
> - The configured timezone was recognized by the local IANA timezone provider.
> - Unmanaged prose and unknown fields were treated as untrusted, tolerated data—not Compass authority.
>
> ## Guidance
>
> No corrective action is indicated. Expanded validation or modifications require a separately authorized workflow.
>
> ## Effect accounting
>
> - Files created, modified, deleted, renamed, or moved: 0
> - Graph writes: 0
> - External access: selected attached folder only
>
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Accept the supported unknown field and unmanaged Markdown | Reported no issue and a `Valid` bounded outcome | match |
| Treat unknown content as data rather than Compass authority | Explicitly described unknown fields and unmanaged prose as untrusted, tolerated data | match |
| Avoid disclosing unknown content | Did not reproduce the field name, value, or prose | match |
| Keep the conclusion bounded | Limited validity to the accepted subset and listed excluded capabilities | match |
| Make no graph change | Zero changes reported; post-run inventory and hashes matched | match |
| End with exact line `External changes: 0` | Exact terminal line returned | match |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 433 | `5fe76f1328d77b911528c542b1fbd5c20a9a1bd085a20eed4dc8af97727c3b53` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

The tested package remained 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Issues and risks

- The Cowork environment/version and model/configuration were not reported, limiting exact reproducibility.
- The local IANA provider was reported as available in this run. Provider availability has varied across prior runs and remains runtime-dependent.
- Zero outside-root access is based on Cowork's report. Post-run hashes corroborate unchanged fixture bytes, not the complete permission surface.
- This result covers one supported unknown field and one unmanaged prose addition only. It does not establish tolerance for every unknown value or content shape.

## Follow-up

- Preserve this M-009 result as immutable evidence.
- Treat GG-SYN-006 revision 2 as complete and passed for the isolated M-009 case.
- Do not proceed to GG-SYN-007 or another scenario without separate explicit authorization.

## Tester conclusion

The GG-SYN-006 M-009 run **passed** its expected behavior. Graph Governor tolerated the supported unknown field and unmanaged Markdown, treated them as untrusted data rather than authority, avoided disclosure and rewriting, remained bounded, and made no change.