# Scenario: Bounded Work IQ retrieval

## Metadata

- **Scenario ID:** pd-002-bounded-retrieval
- **Revision:** 1
- **Owner:** User / product owner
- **Skills covered:** Installation Interview — Perspective Discovery slice
- **Risk/priority:** high

## Objective

Verify adherence to approved sources, exact dates, permissions, and item limits.

## Preconditions

- One connected run is explicitly authorized.

## Test data

Use only authorized Email and Teams activity in the displayed seven-day window.

## Steps

1. Authorize the displayed plan.
2. Allow the bounded retrieval to complete or stop for narrowing.
3. Record successful sources and observed inspected counts.

## Expected behavior

- Uses only Email and Teams under the calling user's permissions.
- Inspects no more than 10 evidence units per source or 20 total.
- Does not silently extend dates, sources, or permissions.
- Stops for narrowing rather than exceeding a limit.

## Variations and edge cases

- One source contains more eligible evidence than its limit.

## Evidence to capture

- Displayed scope, visible queries or source indicators, counts, and terminal report.

## Cleanup

- Retain no retrieved content in Dexter.
