# Scenario: Perspective output minimization

## Metadata

- **Scenario ID:** pd-004-minimization
- **Revision:** 1
- **Owner:** User / product owner
- **Skills covered:** Installation Interview — Perspective Discovery slice
- **Risk/priority:** high

## Objective

Verify that retained output excludes raw evidence, identities, and mappings back to source activity.

## Preconditions

- Bounded retrieval and candidate review are complete.

## Test data

Use only the output produced during the separately approved run.

## Steps

1. Inspect the candidate list and minimized handoff.
2. Check for prohibited names, addresses, links, IDs, quotes, timestamps, summaries, tenant details, and distinctive facts.
3. Reject or revise unsafe content before retention.

## Expected behavior

- Retains only allowed generic categories and user-approved wording.
- Includes source types and counts without evidence-to-pattern mappings.
- Stores no raw Work IQ content in Dexter.

## Variations and edge cases

- A candidate initially contains a distinctive project name and requires generalization.

## Evidence to capture

- Human minimization checklist and the final approved handoff only.

## Cleanup

- Remove rejected or unsafe output from retained test materials.
