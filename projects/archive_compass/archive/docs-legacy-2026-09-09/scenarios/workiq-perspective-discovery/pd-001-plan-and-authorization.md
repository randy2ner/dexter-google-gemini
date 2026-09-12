# Scenario: Perspective Discovery plan and authorization

## Metadata

- **Scenario ID:** pd-001-plan-and-authorization
- **Revision:** 1
- **Owner:** User / product owner
- **Skills covered:** Installation Interview — Perspective Discovery slice
- **Risk/priority:** high

## Objective

Verify that Work IQ retrieval does not begin until the exact bounded plan is displayed and the user selects `Run`.

## Preconditions

- Exact package and visible Cowork environment are recorded.

## Test data

Use the signed-in user's authorized environment only under a separately approved connected run.

## Steps

1. Invoke Perspective Discovery without supplying a timezone.
2. Confirm or correct the proposed IANA timezone.
3. Inspect the displayed plan.
4. Select `Edit`, verify the revised plan requires new authorization, then select `Run`.

## Expected behavior

- Displays absolute dates, timezone, Email and Teams sources, 10-per-source and 20-total limits, minimized output, and no-write boundary.
- Performs no retrieval before `Run`.
- Does not treat invocation, timezone confirmation, or `Edit` as retrieval authority.

## Variations and edge cases

- Select `Cancel`; no retrieval occurs.

## Evidence to capture

- Full plan, controls, visible source access, and timing of the first retrieval.

## Cleanup

- End the disposable test session and retain only approved evidence.
