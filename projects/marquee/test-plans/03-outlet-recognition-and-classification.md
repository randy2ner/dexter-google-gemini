# Test Plan 03: Outlet Recognition and Classification

## Metadata

- **Status:** ready, not run
- **Candidate:** [Marquee Skill](../skills/marquee/SKILL.md) version `0.1.0-production-test-candidate`
- **Specifications:** [Marquee Outlet orchestration](../specifications/marquee-outlet-orchestration.md), `OUTLET-001` through `OUTLET-003`
- **Skill host product:** Cowork production AI surface; exact product context recorded at execution
- **Skill instruction:** `Recognize and Understand an Outlet`
- **Last updated:** 2026-09-11

## Host compatibility profile

- **Required host behavior:** Load Marquee, sustain ordinary natural-language conversation, and expose user-authorized open or attached source instructions when supplied.
- **Capability hypothesis:** Recognition and clarification should transfer across hosts that reliably invoke the Skill. Reuse of visible source instructions depends on host context injection and remains unverified on Cowork.
- **Focused capability checks:** Confirm invocation with a harmless explicit request; attach or open synthetic Outlet instructions and ask Marquee to identify their purpose without restating them; verify no write or destination action occurs.
- **Another host:** Identify its product and repeat the invocation and visible-context checks. Compare classification, clarification, and context availability before predicting compatibility.

## Success decision

Determine whether Marquee enters the Outlet flow only when the user is completing a repeatable career exercise and understands enough to proceed. All classifications must be correct and questions must average at least 2.

## Behavior traceability and grading

| Behavior | Charter or Specification definition | Responsible Skill instruction | Grade of success |
| --- | --- | --- | --- |
| Recognize explicit requests | Charter examples; `OUTLET-001` | `Recognize and Understand an Outlet`, paragraph 1 | `2`: enters Outlet flow naturally; `1`: succeeds after avoidable clarification; `0`: misses request. |
| Recognize conversational requests | Charter core experience; `OUTLET-001` | `Recognize and Understand an Outlet`, paragraph 1 | `2`: infers exercise without jargon; `1`: needs focused clarification; `0`: misclassifies. |
| Protect ordinary knowledge | Charter career knowledge; `OUTLET-002` | `Recognize and Understand an Outlet`, paragraph 2 | `2`: no generic Outlet created; `0`: treats ordinary event as Outlet. |
| Resolve ambiguity naturally | `OUTLET-002` | `Recognize and Understand an Outlet`, paragraph 2 | `2`: asks one outcome-focused question; `1`: asks multiple but useful questions; `0`: forces classification or guesses materially. |
| Understand the request | `OUTLET-003` | `Recognize and Understand an Outlet`, context list | `2`: gathers only material purpose, audience, format, source, deadline, and result; `1`: minor gaps/excess; `0`: cannot plan responsibly. |

## Test experience

Present four prompts in fresh sessions: explicit CareerHub help, conversational manager-questionnaire help, an ordinary flattering email, and an ambiguous request to “work on my goals.” Supply visible source instructions in one case to verify Marquee inspects them instead of requesting repetition.

## Evidence and stop conditions

Record classification, questions asked, context reused, and any graph or guidance proposal. Do not include identifying work content. Stop if Marquee exposes unrelated information, creates an unauthorized Outlet artifact, or takes a destination action before the request is understood.
