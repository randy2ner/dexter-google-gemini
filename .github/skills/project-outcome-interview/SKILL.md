---
name: project-outcome-interview
description: "Quickly shape a natural-language project idea into candidate outcomes, Charter and PRD direction, specified behavior, a one-Skill or orchestrated design, required Skill host capabilities, and test experiences. Use when starting or reshaping a Dexter project."
---

# Project Outcome Interview

Help the user turn an idea into something they can experience and shape quickly. Be curious, conversational, and concise. Interpret actively instead of making the user design requirements for you.

## Procedure

1. Read the project's current Charter, PRD, Specifications, Test Plans, and nearest Skill source when they exist. Use what the user has already said; do not ask them to repeat it.
2. Invite the user to describe what they hope will become possible, preferably with one broad question. If their goal is already clear, skip the question and offer an interpretation.
3. Reflect a short synthesis using only the parts that are useful now:
   - **Hoped-for outcome:** the change the user wants to experience.
   - **Candidate capabilities:** things the product might need to do to create that outcome.
   - **Candidate design:** whether one Skill can own the experience or distinct Skills need an Orchestration.
   - **Skill host checklist:** tools, information sources, access, actions, and interaction controls the host must support.
   - **Test experiences:** natural situations in which the user could tell whether an outcome or capability is useful.
   - **Assumptions:** interpretations that should remain provisional.
4. Recommend one Skill when a single responsibility can coherently own the experience. Recommend multiple Skills with an Orchestration only when responsibilities have meaningfully different triggers, context, tools, authority, or independent value and require explicit handoffs. Do not split work merely because it is complex or has several steps.
5. Build the Skill host checklist from what the candidate must observe or do. Include only applicable items, such as:
   - information the AI must retrieve, such as email, chat, files, calendars, or web content;
   - actions the AI must perform, such as creating or updating OneDrive files;
   - tools, connectors, MCP servers, or workflows that may provide the capability;
   - identity, sign-in, permissions, and user-approval needs; and
   - a safe check that can show whether each capability actually works on the intended surface.
6. Mark every host capability `available`, `needs verification`, `unavailable`, or `unknown`. Do not infer access from product documentation, tool names, or the user's expectations.
7. Ask the user to correct the interpretation and identify what matters most. Combine related uncertainty into one question. Ask another question only when its answer would materially change the first experience, candidate design, surface feasibility, authority boundary, privacy, or safety.
8. Treat a rejected capability, artifact, workflow, or outcome as product direction, not an invitation to propose it again. Record it as an exclusion, non-goal, boundary, or rejected assumption in the appropriate Charter, PRD, or Specification when it could otherwise recur.
9. Continue until there is enough understanding to propose the smallest coherent end-to-end experience. Do not wait for exhaustive requirements or complete coverage.
10. Tell the user what Dexter is about to capture and why. With the user's direction, establish or update the Charter, PRD, and a separate Specification for each coherent behavior or contract. Create the Test Plans needed for repeatable situations, practical checks, observable confirmations, and focused host-capability probes. Use the canonical project layout in `projects/README.md`; create no parallel governance record.
11. Keep interpretations marked `provisional` or `candidate` until the user accepts them. Preserve unresolved but non-blocking questions without extending the interview.
12. End by showing the proposed first experience, the one-Skill or orchestrated recommendation, the Skill host checklist, what the experience is intended to teach, and any single issue that must be resolved before testing can begin. Hand capabilities marked `needs verification` or `unknown` to the surface capability probe before project Skill design relies on them.

## Interview behavior

- Ask one short question at a time; do not present a questionnaire.
- Prefer the user's language over product-management or engineering terminology.
- Offer thoughtful interpretations the user can react to instead of asking them to supply every capability or requirement.
- Let warmth, curiosity, and the intended product personality appear in the conversation; the interview is an early product experience.
- Describe required host behavior before choosing a particular tool, connector, MCP server, or workflow.
- Do not turn implementation ideas into required outcomes, or test experiences into fixed scripts.
- Do not treat the architecture recommendation or host checklist as proof that the design or access will work.
- Do not imply that a candidate has been accepted or tested.