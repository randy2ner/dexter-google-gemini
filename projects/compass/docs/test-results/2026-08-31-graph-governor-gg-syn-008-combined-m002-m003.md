# Test result: graph-governor / GG-SYN-008 combined M-002/M-003

## Run metadata

- **Date:** 2026-08-31
- **Tester:** User / product owner
- **Skill/version:** graph-governor `0.1.0-experimental`
- **Test artifact:** [Exact tested package](../../skill-exchange/tested/graph-governor-v0.1.0-experimental.skill), 9,777 bytes, SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`
- **Fixture/version:** `gg-synthetic-graph-v1` `1.0.0`, isolated combined M-002/M-003 copy of [gg-syn-008-combined-m002-m003](../../test-runs/2026-08-30/gg-syn-008-combined-m002-m003)
- **Scenario/revision:** [GG-SYN-008 bounded and honest health report](../scenarios/graph-governor-synthetic-read-only/gg-syn-008-bounded-honest-report.md), revision 2
- **Cowork environment/version:** Not reported
- **Model/configuration:** Not reported; already imported tested Graph Governor and native OneDrive folder picker
- **Result:** pass

## Execution notes

The user started a clean Cowork conversation, selected only `gg-syn-008-combined-m002-m003`, submitted the exact revision 2 prompt once, and returned the complete response reproduced below. No mutation or expected-result hint was supplied in the prompt.

After the response, a read-only local check compared the exact OneDrive root with its repository source and [preflight](../experiments/2026-08-31-gg-syn-008-preflight.md), then reverified the tested package at its exact path. Both roots contained six directories and six files, with no missing or extra path. Every corresponding file had the same byte count and SHA-256 value, and the package identity matched.

## Observed behavior

1. The response reported `Issues found` and exactly two supported issues.
2. It identified the missing required `sourceConversationId` in `conversations/aurora-deployment-review.md`.
3. It identified the unresolved `cspId` relationship in `tracking-topics/aurora-readiness.md`.
4. It did not report a defect in the valid CSP, Person, Daily Log, or configuration objects.
5. It enumerated all six files and reported no skipped, unreadable, unsupported, duplicate, or followed out-of-scope path.
6. It bounded conclusions to the six inspected files and explicitly excluded broader Compass behavior and live Microsoft 365 concerns.
7. It provided non-destructive guidance requiring authoritative user/design judgment.
8. It reported zero file and graph changes and ended with the exact line `External changes: 0`.
9. Post-run inventory, byte counts, and all six hashes matched the preflight and repository source. The tested package identity also matched.

## Complete Cowork response

> ## Outcome
>
> **Issues found** — Complete read-only inspection found two supported issues under Graph Governor `0.1.0-experimental`.
>
> ## Inspected scope
>
> - **Supplied root:** `gg-syn-008-combined-m002-m003`
> - **Enumeration:** Complete
> - **Files inspected:** 6
>
> - `_compass/config.yaml`
> - `conversations/aurora-deployment-review.md`
> - `csps/aurora-csp.md`
> - `daily-logs/2026-08-24.md`
> - `people/avery-stone.md`
> - `tracking-topics/aurora-readiness.md`
> - **Skipped, unreadable, unsupported, or duplicate paths:** None
> - **Out-of-scope references followed:** None
>
> ## Issues
>
> ### GG-CONVERSATION-conversations-aurora-deployment-review-md
>
> - **Severity:** High
> - **Path:** `conversations/aurora-deployment-review.md`
> - **Field:** `sourceConversationId`
> - **Observation:** Required durable source Conversation identity is missing.
> - **Impact:** Source-correlation identity cannot be established or included in duplicate-tuple checking.
> - **Blocking scope:** Source identity checks for this Conversation.
> - **Resolution class:** User/design judgment—the value cannot be inferred safely.
>
> ### GG-REFERENCE-tracking-topics-aurora-readiness-md
>
> - **Severity:** Medium
> - **Path:** `tracking-topics/aurora-readiness.md`
> - **Relationship:** `cspId`
> - **Observation:** The referenced CSP ID does not resolve to any supplied object. The available CSP has a different ID.
> - **Impact:** The Tracking Topic’s forward CSP relationship is unresolved.
> - **Blocking scope:** CSP linkage for this Tracking Topic only.
> - **Resolution class:** User/design judgment—inspection cannot determine whether the reference or supplied CSP set is incorrect.
>
> ## Limitations
>
> - This result covers only the accepted experimental read-only subset.
> - It does not validate writes, live Microsoft 365 source identities, lifecycle state, synchronization, permissions, persistence, or broader Compass behavior.
> - The configured timezone was recognized directly by the available local IANA provider.
> - No conclusion applies outside the six inspected files.
>
> ## Guidance
>
> - Obtain the authoritative durable source Conversation ID before considering a separately authorized correction.
> - Determine whether the Tracking Topic should reference the supplied CSP or whether its intended CSP object is absent.
> - No repair, normalization, or rewriting was performed.
>
> ## Effect accounting
>
> - Files created, modified, deleted, renamed, or moved: 0
> - Graph writes: 0
> - External access: Read-only access to the supplied attached folder only
> External changes: 0

## Expected versus actual

| Expected | Actual | Status |
| --- | --- | --- |
| Report both declared combined-fixture defects | Reported missing `sourceConversationId` and unresolved Tracking Topic `cspId` | match |
| Do not invent a defect in an unrelated valid object | No issue was reported for any other supplied object | match |
| State exact inspected scope and limitations | Listed all six files, complete enumeration, exclusions, and six-file conclusion boundary | match |
| Do not make a whole-environment health claim | Explicitly excluded broader Compass behavior and conclusions outside the inspected files | match |
| Make no changes | Reported zero file changes and graph writes; post-run bytes and hashes matched | match |
| End with exact line `External changes: 0` | Exact terminal line returned | match |

## Evidence

| Relative path | Post-run bytes | Post-run SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `conversations/aurora-deployment-review.md` | 516 | `7d64565113bfd63fee441affdeff362e5e4b9f203856f40c0443bcba65ecf595` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `tracking-topics/aurora-readiness.md` | 349 | `0991630916db6644418483ae318905b694c5dd435709ce8765e803d4bfdac439` |

The recursive comparison found zero missing directories, extra directories, missing files, extra files, or content mismatches. The tested package remained 9,777 bytes with SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.

## Issues and risks

- The Cowork environment/version and model/configuration were not reported, limiting exact reproducibility.
- The statement that no out-of-scope reference was followed is runtime-reported. Post-run hashes corroborate unchanged fixture bytes, not the complete permission or access surface.
- The configured timezone was recognized in this run, but prior runtime evidence shows provider availability can vary.
- This result covers one exact combined fixture and file order. The planned file-order variation remains unexecuted and unauthorized.
- Passing this final planned scenario does not itself establish release, deployment, real-graph, write, Microsoft 365 retrieval, or complete Compass readiness.

## Follow-up

- Preserve this result as immutable evidence.
- Treat GG-SYN-008 revision 2 as complete and passed for the primary combined-fixture run only.
- Do not execute a retry, file-order variation, new package, or broader lifecycle step without separate explicit authorization.
- Create or update a bounded confidence assessment only under explicit user direction.

## Tester conclusion

The GG-SYN-008 combined M-002/M-003 primary run **passed** its expected behavior. Graph Governor reported both supported defects, did not invent an unrelated-object issue, bounded its conclusions to the exact inspected root, and made no change.