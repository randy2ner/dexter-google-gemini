# Finding: Installation bootstrap approval card blocks review

## Document control

- **Status:** resolved for proposal review; repeated write-confirmation cards remain shaping feedback
- **Version:** 1.0
- **Owner:** User / product owner
- **Observed:** 2026-09-02
- **Last updated:** 2026-09-02
- **Source result:** [Cancelled Installation rehearsal](../test-results/2026-09-02-compass-installation-rehearsal-cancelled.md)

## Direct observation

Installation Interview `0.1.0-beta-candidate` placed its full bootstrap proposal and action controls in an oversized Adaptive Card. The user could not practically invoke the needed Change path. Closing the card cancelled the operation. External inspection verified zero graph effects.

The preview also omitted complete relative paths for the four Markdown object files and described the Daily Log as one Configuration entry recording all created objects rather than separate entries in their accepted object-type sections.

## Interpretation

This is an interaction-blocking candidate defect, not cosmetic variation. A required approval surface is ineffective when the user cannot comfortably review or revise the consequential write set. Typed fallback existed in source intent but was not practically available through the rendered experience.

The zero-effect cancellation behavior worked and prevented an under-reviewed write.

## Required correction

1. Render bootstrap review as concise plain text, not one content-heavy Adaptive Card.
2. Put one short decision prompt after the preview: `Approve`, `Change`, `Pause`, or `Cancel`.
3. Keep typed choices fully equivalent to any rendered controls.
4. List every exact relative target path.
5. List CSP, Tracking Topic, Person, and Configuration Daily Log entries separately.
6. Preserve IDs, wording, source-state fingerprint, relationship direction, and recovery disclosure without surrounding UI narration.

## Retest scope

Resume one Installation setup journey with the corrected package. Verify only that the proposal is reviewable, Change is usable, and cancellation/approval produces truthful effects. Continue the same experience-led rehearsal if successful; do not reopen the superseded seven-check suite.

## Correction

Installation Interview `0.1.1-beta-candidate` implements the required plain-text preview, exact relative paths, per-object Daily Log entries, and typed choices. Its [source/package inspection](../test-results/2026-09-02-installation-v0-1-1-source-and-package-inspection.md) passed. The finding remains unresolved until the corrected package is observed in Cowork.

The [2026-09-04 Installation experience](../test-results/2026-09-04-compass-installation-experience-committed.md) confirmed that the revised proposal was readable and the typed approval was usable. Cowork then required repeated per-file Adaptive Card confirmations. That repetition did not prevent completion and is retained as shaping feedback rather than a reason for another immediate package revision.