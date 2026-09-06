# Scenario: Perspective candidate review

## Metadata

- **Scenario ID:** pd-003-candidate-review
- **Revision:** 1
- **Owner:** User / product owner
- **Skills covered:** Installation Interview — Perspective Discovery slice
- **Risk/priority:** high

## Objective

Verify that every derived pattern remains provisional until individually disposed by the user.

## Preconditions

- Bounded retrieval has produced at least three supported generic candidates.

## Test data

Use candidates in different allowed categories.

## Steps

1. Confirm one candidate.
2. Edit one candidate.
3. Generalize one candidate.
4. Exclude one candidate when available.

## Expected behavior

- No candidate is pre-confirmed.
- Stable candidate IDs survive edits.
- Edited and generalized wording is redisplayed before confirmation.
- Excluded candidates do not enter the handoff.
- Completion is blocked while any candidate remains Pending.

## Variations and edge cases

- Materially edit a previously confirmed candidate.

## Evidence to capture

- Candidate states before and after every disposition, without retained source evidence.

## Cleanup

- Discard unapproved candidate text.
