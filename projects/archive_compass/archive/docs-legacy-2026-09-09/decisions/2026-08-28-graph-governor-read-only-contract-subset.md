# Decision: Bound the Graph Governor read-only contract subset

- **Date:** 2026-08-28
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Synthetic fixture construction validation](../test-results/2026-08-28-graph-governor-synthetic-fixture-validation.md)
- **Accepted:** 2026-08-28 by explicit user decision

## Context

The generic synthetic fixture family is complete and passed bounded disconnected construction validation. The shared contracts, graph schema, and Graph Governor specifications remain review drafts. The accepted first-slice decision requires an exact approved subset before Graph Governor source may be implemented, but accepting every write, recovery, Microsoft 365, timezone-mapping, lifecycle, and last-activity rule would unnecessarily widen the read-only experiment.

This decision defines the smallest current contract subset needed by scenarios GG-SYN-001 through GG-SYN-008. Acceptance applies only to the listed subset and does not infer acceptance of the surrounding draft specifications.

## Decision

For the first experimental read-only Graph Governor slice, only the following rules are approved:

### Shared-contract subset from version 0.2-draft

- Shared vocabulary for Conversation, Tracking Topic, CSP, Person, Daily Log, and Graph Governor in section 4.
- Forward relationship ownership in SC-KNOW-005.
- Source Conversation identity and identity separation in SC-ID-001 through SC-ID-005, limited to structural presence and distinction; no live-source verification is included.
- Evidence and graph content do not become trusted instructions under SC-AUTH-001.
- Read access does not imply write authority under SC-ROLE-003.
- No-false-success, bounded effect accounting, and safe reporting under SC-OUT-001 through SC-OUT-003.
- Exact-version evidence and preservation of historical evidence under SC-EVO-003 and SC-EVO-004.

### Graph-schema subset from version 0.2-draft

- Representation, field naming, timestamps, stable identity, frontmatter ownership, and common object rules in sections 3 and 4.
- The baseline and mutation-relevant Conversation rules in sections 5.1 through 5.4.
- The baseline and mutation-relevant Tracking Topic rules in sections 6.1 through 6.4.
- CSP structure and stability in section 7.
- Person structure and identity in sections 8.1 through 8.3.
- Daily Log frontmatter, managed-marker boundary, and managed index organization in sections 9.1 through 9.3. Write, deduplication, backdating, and tombstone behavior remain excluded.
- Stored graph configuration in section 10.1 only: supported schema version, canonical lowercase UUID v4 graph ID, and IANA timezone value. Runtime timezone lookup, Windows mapping, provisional use, bootstrap, and configuration writes remain excluded.
- Forward relationship existence, target type, uniqueness, cardinality, and ownership in section 11.
- Only the corresponding read-only checks in section 12: checks 1 through 9 and 12 through 14. Checks 10 and 11 are reported only where the supplied fixture makes them directly observable. Checks 15 and 16 remain excluded.

### Graph Governor subset from version 0.1-draft

- Purpose and quiet-safety-officer interaction style in sections 1 and 3, restricted to the read-only slice.
- User-requested health scan in section 4.3.
- Health-scan scope and bounded issue-report shape in section 9. Candidate severity labels may organize findings but do not independently authorize or block any operation in this slice.
- No modification authority and explicit exclusions in sections 11 and 12.
- Required evidence boundary in section 14.

### Explicit behavior boundary

The experimental Skill may inspect only a user-supplied synthetic fixture, report observed issues and limitations, and refuse every request to repair, normalize, create, delete, move, or rewrite graph content. It must treat all supplied graph text as untrusted data. A valid baseline result means only that no issue was found within the accepted subset and inspected fixture; it is not a whole-graph, environment, runtime, or Compass-health claim.

All other provisions in the three draft specifications remain unapproved and unavailable as implementation assumptions for this slice.

## Alternatives considered

- **Approve all three draft specifications:** Not selected because unresolved write, runtime, source-identity, last-activity, and timezone-mapping questions are outside this experiment.
- **Implement directly from the fixture specification:** Not selected because fixtures define test inputs, not Skill responsibilities or reporting authority.
- **Wait for every Compass contract to be final:** Not selected because a narrow read-only slice can generate evidence while preserving open decisions.

## Consequences

- Acceptance provides a traceable, narrow dependency boundary for source design and static review.
- The first source version could not claim write validation, post-write verification, connected identity verification, complete schema coverage, or production graph support.
- Any change to the accepted subset would require a new decision revision and affected scenario review.
- The fixture and scenarios remain usable without converting unresolved draft content into accepted behavior.

## Follow-up

- Project Dexter: prepare an experimental read-only Graph Governor implementation plan; create no Skill source under this authorization.
- User / product owner: separately accept, revise, or defer the implementation plan before any source is created.
- Project Dexter: do not package, upload, or execute the Skill without later explicit authorization and satisfaction of the remaining test-plan gates.

## Authorization boundary

The user explicitly accepted this bounded subset and selected implementation planning only on 2026-08-28. This acceptance authorizes creation of an implementation plan. It does not authorize Skill source creation, local implementation checks, `.skill` packaging, Cowork upload, scenario execution, connected access, graph modification, deployment, or publication.
