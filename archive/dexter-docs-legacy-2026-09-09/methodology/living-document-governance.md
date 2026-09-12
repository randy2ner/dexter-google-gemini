# Living-document governance

## Document control

- **Status:** living
- **Version:** 3.0
- **Owner:** Project Dexter
- **Last updated:** 2026-09-01

## Purpose

Allow project intent to evolve through Vibe Coding, training, findings, and user learning while preserving reliable history.

## Living and immutable records

| Record | Treatment |
| --- | --- |
| Specification | Living; revise when purpose, requirements, decisions, behavior, dependencies, or implementation status change |
| Test Plan | Living; preserve dated execution observations while updating cases and the current success assessment |
| Packaged and tested specimens | Immutable by identity; changed bytes create a new specimen |

## Required document control

Every living source of truth identifies:

- owner;
- status;
- version;
- last-updated date;
- material revision history.

## Revision rules

- Correct trivial typography without changing meaning.
- Record the motivation for a material Specification change in its revision history.
- Preserve a prior version when it governed completed implementation, packaging, testing, or a consequential decision.
- Mark superseded documents clearly and point to the current version.
- Never edit a dated Test Plan observation to make it agree with a newer requirement.
- Reassess dependent evidence after material change; prefer one post-beta compatibility rewrite and do not automatically discard unaffected evidence.

## Status vocabulary

Recommended document states are `draft`, `active`, and `complete`. A requirement or test case may have its own concise status when needed.

## User authority

Dexter may synthesize existing accepted information into a draft to reduce user effort. It must identify unresolved conflicts and may not infer acceptance, implementation authority, release authority, or observed outcomes.