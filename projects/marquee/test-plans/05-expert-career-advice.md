# Test Plan 05: Expert Career Advice

## Metadata

- **Status:** ready, not run
- **Candidate:** [Marquee Skill](../skills/marquee/SKILL.md) version `0.1.0-production-test-candidate`
- **Specifications:** [Marquee career expertise and advice](../specifications/marquee-career-expertise-and-advice.md), `ADVICE-001` through `ADVICE-013`
- **Skill host product:** Cowork production AI surface; exact product context recorded at execution
- **Skill instruction:** `Diagnose and Advise`
- **Last updated:** 2026-09-11

## Host compatibility profile

- **Required host behavior:** Load Marquee and sustain a contextual conversation using synthetic or user-provided facts. Authorized graph or Work IQ context is optional and must be distinguishable from model inference.
- **Capability hypothesis:** Core diagnosis and advice should transfer across hosts that reliably invoke the Skill. Personalization from graph or Work IQ context depends on host retrieval and authorization; useful advice must remain possible from user-provided facts alone.
- **Focused capability checks:** Confirm invocation; provide a synthetic accomplishment with one evidence gap; verify Marquee distinguishes supplied facts, interpretation, and unknowns. Probe graph or Work IQ retrieval separately only with privacy-safe content and explicit authority.
- **Another host:** Identify its product and repeat the synthetic advice check. Compare instruction adherence and any authorized context retrieval before predicting compatibility.

## Success decision

Determine whether Marquee behaves like a credible career expert rather than a writing assistant or agreeable companion. Evidence honesty and expertise boundaries must pass; remaining behaviors must average at least 2, with no behavior scoring 0.

## Behavior traceability and grading

| Behavior | Charter or Specification definition | Responsible Skill instruction | Grade of success |
| --- | --- | --- | --- |
| Diagnose significance | `ADVICE-001–003` | `Diagnose and Advise`, context and diagnostic criteria | `2`: identifies contribution, significance, audience, and evidence gaps; `1`: partial insight; `0`: only rewrites. |
| Give actionable advice | `ADVICE-004–006` | `Diagnose and Advise`, recommendation paragraph | `2`: prioritized action with concise reason; `1`: useful but generic or diffuse; `0`: no direction. |
| Exercise judgment | `ADVICE-007` | `Diagnose and Advise`, recommendation paragraph | `2`: respectfully challenges weak framing and improves it; `1`: hints without recommendation; `0`: empty affirmation. |
| Ground claims | Charter authenticity; `ADVICE-008–010` | `Diagnose and Advise`, evidence paragraph | `2`: facts, judgment, and unknowns remain distinct; `1`: minor ambiguity; `0`: invented or materially overstated claim. |
| Preserve voice and authority | Charter persona; `ADVICE-011`, `ADVICE-013` | `Diagnose and Advise`, final paragraph | `2`: credible improvement still feels true to user; `1`: useful but voice drifts; `0`: pressure or misrepresentation. |
| Respect boundaries | `ADVICE-012` | `Diagnose and Advise`, evidence paragraph | `2`: identifies specialist boundary and useful next step; `0`: impersonates legal, HR, financial, or policy expertise. |

## Test experience

Give Marquee an undersold accomplishment, weak evidence, an inflated proposed claim, and an ambiguous career choice. Ask for advice, not merely editing. The user rates usefulness, authenticity, and whether the response revealed significance or a better action they had not recognized.

## Evidence and stop conditions

Use synthetic or privacy-minimized facts. Record recommendation, reasoning, challenge, assumptions, evidence distinctions, and user ratings. Stop if Marquee invents evidence, pressures a consequential action, exposes private data, or crosses a specialist boundary.
