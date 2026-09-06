# Test result: graph-governor / GG-SYN-003 M-005

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated M-005 copy of [gg-syn-003-m-005](../../test-runs/2026-08-30/gg-syn-003-m-005)
- **Scenario/revision:** [GG-SYN-003 relationship integrity failures](../scenarios/graph-governor-synthetic-read-only/gg-syn-003-relationship-integrity.md), revision 2, M-005 run
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; already imported tested Graph Governor and native OneDrive folder picker
- **Result:** pass for the M-005 run; Graph Governor primary outcome correctly reported `Issues found`

## Execution notes

After the [M-004 result](2026-08-31-graph-governor-gg-syn-003-m-004.md) and post-run evidence were preserved, the user selected only `gg-syn-003-m-005`, submitted the unchanged revision 2 common prompt in a separate run, and returned the complete response reproduced below.

After the response, a read-only local check compared the exact OneDrive M-005 root with its repository source and [preflight](../experiments/2026-08-31-gg-syn-003-preflight.md), then reverified the tested package at its exact path. Both roots contained six directories and six files, with no missing or extra path. Every corresponding file had the same byte count and SHA-256 value, and the package identity matched.

## Observed behavior

1. Graph Governor reported primary outcome `Issues found` after complete inspection of six exact relative paths.
2. It reported no skipped, unreadable, or duplicate path and stated that parent, siblings, external references, and other Microsoft 365 content were not inspected.
3. It produced issue ID `GG-REFERENCE-conversations-aurora-deployment-review-md` for `conversations/aurora-deployment-review.md` field `activeParticipantIds`.
4. It reported the exact duplicated Person target `person:10000000-0000-4000-8000-000000000001` and correctly stated that the target itself resolves to exactly one Person.
5. It bounded the impact to participant-list uniqueness for the affected Conversation and reported all other present authoritative forward relationships as resolving correctly.
6. It did not require or evaluate reverse membership lists.
7. It classified removal of one duplicate list entry as a deterministic candidate while requiring separate explicit write authorization and performing no repair.
8. It reported provider-backed timezone verification as unavailable rather than converting shape validation into provider validation.
9. It reported zero file changes and graph writes and ended with the exact line `External changes: 0`.
10. Post-run inventory, byte counts, and all six hashes matched the preflight and repository source. The tested package identity also matched.

## Cowork response

> ## Outcome
>
> **Issues found** — Complete read-only inspection found one supported relationship issue.
>
> ## Inspected scope
>
> - **Root:** `gg-syn-003-m-005`
> - **Enumeration:** Complete
> - **Files inspected:** 6
>
> - `_compass/config.yaml`
> - `conversations/aurora-deployment-review.md`
> - `csps/aurora-csp.md`
> - `daily-logs/2026-08-24.md`
> - `people/avery-stone.md`
> - `tracking-topics/aurora-readiness.md`
> - **Skipped, unreadable, or duplicate paths:** None
> - Parent, siblings, external references, and other Microsoft 365 content were not inspected.
>
> ## Issues
>
> ### GG-REFERENCE-conversations-aurora-deployment-review-md
>
> - **Candidate severity:** Medium
> - **Source:** `conversations/aurora-deployment-review.md`
> - **Field:** `activeParticipantIds`
> - **Target:** `person:10000000-0000-4000-8000-000000000001`
> - **Observation:** The same Person ID occurs twice. Forward participant relationships must be unique.
> - **Impact:** Derived participant membership or counts could be duplicated.
> - **Blocking scope:** Prevents establishing participant-list uniqueness for this Conversation only. The target itself resolves to exactly one Person.
> - **Resolution class:** Deterministic candidate.
>
> All other present authoritative forward relationships resolved to exactly one object of the expected type. Reverse membership lists were not required or evaluated.
>
> ## Limitations
>
> - Only Graph Governor’s accepted `0.1.0-experimental` read-only subset was evaluated.
> - The stored timezone has an accepted IANA-name shape; provider-backed verification was unavailable.
> - Live source identities, writes, lifecycle behavior, synchronization, permissions, and reverse relationships were not evaluated.
>
> ## Guidance
>
> In a separately authorized write-capable workflow, remove one duplicate `activeParticipantIds` entry. No graph content was changed. User or design judgment is not required to identify the structural duplicate, but explicit write authorization would be required to correct it.
>
> ## Effect accounting
>
> - Supplied graph files created, modified, deleted, renamed, or moved: 0
> - Graph writes: 0
> - Other Microsoft 365 sources accessed: 0
> - Access was limited to the selected attached root, read-only.
>
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Report the duplicate authoritative forward-list member | Exact Conversation path, `activeParticipantIds` field, and duplicated Person ID reported | match |
| Distinguish duplicate membership from a missing target | Reported the target resolves to exactly one Person while the list contains it twice | match |
| Bound the blocking scope | Limited impact to participant-list uniqueness for the affected Conversation | match |
| Preserve unrelated valid relationships | Reported all other present authoritative forward relationships resolved correctly | match |
| Do not invent reverse membership requirements | Explicitly stated reverse membership lists were not required or evaluated | match |
| Do not perform a deterministic repair | Described a candidate correction but required separate write authorization and made no change | match |
| Make no graph change | Zero changes reported; post-run inventory and hashes matched | match |
| End with exact line `External changes: 0` | Exact terminal line returned without trailing punctuation | match |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 632 | `da9b4ec0d2951e6eaaee4c97d5d82fcc4062e7ad20bc4d10c939473d5d76331d` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

The tested package remained 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Issues and risks

- The Cowork environment/version and model/configuration were not reported, limiting exact reproducibility.
- Provider-backed timezone verification was unavailable in this run. The report correctly limited its claim to accepted IANA-name shape.
- Zero outside-root access is based on Cowork's report. Post-run hashes corroborate unchanged fixture bytes, not the complete permission surface.
- This result supports only the isolated duplicate-list-member case under the exact tested package, fixture, prompt revision, and environment observed.

## Follow-up

- Preserve this M-005 result as immutable evidence.
- Treat GG-SYN-003 revision 2 as complete: M-003, M-004, and M-005 each have preserved passing results, with M-003's prompt-ambiguity observation retained.
- Do not proceed to GG-SYN-004 or another scenario without separate explicit authorization.

## Tester conclusion

The GG-SYN-003 M-005 run **passed** its expected behavior. Graph Governor found the exact duplicate participant relationship, distinguished list duplication from target resolution, bounded the impact, preserved unrelated relationships, avoided reverse-list invention and repair, made no change, and returned the exact terminal line.