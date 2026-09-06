# Experiment notes: Perspective Discovery lean connected-run preflight

## Hypothesis

The exact package authorized for PD-LEAN-001 remains locally available and retains its reviewed archive identity before any Cowork import or Work IQ access.

## Variables

- **Changed:** None; this was a read-only package check
- **Held constant:** Package path, bytes, member paths and order, UTF-8 content, and frontmatter identity
- **Environment:** Local Windows filesystem only; no network, Cowork, Work IQ, Microsoft 365, or OneDrive access

## Method

After acceptance of the [lean connected-run authorization](../decisions/2026-09-01-authorize-perspective-discovery-lean-connected-run.md), inspected the exact package at its registered `ready-for-test` path. The check measured byte count and SHA-256, opened the ZIP-compatible archive read-only, verified the exact member set and order, rejected unsafe path forms, tested archive CRCs and UTF-8 decoding, and parsed the root frontmatter name.

## Direct observations

1. The package exists at the exact registered path.
2. The package is 5,972 bytes.
3. The package SHA-256 is `0dfa685330afabe0d3e3e31ad1b5beaf3211c0d275dc1aaac845c92896bfb56f`.
4. Archive members appear in exact order: `SKILL.md`, `references/behavior-contract.md`, and `references/evaluation-cases.md`.
5. All member paths passed the safe-path checks.
6. CRC and UTF-8 checks passed for every member.
7. Root frontmatter identifies `compass-installation-perspective-discovery`.
8. No package, source, or other file was changed.

## Interpretation

The local package identity and archive structure match the artifact authorized for PD-LEAN-001. This establishes only local prerequisite identity. It does not establish Cowork import, Skill activation, Work IQ availability, retrieval behavior, privacy behavior, or any connected scenario outcome.

## Outcome

- **Hypothesis:** supported for local prerequisite identity
- **Result:** pass
- **Related scenario:** [PD-LEAN-001 revision 1](../scenarios/workiq-perspective-discovery/pd-lean-001-bounded-discovery-session.md), authorized but not executed
- **Follow-up:** Perform only the import, invocation, timezone confirmation, and displayed-plan review before selecting `Run`