# Compass MVP Scope

## Document control

- **Status:** living record of closed first slice
- **Version:** 1.0
- **Owner:** User / product owner
- **Created:** 2026-09-01
- **Last updated:** 2026-09-01
- **Governed by:** [Compass Charter](../charter/compass-vision-and-scope-charter.md) and [Compass PRD](../requirements/compass-product-requirements.md)
- **Accepted scope:** [2026-08-28 first-slice decision](../decisions/2026-08-28-graph-governor-first-test-slice.md)
- **Closure:** [2026-09-01 closure decision](../decisions/2026-09-01-close-graph-governor-v0-1-0-experimental-test-slice.md)

## Learning objective

Determine whether a Copilot Cowork Skill can inspect a generic fictional Compass graph, apply a bounded integrity contract, resist untrusted instructions, refuse writes, and report honestly before connected evidence retrieval or persistence is attempted.

## Scope statement

The first Compass MVP learning slice is Graph Governor version `0.1.0-experimental`, limited to a synthetic, read-only health scan.

### Included

- Inspect the supplied six-file synthetic Compass graph fixture.
- Validate the accepted subset of configuration, frontmatter, object identity, forward relationships, and Daily Log markers.
- Tolerate unknown content covered by the accepted contract.
- Treat graph content as untrusted data.
- Report deterministic issues with severity, impact, and blocking scope.
- Refuse repair, normalization, and rewrite requests.

### Excluded

- Microsoft 365 or Work IQ evidence retrieval.
- OneDrive or real-graph access.
- Writes, repairs, rollback, recovery, or persistence.
- Last-activity enforcement and automatic repair.
- Cross-Skill Orchestration.
- Product release, deployment, or broad Compass readiness.

## Success and stop conditions

- All eight primary scenarios produce the required bounded behavior.
- Fixture mutations exercise representative schema, relationship, configuration, Daily Log, unknown-content, injection, refusal, and reporting classes.
- The fixture remains byte-identical after each read-only run.
- Failures, unavailable metadata, and scope limitations are reported honestly.
- Testing stops when the accepted claims have proportional evidence and additional variation has low decision value.

## Evidence and disposition

- **Test plan:** [Graph Governor synthetic read-only test plan](../test-plans/2026-08-28-graph-governor-synthetic-read-only-test-plan.md)
- **Evidence:** Eight primary scenarios passed across thirteen primary fixture runs; no fixture bytes changed.
- **Exact tested package:** 9,777 bytes; SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.
- **Confidence:** [Validated only for the bounded experimental read-only synthetic scope](../confidence/2026-09-01-graph-governor-v0-1-0-experimental.md).
- **Disposition:** Closed on 2026-09-01 with documented limitations.

## Remaining gaps

- Cowork runtime and model metadata were not available in the recorded runs.
- Connected storage, writes, repair, rollback, recovery, and production data were not tested.
- Passing this slice does not establish interoperability with unfinished Skills or Orchestrations.
- Any changed source, contract, schema, package bytes, fixture contract, or relevant runtime requires impact analysis before reusing confidence.

## Adjacent but separate work

Perspective Discovery is not part of the closed Graph Governor MVP slice. Its connected candidate-review run is paused after the [humanistic usability finding](../findings/2026-09-01-perspective-discovery-candidate-review-is-too-technical.md). It has no final confidence assessment and must not be represented as complete.

## Revision history

| Version | Date | Change | Motivation |
| --- | --- | --- | --- |
| 1.0 | 2026-09-01 | Normalized the accepted first-slice decision and immutable closure evidence into a living scope record. | User-authorized Dexter source-of-truth feature build |

## Acceptance boundary

This record reflects prior accepted decisions and evidence. It does not expand MVP scope, authorize further implementation, or advance another Compass capability.