# Living-document governance

## Document control

- **Status:** living
- **Version:** 1.0
- **Owner:** Project Dexter
- **Last updated:** 2026-09-01

## Purpose

Allow project intent to evolve through Vibe Coding, training, findings, and user learning while preserving reliable history.

## Living and immutable records

| Record class | Treatment |
| --- | --- |
| Charter, PRD, MVP scope, specifications, test plans, registers | Living; revise when current intent changes |
| Decisions, findings, experiments, test results | Dated history; preserve rather than rewriting observed context or outcomes |
| Confidence assessments | Dated conclusions for an exact evidence state; add a new assessment when materially reassessed |
| Packaged and tested specimens | Immutable by identity; changed bytes create a new specimen |

## Required document control

Every living source of truth identifies:

- owner;
- status;
- version;
- last-updated date;
- governing or upstream sources; and
- material revision history or linked change log.

## Revision rules

- Correct trivial typography without changing meaning.
- Link material changes to the finding, decision, or explicit user direction that motivated them.
- Preserve a prior version when it governed completed implementation, packaging, testing, or a consequential decision.
- Mark superseded documents clearly and point to the current version.
- Never edit an old test result to make it agree with a newer requirement.
- Reassess dependent evidence after material change; do not automatically discard unaffected evidence.

## Status vocabulary

Recommended living-document states are `draft`, `proposed`, `accepted`, `living`, `superseded`, and `retired`. Projects may define narrower vocabularies in their register.

## User authority

Dexter may synthesize existing accepted information into a draft to reduce user effort. It must identify unresolved conflicts and may not infer acceptance, implementation authority, release authority, or observed outcomes.