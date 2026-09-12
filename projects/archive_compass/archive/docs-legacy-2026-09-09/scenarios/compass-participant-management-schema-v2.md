# Scenario: Compass participant management schema version 2

## Metadata

- **Scenario ID:** CPM-V2-001
- **Status:** planned; execution not authorized
- **Owner:** User / product owner
- **Skills covered:** Compass Installation Interview, Compass Daily Scan, Compass Tracking Topic Interview, Graph Governor
- **Requirement coverage:** `PR-PART-001`, `PR-TOPIC-001`, `PR-PARK-001`, `PR-GRAPH-001`, `PR-SAFE-001`, `PR-TRUTH-001`
- **Test plan:** [Participant-management test plan](../test-plans/2026-09-06-participant-management-test-plan.md)

## Purpose

Determine whether the schema-v2 candidate enforces intentional, complete, and persistent participant relationships without treating passive visibility as participation or silently reversing Topic Interview decisions.

## Preconditions

- Use only a separately versioned fictional schema-v2 fixture.
- Do not access Microsoft 365 or modify a personal Compass graph.
- Graph Governor candidate and initiating Skill versions are exact and recorded.

## Checks

1. Accept initial and later message authors as Conversation participants.
2. Exclude email recipients and chat-roster members who neither author nor receive an accepted authored-content mention.
3. Accept a complete-name authored-content mention only after user identity confirmation.
4. Block a first-name-only mention until the user supplies a last name and confirms existing-or-new Person binding.
5. Reject a Person missing either `firstName` or `lastName`.
6. Accept `trackingTopicId: parking-lot` without resolving a Topic object.
7. Reject missing, null, empty, or dangling `trackingTopicId`.
8. Funnel accepted Conversation participants to an aligned Topic unless excluded.
9. Preserve Topic participants after Conversation staleness, deletion, Parking Lot movement, or reassignment.
10. Move a removed Person from Topic `participantIds` to `excludedParticipantIds` and log `person-unlinked`.
11. Confirm later automatic funneling does not re-add the excluded Person.
12. Explicitly re-add the Person, remove the exclusion, and log `person-linked`.
13. Reject duplicate IDs, wrong target types, and overlap between Topic participant and exclusion lists.
14. Verify Person objects contain no reverse Conversation or Topic lists.

## Expected result

Each positive and negative check produces the contract-defined validation decision and no undeclared effect. This expected result is a test oracle, not observed evidence.

## Stop conditions

- Fixture identity or candidate version is uncertain.
- Any operation would access connected work data or a personal graph.
- A write cannot be bounded, validated, or fully effect-accounted.