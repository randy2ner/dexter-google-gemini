# Scenario: Topic attention-state lifecycle

## Metadata

- **Scenario ID:** ctas-v2-002
- **Revision:** 2026-09-06
- **Owner:** User / product owner
- **Skills covered:** compass-installation-interview; compass-daily-scan; compass-tracking-topic-interview; compass-curator; graph-governor
- **Risk/priority:** high

## Objective

Evaluate explicit Topic attention-state creation, changes, preservation, non-inference, validation, and lifecycle interaction.

## Preconditions

- Use only a disposable copy of the fictional fixture.
- Use the exact candidate versions in the test plan.
- Obtain separate product-owner authorization before behavioral execution.

## Test data

Use [the Topic attention-state fixture](../../test-data/compass-topic-attention-state-v2/README.md).

## Steps

1. Validate all four positive fixture Topics.
2. During Installation, propose a foundational Topic and verify the user must choose action, waiting, or observing without a default.
3. Through Topic Interview, change an action Topic to waiting and verify the exact before/after preview and Daily Log effect.
4. Begin another change, then cancel; verify no graph effect.
5. Present Conversation activity related to an observing Topic in Daily Scan; verify the accepted state may be shown but is not changed or approved with the Conversation.
6. Ask Curator to review attention; verify it reads accepted state and routes a selected change without deriving a replacement.
7. In disposable variants, validate missing, null, empty, `blocked`, `active`, and another unknown value.
8. Archive a waiting Topic and verify the value is retained independently of boolean success.
9. Reactivate the archived Topic and verify success is removed while attention state is explicitly confirmed or changed.

## Expected behavior

- Only `action`, `waiting`, and `observing` are valid.
- Creation and changes require exact user authority.
- Evidence, participation, recency, alignment, lifecycle, and success never silently determine attention state.
- Archival retains the value; reactivation confirms or changes it.
- Cancellation and invalid states produce no unauthorized graph effect.

## Variations and edge cases

- A user says “blocked”; Topic Interview clarifies whether this means waiting and does not store `blocked`.
- A user has an action while also waiting on someone; Topic Interview asks which state best represents current attention rather than storing multiple values.
- An observing Topic has recent activity; Daily Scan does not convert it to action.

## Evidence to capture

- Exact prompts, answers, proposals, handoffs, Governor decisions, effect reports, resulting YAML, package hashes, and fixture hashes.

## Cleanup

- Restore or discard the disposable copy. Do not mutate a personal graph.