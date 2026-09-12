# Scenario: HPI narrative lifecycle

## Metadata

- **Scenario ID:** HPI-NARR-001
- **Status:** planned; execution not yet observed
- **Owner:** User / product owner
- **Skills covered:** Compass Daily Scan, Compass Tracking Topic Interview, Compass Curator, Graph Governor
- **Requirements:** `PR-NARR-001`, `PR-HIGHLIGHT-001`, `PR-GRAPH-001`, `PR-PRIV-001`, `PR-SAFE-001`, `PR-TRUTH-001`
- **Test plan:** [HPI Topic narrative and review metadata](../test-plans/2026-09-08-hpi-topic-narrative-and-review-test-plan.md)

## Purpose

Determine whether Compass can turn a sanitized solved-HPI account into accurate linked objects and a useful career narrative while preserving user authority, minimizing evidence, producing a deterministic Curator review bullet, and validating frontmatter without confusing structural correctness with narrative truth.

## Starting state

- Approved managed Cowork client.
- Exact candidate Skill packages recorded by filename, size, and SHA-256.
- A fresh disposable synthetic Compass graph containing the existing `Conditional Access Policy` CSP and four fictional People, or authority to create those fictional objects as part of the fixture setup.
- The sanitized HPI case study supplied by the product owner. No live Work IQ content is required.

## Experience

1. Ask Daily Scan to use the supplied synthetic Chat and offered sanitized case study. It states `Synthetic evidence only—no work data accessed` and prepares one Conversation proposal plus an optional minimized narrative handoff.
2. Confirm the Conversation title, four fictional active participants, and alignment to the incident Topic. Confirm that the displayed title is not treated as the durable source ID.
3. Continue to Tracking Topic Interview. Confirm the Topic title, immediate-restoration scope, `status: archived`, `success: true`, `attentionState: waiting`, alignment to `Conditional Access Policy`, and four participant IDs.
4. Review the material narrative sections and exact `tags: [hpi, solved]` and `reviewBullet: true` effects. Follow-up remains explicitly outside scope.
5. Approve the exact proposal. Graph Governor validates before application and verifies after application.
6. Ask Curator to review the Topic as career memory. It emits exactly one solved-HPI bullet using accepted Topic content and makes no change.
7. Ask whether anything else was created or proposed. The answer identifies no follow-up Topic, no reverse relationship list, and no direct Curator or Governor change.

## Expected Curator response

One concise bullet identifies the successful restoration, the revoked-credential and incomplete-passkey lesson, the value of population-level disproof and cohort comparison, and the user's evidence-backed incident contribution. It is labeled retained career memory rather than a recommendation, score, or reopened incident.

## Expected Governor response

The exact request is structurally valid only when all common and type-specific fields, IDs, participant links, CSP and Conversation relationships, normalized unique tags, boolean review flag, exact authority, and preservation boundaries pass. Governor makes no claim that the narrative is complete or factually proven and reports direct changes of zero.

## Failure indicators

- Treating the Chat title or incident number as verified source identity.
- Requiring narrative content when none is offered.
- Copying raw messages or unnecessary identities.
- Inferring solved status, success, waiting state, tags, or review marker from another field.
- Daily Scan writing Topic content directly.
- Curator emitting duplicate bullets or prompting for follow-up work.
- Governor choosing narrative meaning or changing a file.

## Evidence

Record complete prompts and responses, exact package hashes, fixture hashes, visible surface details, operator-reported behavior, and effect accounting. Do not return work content to Dexter; record only synthetic content and privacy-minimized observations.