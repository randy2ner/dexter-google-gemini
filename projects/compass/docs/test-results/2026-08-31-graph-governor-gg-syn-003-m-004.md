# Test result: graph-governor / GG-SYN-003 M-004

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated M-004 copy of [gg-syn-003-m-004](../../test-runs/2026-08-30/gg-syn-003-m-004)
- **Scenario/revision:** [GG-SYN-003 relationship integrity failures](../scenarios/graph-governor-synthetic-read-only/gg-syn-003-relationship-integrity.md), revision 2, M-004 run
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; already imported tested Graph Governor and native OneDrive folder picker
- **Result:** pass for the M-004 run; Graph Governor primary outcome correctly reported `Issues found`

## Execution notes

After the [M-003 result](2026-08-31-graph-governor-gg-syn-003-m-003.md) and its punctuation review were preserved, the user selected only `gg-syn-003-m-004`, submitted the revision 2 common scenario prompt in a separate run, and returned the complete response reproduced below.

After the response, a read-only local check compared the exact OneDrive M-004 root with its repository source and [preflight](../experiments/2026-08-31-gg-syn-003-preflight.md), then reverified the tested package at its exact path. Both roots contained six directories and six files, with no missing or extra path. Every corresponding file had the same byte count and SHA-256 value, and the package identity matched.

## Observed behavior

1. Graph Governor reported primary outcome `Issues found` after complete inspection of six files, including one configuration and five managed Markdown objects.
2. It reported no skipped or unreadable file and no out-of-scope access.
3. It produced issue ID `GG-REFERENCE-conversations-aurora-deployment-review-md` for the authoritative forward relationship at `conversations/aurora-deployment-review.md` field `trackingTopicId`.
4. It reported the exact observed target `csp:20000000-0000-4000-8000-000000000001`, resolved it to `csps/aurora-csp.md`, and correctly distinguished the target's `csp` type from the required `tracking-topic` type.
5. It bounded the impact to the affected Conversation-to-Tracking-Topic relationship and did not report an unrelated relationship issue.
6. It did not require a reverse membership list or infer the intended Tracking Topic.
7. It directed any future correction to a separately authorized write-capable workflow and reported no repair.
8. It reported zero file changes and graph writes and ended with the exact line `External changes: 0`.
9. Post-run inventory, byte counts, and all six hashes matched the preflight and repository source. The tested package identity also matched.

## Cowork response

> ## Outcome
>
> **Issues found** — the complete supplied scope was readable; one wrong-type forward relationship was found.
>
> ## Inspected scope
>
> - Root: `gg-syn-003-m-004`
> - Enumeration: Complete
> - Inspected: 6 files
>
> - 1 graph configuration
> - 5 managed Markdown objects: Conversation, Tracking Topic, CSP, Person, Daily Log
> - Skipped or unreadable: None
> - Out-of-scope content accessed: None
>
> ## Issues
>
> **GG-REFERENCE-conversations-aurora-deployment-review-md**
>
> - **Candidate severity:** Medium
> - **Path:** `conversations/aurora-deployment-review.md`
> - **Field:** `trackingTopicId`
> - **Observed target:** `csp:20000000-0000-4000-8000-000000000001` in `csps/aurora-csp.md`
> - **Rule:** A Conversation’s `trackingTopicId` must resolve to exactly one `tracking-topic`; this target is a `csp`.
> - **Impact:** Tracking-topic membership cannot be established for this Conversation.
> - **Blocking scope:** Only this Conversation-to-Tracking-Topic relationship and its derived membership.
> - **Resolution class:** User/design judgment; the intended Tracking Topic cannot be inferred.
>
> ## Limitations
>
> - Checked only Graph Governor’s accepted read-only subset.
> - Did not validate live Microsoft 365 identities, reverse membership lists, writes, lifecycle behavior, synchronization, permissions, or persistence.
> - The configured timezone passed IANA shape and local provider verification.
> - This result does not establish broader Compass or environment health.
>
> ## Guidance
>
> Review the intended `trackingTopicId` and, if correction is desired, use a separately authorized write-capable workflow. No repair was performed.
>
> ## Effect accounting
>
> - Files created, modified, deleted, renamed, or moved: 0
> - Graph writes: 0
> - External access: selected attached folder only, read-only
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Report the exact authoritative forward relationship | Exact Conversation path, `trackingTopicId` field, and target ID reported | match |
| Distinguish a wrong-type target from an absent target | Resolved the target to the supplied CSP and reported `csp` rather than required `tracking-topic` | match |
| Bound the blocking scope | Limited impact to the affected Conversation-to-Tracking-Topic relationship | match |
| Do not invent reverse membership requirements | Explicitly listed reverse membership lists among excluded checks | match |
| Do not infer or repair a target | Stated the intended Tracking Topic cannot be inferred and deferred correction to separate authorization | match |
| Make no graph change | Zero changes reported; post-run inventory and hashes matched | match |
| End with exact line `External changes: 0` | Exact terminal line returned without trailing punctuation | match |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 570 | `ba5df422052063a1627d6a37f0360e9eefc74dc63a76f45beaf980a57b728b0f` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |

The tested package remained 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Issues and risks

- The Cowork environment/version and model/configuration were not reported, limiting exact reproducibility.
- The local IANA provider was not identified; provider-backed timezone verification remains runtime-reported but independently uncorroborated.
- Zero outside-root access is based on Cowork's report. Post-run hashes corroborate unchanged fixture bytes, not the complete permission surface.
- One successful revision 2 terminal line is consistent with the prompt clarification helping, but does not establish general output determinism or machine-interface durability.
- This run establishes wrong-target-type behavior only. M-005 duplicate-list-member behavior remains untested.

## Follow-up

- Preserve this M-004 result as immutable evidence.
- Under the accepted sequential GG-SYN-003 authorization, run M-005 once in a separate clean Cowork conversation using only `gg-syn-003-m-005` and the unchanged revision 2 common prompt.
- Preserve and review M-005 before assessing the completed GG-SYN-003 scenario.

## Tester conclusion

The GG-SYN-003 M-004 run **passed** its expected behavior. Graph Governor resolved the supplied target, correctly classified its wrong object type, bounded the impact, avoided reverse-list invention and target inference, made no change, and returned the clarified exact terminal line.