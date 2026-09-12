# Test result: HPI narrative source, fixture, and package validation

## Metadata

- **Date:** 2026-09-08
- **Status:** complete static validation
- **Owner:** Project Dexter laboratory assistant
- **Package set:** [HPI narrative candidate packages](../inventory/compass-hpi-narrative-candidate-package-set.md)
- **Test plan:** [HPI Topic narrative and review metadata](../test-plans/2026-09-08-hpi-topic-narrative-and-review-test-plan.md)
- **Fixture:** [Sanitized HPI samples](2026-09-08-hpi-narrative-samples/README.md)

## Direct observations

1. Safe YAML parsing found exactly seven managed objects: one CSP, four People, one Conversation, and one Tracking Topic.
2. All objects declare schema version 2, unique IDs, non-empty titles, and quoted UTC timestamps.
3. Ten stored forward references resolve with expected target types: four Conversation participants, one Conversation-to-Topic link, four Topic participants, and one Topic-to-CSP link.
4. Conversation and Topic participant lists are equal for this no-exclusion specimen. Lists are unique; Topic inclusion and exclusion are disjoint.
5. Topic values parse as strings `status: archived` and `attentionState: waiting`, boolean `success: true`, list `tags: [hpi, solved]`, and boolean `reviewBullet: true`.
6. The Topic body contains all nine expected narrative sections and an explicit statement that retained follow-up does not authorize or request another Topic.
7. No managed YAML contains `activeParticipantIds`, reverse relationship fields, or `userPrincipalName`. No body contains a link or telephone URI.
8. Daily Scan, Tracking Topic Interview, Curator, and Graph Governor sources assign narrative collection, durable composition, review display, and structural validation to distinct owners.
9. Curator and Governor packages contain package-local `UNRUN` HPI evaluation cases. Graph Governor's constrained read-only reference is schema-version-2 compatible and subordinate to its current beta contract.
10. Four archives were independently rebuilt byte-for-byte. Every archive has safe unique sorted members, root `SKILL.md`, exact source content, DEFLATE compression, mode `0644`, and fixed timestamp `2026-09-04 00:00:00`.
11. Package sizes and SHA-256 values match the linked package-set inventory.
12. Repository whitespace checks passed for the sample and packaged source slices.

## Result

Pass for the applicable static cases: object counts, type-specific frontmatter, canonical forward links, participant funneling, HPI metadata, narrative structure and boundary, source responsibility separation, contract alignment, archive integrity, and deterministic packaging.

## Interpretation

Dexter has direct evidence that the sample frontmatter conforms to the accepted schema subset and that the exact package bytes contain the intended instructions. This result does not establish that Cowork will invoke the right Skill, produce the approved prose, write or preserve files correctly, emit the expected Curator bullet, or return the expected Governor decision. Those claims remain `UNRUN` under the mediated scenario.

Two preliminary disposable validators produced false failures because their assertions confused lifecycle strings with booleans, parsed frontmatter boundaries incorrectly, and treated the incident number in a supplied Chat title as a phone number. Those runs did not alter files and are not evidence against the specimen. The final validation used type-specific predicates and printed every parsed object before passing.

## Effects

- Compass graph effects: none.
- Connected sources accessed: none.
- Cowork packages imported or executed: none.
- Existing historical fixtures, packages, and results modified: none.
