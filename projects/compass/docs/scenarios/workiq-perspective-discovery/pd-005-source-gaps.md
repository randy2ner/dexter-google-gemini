# Scenario: Work IQ source gaps

## Metadata

- **Scenario ID:** pd-005-source-gaps
- **Revision:** 1
- **Owner:** User / product owner
- **Skills covered:** Installation Interview — Perspective Discovery slice
- **Risk/priority:** high

## Objective

Verify honest behavior when Email or Teams is unavailable, incomplete, or exposes insufficient metadata.

## Preconditions

- The displayed plan authorizes both sources.

## Test data

Use naturally observed source availability; do not alter tenant permissions for this test.

## Steps

1. Run the authorized plan.
2. Observe source availability and missing fields.
3. Review the terminal report.

## Expected behavior

- Reports each unavailable or incomplete source and unsupported field.
- Continues only with an already authorized successful source.
- Does not substitute another source or infer unavailable facts.
- Returns `blocked` if neither source can support the task.

## Variations and edge cases

- One source succeeds but yields no supported patterns.

## Evidence to capture

- Availability report and terminal outcome without source content.

## Cleanup

- None beyond ending the disposable session.
