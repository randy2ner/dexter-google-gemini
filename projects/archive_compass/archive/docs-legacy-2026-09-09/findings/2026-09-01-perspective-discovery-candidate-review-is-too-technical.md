# Finding: Perspective Discovery candidate review is too technical

## Metadata

- **First observed:** 2026-09-01
- **Status:** open
- **Severity:** high
- **Owner:** User / product owner
- **Affected skills/versions:** compass-installation-perspective-discovery `0.1.0-experimental`

## Summary

During the authorized PD-LEAN-001 connected conversation, the candidate-review interaction used technical process language such as `Disposition`, a machine-like candidate ID, and an abstract declarative statement. The user reported difficulty understanding the purpose and became concerned that the interaction felt like an interrogation rather than a humanistic conversation.

This conflicts with the accepted interaction requirement that Perspective Discovery be concise, respectful, curious, grounded in the user's own language, and not feel like employee monitoring, performance analysis, psychological profiling, or interrogation.

## Evidence

- [PD-LEAN-001 pre-retrieval evidence](../test-results/2026-09-01-perspective-discovery-pd-lean-001-pre-retrieval.md)
- User-reported candidate-review heading: `Disposition for PD-20260901-01`
- User-reported generic candidate wording: `Coordinates technical work by connecting issues, people, and follow-up actions.`
- User directly reported that the test questions sounded very technical and that the conversational flow caused concern.

The quoted candidate contains no person, customer, organization, project, message, address, link, source identifier, tenant detail, or raw work excerpt. No retrieved evidence is retained in this finding.

## Reproduction conditions

Observed after the authorized bounded retrieval reached candidate review in one Cowork conversation. Only one reported candidate interaction is available, so consistency across candidates or runtimes is unknown.

## Impact

- The user cannot confidently decide whether a candidate accurately represents their perspective when the candidate's meaning and purpose are unclear.
- Technical disposition terminology shifts interpretation burden onto the user.
- Abstract assertions may feel evaluative or profiling-oriented even when the underlying output is privacy-minimized.
- Confusion can cause accidental confirmation, reduce trust, and undermine meaningful user authority over retained patterns.
- A structurally compliant privacy flow is insufficient if the interaction does not feel understandable and voluntary.

## Proposed action

1. Pause PD-LEAN-001 without further retrieval or candidate processing until the user decides whether to stop the session.
2. Treat conversational quality and user comprehension as primary acceptance requirements, not optional polish.
3. For a future Skill version, replace `Disposition` with a short explanation and a natural question such as `Does this sound like an important pattern in how you work?`
4. Present plain-language choices such as `Yes`, `Change the wording`, `Make it more general`, and `Leave this out`; keep internal IDs secondary or hidden unless needed for correction.
5. Explain why each pattern is being asked about without exposing source content, and allow the user to ask what a statement means before deciding.
6. Do not revise source, rebuild the package, retry the run, or classify the final run outcome without a separate decision and terminal evidence.

## Resolution

Open. The [authorized corrective revision](../decisions/2026-09-01-authorize-perspective-discovery-conversational-review-revision.md) produced source and a [disconnectedly inspected `0.1.1-experimental` package](../test-results/2026-09-01-perspective-discovery-v0-1-1-source-and-package-inspection.md). Resolution remains unverified until a separately authorized connected run provides candidate-review evidence for the exact revised package.