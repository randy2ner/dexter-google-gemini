# Scenario: Topic archival success lifecycle

## Metadata

- **Scenario ID:** ctas-v2-001
- **Revision:** 2026-09-06
- **Owner:** User / product owner
- **Skills covered:** compass-tracking-topic-interview; graph-governor
- **Risk/priority:** high

## Objective

Evaluate explicit archival success capture, schema enforcement, merge-source handling, and removal of success during reactivation.

## Preconditions

- Use only a disposable copy of the fictional fixture.
- Use the exact candidate versions named in the test plan.
- Behavioral execution has separate product-owner authorization.

## Test data

Use [the Topic archival-success fixture](../../test-data/compass-topic-archival-success-v2/README.md).

## Steps

1. Validate the four positive fixture Topics.
2. Ask to archive the active Topic without stating whether it succeeded.
3. Confirm that Topic Interview asks the user for a success choice before presenting an exact preview.
4. Approve `success: false`, validate the handoff, apply only if execution is authorized, and verify the archived state.
5. Ask to reactivate that Topic and verify the preview removes `success` rather than setting it to null.
6. In disposable variants, evaluate archived missing, archived null, archived string, active true, and active false values.
7. Prepare a merge with two source Topics and verify the proposal requires a separate explicit boolean success value for each archived source.

## Expected behavior

- Archived Topics accept only native YAML booleans `true` and `false`.
- Active Topics accept absent or null success in static state.
- Reactivation removes the field and post-write verification requires absence.
- No Skill infers success from Topic wording, staleness, recency, completion, or merge.
- Invalid or unapproved combinations do not produce a valid write decision.

## Variations and edge cases

- User changes the success answer after preview; prior approval is invalidated.
- User cancels at the success question; no graph effect occurs.
- One merge source is successful and another unsuccessful; both values remain independently visible.

## Evidence to capture

- Exact prompts, user answers, previews, handoffs, validation decisions, effect reports, and resulting YAML.
- Package versions, fixture hashes, environment, and any limitations.

## Cleanup

- Restore or discard the disposable copy. Do not mutate a personal graph.