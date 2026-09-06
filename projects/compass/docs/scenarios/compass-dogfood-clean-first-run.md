# Cowork session kit: Compass dogfood clean first run

## Document control

- **Status:** ready after package inspection
- **Version:** 1.2
- **Owner:** User / product owner
- **Last updated:** 2026-09-04

## Product acceptance boundary

The product owner may remove previous synthetic and development-beta Compass folders from OneDrive before this run. That cleanup is a user-controlled reset, not a Compass runtime effect and not evidence about Compass deletion behavior.

The dogfood experience begins in a new Cowork task with the exact [Compass package set](../inventory/compass-0.3.3-dogfood-candidate-package-set.md) available. No graph folder, fixture, schema prompt, or prior conversation is supplied. One user-selected internally classified Loop page is available in Microsoft 365 and is introduced naturally during setup to define foundational CSPs.

## First prompt

> Help me install Compass.

## Expected experience

1. Compass explains that it uses an editable OneDrive folder.
2. It offers to create a new `Compass` folder in OneDrive Documents, use an existing folder, or cancel.
3. It confirms timezone and asks conversationally about the user's role and desired outcomes.
4. It accepts the selected protected Loop page through the signed-in Cowork/Microsoft 365 context, confirms its setup purpose, and does not require declassification or a label-free task.
5. It retrieves only relevant content, preserves platform protection, and presents CSPs and Topics as editable derived proposals without retaining raw classified source bodies or label metadata in the graph.
6. It distinguishes strategic CSP outcomes from project-level Tracking Topics and allows a minimal setup.
7. After protected-source retrieval, it explains and completes one content-free plain-text write/read/delete probe at the graph root before creating any managed subfolder.
8. It presents one readable exact proposal, obtains approval, validates, writes and verifies `_compass/config.yaml` first, then creates and verifies the remaining graph.
9. It reports `Compass is installed` and offers `Scan a day`, `Add or discuss a Topic`, or `Review my Compass`.
10. `Scan a day` requests an absolute date, shows a bounded WorkIQ Email and Teams plan, and proceeds through reviewed Conversation proposals.

## Stop conditions

Stop if Compass requires laboratory terminology, a pre-created graph, or schema coaching; rejects the selected source solely because it is classified; asks to remove or weaken its label; accesses an unselected source; retains raw source content or protection metadata in the graph; accesses WorkIQ Email or Teams during installation; searches neighboring OneDrive content; creates managed structure before the post-retrieval probe succeeds and is removed; writes bootstrap content before approval; or reports unverified effects as complete.

If the platform actually refuses the plain-text probe, expect `write-blocked` / `blocked`, the verbatim reason, confirmed probe cleanup state, zero configuration or Daily Log writes, and at most the empty user-confirmed graph root. Compass must describe the protected source as valid and must not prescribe declassification; this outcome remains evidence of an unresolved platform output path.

## Privacy-safe evidence

Record interaction behavior, choice clarity, counts, object types, and verified effect structure. Do not copy real work content, identities, source titles, addresses, tenant URLs, or graph item IDs into Dexter.