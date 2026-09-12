# Test Plan 07: Outlet Guidance Value and Accuracy

## Metadata

- **Status:** ready, not run
- **Candidate:** [Marquee Skill](../skills/marquee/SKILL.md) version `0.1.0-production-test-candidate`
- **Specifications:** [Marquee Outlet orchestration](../specifications/marquee-outlet-orchestration.md), `OUTLET-012`; [Marquee graph creation](../specifications/marquee-graph-creation.md), `GRAPH-008` and `GRAPH-009`
- **Skill host product:** Cowork production AI surface; exact product context recorded at execution
- **Skill instructions:** `Maintain Outlet Guidance`; `Write Career Knowledge Artifacts`
- **Last updated:** 2026-09-11

## Host compatibility profile

- **Required host behavior:** Load Marquee, inspect and update Outlet guidance in the confirmed graph across repeated uses, and expose changes for user review and independent comparison.
- **Capability hypothesis:** Cowork may support durable guidance reuse through OneDrive Markdown, but discovery across summons and measurable improvement from retained guidance remain unverified. The host must not silently convert one run into universal instructions.
- **Focused capability checks:** Read a synthetic guidance artifact in a fresh summons; propose one transparent update; preserve an explicitly marked unknown; independently inspect the changed file. The full repeated-use value claim still requires the complete experience.
- **Another host:** Identify its product and repeat the read/update check. Compare guidance discovery, mutation fidelity, and provenance handling before predicting compatibility.

## Success decision

Determine whether Outlet guidance accurately captures what proved useful and materially improves later assistance. Unsupported assumptions, private facts in reusable instructions, or activity-ledger content fail the plan; other behaviors must average at least 2.

## Behavior traceability and grading

| Behavior | Charter or Specification definition | Responsible Skill instruction | Grade of success |
| --- | --- | --- | --- |
| Capture proven process | Charter Outlets; `OUTLET-012` | `Maintain Outlet Guidance`, paragraphs 1-2 | `2`: reflects observed effective process and conditions; `1`: useful but incomplete; `0`: invented or inaccurate. |
| Capture useful detail | Charter repeatable assistance | `Maintain Outlet Guidance`, guidance list | `2`: audience, sources, questions, voice, approach, and limits are usefully selective; `1`: generic; `0`: not reusable. |
| Distinguish knowledge status | Charter user control; `GRAPH-009` | `Maintain Outlet Guidance`, status paragraph | `2`: proven guidance, preference, condition, and unknown are distinct; `1`: minor ambiguity; `0`: assumptions presented as rules. |
| Protect portability and privacy | Charter distributable beta | `Maintain Outlet Guidance`, status paragraph | `2`: reusable without private facts or activity tracking; `0`: embeds private content or ledger entries. |
| Improve repeated use | Charter success signals | `Maintain Outlet Guidance`, final paragraph | `2`: later assistance is more accurate or efficient without rigidity; `1`: no measurable change; `0`: guidance degrades the experience. |

## Test experience

Complete an Outlet once, inspect and rate the resulting guidance, then repeat the same Outlet with meaningful variation. Compare planning accuracy, questions, effort, and output quality. Introduce one outdated or unsupported guidance statement and verify Marquee proposes a transparent correction.

## Evidence and stop conditions

Record privacy-minimized guidance before and after each use, factual basis, user usefulness rating, repeated-use differences, and corrections. Stop if guidance exposes private facts, records activity history, silently rewrites user content, or causes an unauthorized action.
