# Decision: Accept HPI Topic narrative and review metadata

- **Date:** 2026-09-08
- **Status:** accepted
- **Deciders:** User / product owner
- **Related sample:** [HPI narrative object samples](../test-results/2026-09-08-hpi-narrative-samples/README.md)

## Context

Tracking Topics are intended to preserve detailed stories from the user's career, not only short organizational labels. A resolved High Profile Incident demonstrated the need to retain troubleshooting logic, disproved hypotheses, evidence discipline, resolution, contribution, and transferable lessons. Content may come from user-offered material or an explicitly authorized evidence review, but absence of detailed content must not block ordinary Topic management.

The user also needs solved HPIs to appear as explicit Curator review bullets. Unknown plugin frontmatter would be preserved but would not create reliable Compass behavior.

## Decision

1. Tracking Topic Markdown may contain an optional detailed user-approved narrative.
2. Daily Scan may collect content only when offered or included in its authorized retrieval purpose and may produce only a minimized candidate handoff.
3. Tracking Topic Interview owns durable narrative composition and revision.
4. Topic `tags` is an optional unique lowercase kebab-case string list. `hpi` means High Profile Incident and `solved` identifies a resolved outcome.
5. Topic `reviewBullet` is an optional boolean. Curator surfaces each in-scope `true` Topic once as a distinct review bullet.
6. `tags`, `reviewBullet`, `status`, `success`, and `attentionState` remain independent and require their own authority.
7. Graph Governor validates frontmatter shape, exact authority, expected effects, and preservation. It does not judge whether narrative claims are complete or true.
8. Follow-up ideas may be retained in the archived narrative while outside the Topic's scope. Compass does not suggest, ask about, create, or hand off another Topic unless the user initiates it.
9. The HPI sample uses fictional Person aliases and a synthetic source Conversation ID; no Work IQ observation or connected write is claimed.

## Alternatives considered

- **Body-only review note:** Rejected because Curator could not identify it deterministically without interpreting prose.
- **Unknown plugin tags:** Rejected because Compass would preserve but not understand them.
- **Store a narrative string in YAML:** Rejected because Markdown is more portable and readable for a detailed career story.
- **Let Daily Scan update the Topic directly:** Rejected because evidence retrieval does not transfer authority over Topic meaning.
- **Automatically open follow-up Topics:** Rejected because the user explicitly reserves initiation of future work.

## Consequences

- Shared contracts, graph schema, four Skill responsibilities, active Skill sources, lifecycle orchestration, and tests advance together.
- Installation remains unchanged because the optional fields are introduced through Tracking Topic Interview after foundational setup.
- Prior packages, fixtures, and completed evidence remain historical and are not rewritten.
- Runtime confidence remains unchanged until the exact candidate packages complete the mediated experience.
