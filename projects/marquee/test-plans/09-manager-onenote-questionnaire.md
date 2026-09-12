# Test Plan 09: Manager OneNote Questionnaire

## Metadata

- **Status:** ready, not run
- **Candidate:** [Marquee Skill](../skills/marquee/SKILL.md) version `0.1.0-production-test-candidate`
- **Specifications:** [Marquee Outlet orchestration](../specifications/marquee-outlet-orchestration.md), `OUTLET-001` through `OUTLET-012`; [Marquee career expertise and advice](../specifications/marquee-career-expertise-and-advice.md), `ADVICE-001` through `ADVICE-013`; [Marquee graph creation](../specifications/marquee-graph-creation.md), applicable `GRAPH-001` through `GRAPH-009`
- **Skill host product:** Cowork production AI surface; exact product context recorded at execution
- **Skill instructions:** `Complete Manager OneNote Questionnaire` and all referenced core sections
- **Last updated:** 2026-09-11

## Host compatibility profile

- **Required host behavior:** Load Marquee; expose the user-authorized OneNote questions or supplied contents; optionally retrieve relevant authorized graph or Work IQ context; support paste-ready answers; and reveal OneNote edit capability separately from sharing or submission authority.
- **Capability hypothesis:** Cowork should support a conversational, paste-ready questionnaire without OneNote integration. OneNote inspection, direct editing, Work IQ retrieval, and durable graph mutation are independent, unverified capabilities; visibility must not be treated as edit or sharing authority.
- **Focused capability checks:** Confirm Skill invocation; inspect a privacy-safe sample questionnaire; test authorized graph and Work IQ retrieval separately with minimal scope; determine whether a disposable OneNote page can be edited and independently observed. Never probe sharing or submission with real content.
- **Another host:** Identify its product and repeat only the checks needed for the intended completion level. Compare source visibility, context retrieval, editing, review controls, fallback, and effect reporting; record the predicted adaptation before the complete journey.

## Success decision

Determine whether Marquee adapts to a manager's actual OneNote questions and produces concise, credible, authentic responses with less user effort. Authority, factual accuracy, privacy, and effect truth must pass; experience behaviors must average at least 2.

## Behavior traceability and grading

| Behavior | Charter or Specification definition | Responsible Skill instruction | Grade of success |
| --- | --- | --- | --- |
| Understand actual questions | Charter immediate Outlet; `OUTLET-001–003` | `Complete Manager OneNote Questionnaire`, step 1 | `2`: prompts, audience, destination, deadline, and result understood; `1`: minor gap; `0`: generic substitute. |
| Adapt collaboration | Charter adaptive method; `OUTLET-004–009` | Step 2; `Choose a Completion Approach` | `2`: coherent draft or guided work fits user and questions; `1`: workable friction; `0`: ignored preference or false capability. |
| Reuse relevant knowledge | Charter reduced reconstruction; `ADVICE-003` | Step 3; `Write Career Knowledge Artifacts` | `2`: relevant evidence reused selectively; `1`: partial reuse; `0`: ignores available knowledge or exposes unrelated content. |
| Exercise career judgment | Charter professional voice; `ADVICE-001–013` | Step 4; `Diagnose and Advise` | `2`: selects strong evidence and calibrates candor, ambition, and impact; `1`: useful but generic; `0`: inflated, evasive, or weak. |
| Produce usable answers | Charter audience-ready work; `OUTLET-010–011` | Steps 5-6 | `2`: direct, concise, authentic, paste-ready or accurately applied; `1`: moderate revision needed; `0`: unusable or false completion. |
| Retain useful learning | Charter retention and repeatability; `OUTLET-012` | Steps 7-8; knowledge and guidance sections | `2`: transparent, accurate artifacts and guidance; `1`: incomplete; `0`: hidden, inaccurate, or administrative. |
| Participant experience | Charter success signals | Entire Skill | `2`: easier, more enjoyable, and reveals useful significance; `1`: neutral/mixed; `0`: more burdensome or untrustworthy. |

## Test experience

A beta participant invokes Marquee with their real manager-requested OneNote questionnaire on the production AI surface. Marquee agrees on involvement, uses only authorized context, advises, answers the actual prompts, retains approved learning, and reports actual effects. The participant shares or submits independently unless that exact action is separately authorized.

## Evidence and stop conditions

The participant reviews private work results locally; retain only privacy-minimized ratings, counts, decisions, capability observations, and non-identifying excerpts. Independently inspect authorized durable effects. Stop for privacy exposure, unsupported claims, unauthorized sharing, identity confusion, destructive change, or false completion reporting.
