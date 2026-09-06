# Finding: Perspective Discovery Adaptive Card controls are inaccessible

## Metadata

- **First observed:** 2026-09-01
- **Status:** open
- **Severity:** high
- **Owner:** User / product owner
- **Affected skills/versions:** compass-installation-perspective-discovery `0.1.1-experimental` in the observed Copilot Cowork host

## Summary

During candidate review, the combined explanatory text, review choices, and navigation controls exceeded the usable Adaptive Card surface. The user could not resize or scroll the card to reach required next or skip controls. The interaction therefore exposed user choices but did not keep those choices operable.

This is recorded as an observed Cowork host interaction, not as a universal Adaptive Cards platform limit.

## Evidence

- [Cancelled PD-LEAN-001 connected-run result](../test-results/2026-09-01-perspective-discovery-v0-1-1-pd-lean-001-cancelled.md)
- Microsoft recommends concise Adaptive Cards and one to three primary actions, with up to six supported: [Designing Adaptive Cards for your app](https://learn.microsoft.com/en-us/microsoftteams/platform/task-modules-and-cards/cards/design-effective-cards#anatomy).
- Microsoft states that too many actions can overwhelm users and that less is more: [Adaptive Card action guidance](https://learn.microsoft.com/en-us/microsoftteams/platform/task-modules-and-cards/cards/design-effective-cards#actions).
- Microsoft documents scrollable containers using `maxHeight` for supported Teams card surfaces: [Scrollable containers in Adaptive Cards](https://learn.microsoft.com/en-us/microsoftteams/platform/task-modules-and-cards/cards/cards-format#scrollable-containers-in-adaptive-cards).
- Microsoft notes that rendering and support vary by host and form factor: [Adaptive Card support in Teams](https://learn.microsoft.com/en-us/microsoftteams/platform/task-modules-and-cards/cards/cards-reference#support-for-adaptive-cards).

## Reproduction conditions

Observed once in the authorized PD-LEAN-001 revision 2 Cowork run after bounded retrieval, when a candidate review combined substantial explanatory text with multiple choices and navigation. Cowork version and exact viewport dimensions were not reported. Broader reproducibility is untested.

## Impact

- The user cannot reliably approve, revise, generalize, omit, navigate, or skip when controls are outside the usable surface.
- Candidate review cannot complete even when its language and privacy handling are otherwise acceptable.
- User agency, accessibility, and trust are reduced.
- Connected confidence and handoff claims remain unsupported.

## Proposed action

Perform impact analysis before changing source. Consider a progressive conversational design that:

- keeps each candidate turn short;
- presents no more than the minimum primary choices needed at that moment;
- moves explanation or review references behind optional detail;
- uses secondary-action overflow only where the Cowork host demonstrably supports it;
- provides a plain-text response fallback for every required action; and
- does not depend on card scrolling, resizing, or a Teams-specific property unless Cowork support is verified.

No correction, package revision, rerun, or release is authorized by this finding.

## Resolution

Open. The exact host limitation and an effective corrective interaction remain unverified.