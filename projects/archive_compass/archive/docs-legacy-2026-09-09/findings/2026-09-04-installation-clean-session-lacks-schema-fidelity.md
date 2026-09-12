# Finding: Installation clean session lacks schema fidelity

- **Date:** 2026-09-04
- **Owner:** User / product owner
- **Status:** open
- **Affected candidate:** `compass-installation-interview` `0.1.1-beta-candidate`
- **Severity:** material but recoverable before write

## Observation

In a new development-beta Cowork task, Installation declared the accepted Graph Schema `0.3-beta-baseline` as a dependency but initially proposed noncanonical object directories, incomplete common frontmatter, unsupported CSP state, and an incomplete Daily Log representation. It disclosed that the specification content was not loaded. The user selected `Change`, and laboratory-provided schema details produced a valid final proposal.

## Impact

- No incompatible files were written.
- User review and correction worked.
- Without external schema coaching, a normal user could approve a graph that later candidate Skills cannot safely share.
- The clean-session candidate is not self-sufficient for its owned bootstrap outcome.

## Working hypothesis

The package names the shared schema dependency but does not carry enough normative schema content for reliable clean-session execution. Confirm through package/source impact analysis before revising.

## Direction

After the first real selected-day experience, assess the smallest correction that makes required schema rules available to Installation and Graph Governor without embedding unrelated project documentation. Preserve this completed result and rerun only the affected bootstrap path for a new version.