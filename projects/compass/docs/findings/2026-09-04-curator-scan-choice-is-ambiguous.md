# Finding: Curator scan choice is ambiguous

- **Date:** 2026-09-04
- **Owner:** User / product owner
- **Status:** shaping feedback; direct health scan pending after clarified intent
- **Affected candidate:** `compass-curator` `0.1.0-beta-candidate`
- **Severity:** non-blocking interaction clarity issue

## Observation

Curator offered an independent read-only Graph Governor health scan using its generic recommendation choices. The user intended to run the scan but selected the first option, `Keep as is`, because the remaining choices sounded like cancellation. Curator then correctly reported `Keep as is`, skipped the scan, and prepared no handoff.

## Expected behavior

When Curator offers a concrete optional action, the choices should make the action path explicit. For example, `Run read-only scan`, `Skip for now`, and `Cancel review` are clearer in this context than generic recommendation dispositions.

## Impact

- No graph state was changed or damaged.
- The intended assurance was not performed during Curator review.
- The terminal report accurately represented the selected control.
- The generic choice labels caused avoidable user uncertainty.
- The Curator-to-Governor routing path is not demonstrated by this interaction.

## Recovery

Initiate the same bounded read-only Graph Governor health question directly. Evaluate candidate correction after the experience concludes, alongside the recurring interaction themes, rather than interrupting the rehearsal with immediate repackaging.