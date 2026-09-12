# Test Plan 06: Unconfirmed Knowledge Follow-up

## Metadata

- **Status:** ready, not run
- **Candidate:** [Marquee Skill](../skills/marquee/SKILL.md) version `0.1.0-production-test-candidate`
- **Specifications:** [Marquee graph creation](../specifications/marquee-graph-creation.md), `GRAPH-007` through `GRAPH-009`; [Marquee Outlet orchestration](../specifications/marquee-outlet-orchestration.md), failure and cancellation behavior
- **Skill host product:** Cowork production AI surface; exact product context recorded at execution
- **Skill instructions:** `Write Career Knowledge Artifacts`; `Resume Marquee Knowledge`
- **Last updated:** 2026-09-11

## Host compatibility profile

- **Required host behavior:** Load Marquee in separate summons, rediscover relevant graph artifacts, read confirmation state, and apply an approved correction without losing unrelated content.
- **Capability hypothesis:** Durable continuity can come from inspectable graph files rather than conversation memory, but Cowork's ability to locate and update the relevant artifact on a later summons remains unverified.
- **Focused capability checks:** Create a synthetic `unconfirmed` artifact in an approved disposable graph; start a fresh summons; request a related task; verify retrieval, then approve one correction and independently inspect the file.
- **Another host:** Identify its product and repeat the cross-summons read/update check. Compare durable context discovery, mutation fidelity, and handling of unrelated pending items before predicting compatibility.

## Success decision

Determine whether interrupted knowledge remains visibly unconfirmed and receives a focused follow-up at Marquee's next summons. Unconfirmed information must never be treated as accepted; all behaviors must score 2.

## Behavior traceability and grading

| Behavior | Charter or Specification definition | Responsible Skill instruction | Grade of success |
| --- | --- | --- | --- |
| Mark interrupted knowledge | Charter retention contract, item 6 | `Write Career Knowledge Artifacts`, confirmation procedure | `2`: artifact remains visibly `unconfirmed`; `0`: absent status or false confirmation. |
| Discover on next summons | Charter confirmed/unconfirmed knowledge | `Resume Marquee Knowledge`, opening | `2`: relevant pending item found accurately; `0`: missed or wrong item. |
| Request resolution | Charter user correction authority | `Resume Marquee Knowledge`, paragraph 2 | `2`: focused confirm, correct, or reject request; `0`: silent acceptance or coercion. |
| Avoid administrative takeover | Charter natural conversation | `Resume Marquee Knowledge`, paragraph 2 | `2`: relevant follow-up is brief and unrelated items defer; `1`: cumbersome; `0`: current request blocked unnecessarily. |
| Apply disposition truthfully | Charter retention contract | `Resume Marquee Knowledge`, paragraph 3 | `2`: chosen confirmation, correction, or rejection is accurately reflected and reported; `0`: wrong or unauthorized mutation. |

## Test experience

Create a privacy-safe career artifact and end the interaction before confirming Marquee's interpretation. Independently verify `confirmation: unconfirmed`. Summon Marquee for a related request, choose correction, and inspect the updated file. Repeat with an unrelated summons to test non-disruptive deferral.

## Evidence and stop conditions

Record both summons, the pre-follow-up artifact, Marquee's request, user disposition, final artifact, and exact change report. Stop on false confirmation, unauthorized deletion, loss of user-authored content, or disclosure of unrelated graph knowledge.
