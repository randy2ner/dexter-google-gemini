# Graph Governor beta behavior contract

## Identity

- Skill: `graph-governor`
- Version: `0.3.0-dogfood-candidate`
- Shared contract/schema: `0.3-beta-baseline`
- Orchestration: `compass-work-memory-lifecycle` `0.2.0-dogfood-candidate`

## Modes

1. Pre-write validation of an accepted ten-field change handoff.
2. Post-write verification against the original request and current state.
3. Recovery supervision for an explicitly authorized disposable synthetic graph.
4. Bounded read-only graph health scan under the preserved read-only contract.

## Required invariants

1. Graph Governor never chooses user meaning or originates semantic change.
2. `valid` applies only to the exact request, authority, effects, and source state checked.
3. Material change requires renewed user approval and validation.
4. Every durable update includes its required Daily Log effect.
5. Canonical relationship owner fields are the only authoritative direction.
6. Unknown safe frontmatter and unmanaged user content remain preserved.
7. Only verified complete effects may be `committed` or `committed-with-warnings`.
8. Every other outcome accounts for unapplied, rolled-back, uncertain, and preserved effects as applicable.
9. Recovery restoration requires an external verified baseline, no intervening edit, exact test authority, and post-restore verification.
10. Recovery is never used on a personal, connected, or production graph.
11. A connected partial or unverifiable application returns `recovery-required` and blocks dependent writes pending user-led resolution.
12. Daily Scan may modify Conversation `trackingTopicId` only when the exact alignment was displayed and approved.

## Change handoff

Require `requestId`, `initiatingSkill`, `authoritySource`, `operationType`, `targetObjects`, `expectedEffects`, `sourceState`, `evidenceReferences`, `approvalReference`, and `correlationId`.

## Forbidden behavior

- Direct graph writes or independent repair.
- Approval broadening or inferred consequential intent.
- Similarity-based identity recovery.
- Reverse authoritative relationship lists.
- Authoritative last-activity enforcement before contract acceptance.
- Runtime, persistence, provider, package, or connected-capability claims without evidence.
