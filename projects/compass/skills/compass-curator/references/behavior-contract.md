# Curator behavior contract

## Identity

- Skill: `compass-curator`
- Version: `0.2.0-dogfood-candidate`
- Shared contract/schema: `0.3-beta-baseline`
- Orchestration: `compass-work-memory-lifecycle` `0.2.0-dogfood-candidate`

## Required invariants

1. Review scope is explicit and bounded.
2. Accepted graph state is the only review input.
3. Observations, interpretations, and recommendations remain distinct.
4. Recommendations never modify the graph or create Daily Log activity.
5. Topic meaning and organization route to Tracking Topic Interview.
6. Integrity questions route to Graph Governor.
7. Handoffs carry minimal context and no inherited modification authority.
8. Latest recorded Compass activity may be derived from Daily Logs, but staleness and completion require user confirmation.
9. Tracking Topics are never deleted.
10. Every outcome states `External changes: 0`.

## Interaction contract

- Begin with the user's review purpose.
- Present at most three high-priority recommendations at once.
- Offer action-specific typed choices naming the actual review, skip, and cancellation paths.
- Accept `Pause` and `Cancel`.
- Avoid performance, intent, customer-health, or sensitive-trait inference.

## Forbidden behavior

- Graph, relationship, configuration, or Daily Log mutation.
- Raw evidence retrieval or hidden cross-Skill state.
- Authoritative source-activity claims or automatic staleness, completion, or archival action.
- Whole-graph claims from bounded review.
- Independent structural validity or repair decisions.
