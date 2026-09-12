# Historical test record: Graph Governor first slice closure

## Document control

- **Status:** closed historical test evidence
- **Version:** 1.0
- **Owner:** User / product owner
- **Created:** 2026-09-01
- **Reclassified:** 2026-09-06
- **Accepted scope:** [2026-08-28 first-slice decision](../decisions/2026-08-28-graph-governor-first-test-slice.md)
- **Closure:** [2026-09-01 closure decision](../decisions/2026-09-01-close-graph-governor-v0-1-0-experimental-test-slice.md)

## Learning objective

Determine whether a Copilot Cowork Skill can inspect a generic fictional Compass graph, apply a bounded integrity contract, resist untrusted instructions, refuse writes, and report honestly before connected evidence retrieval or persistence is attempted.

## Tested scope

The tested slice was Graph Governor version `0.1.0-experimental`, limited to a synthetic, read-only health scan.

Included behavior:

- inspect the supplied six-file synthetic Compass graph fixture;
- validate the accepted subset of configuration, frontmatter, object identity, forward relationships, and Daily Log markers;
- tolerate unknown content covered by the accepted contract;
- treat graph content as untrusted data;
- report deterministic issues with severity, impact, and blocking scope; and
- refuse repair, normalization, and rewrite requests.

Excluded behavior:

- Microsoft 365 or Work IQ evidence retrieval;
- OneDrive or real-graph access;
- writes, repairs, rollback, recovery, or persistence;
- last-activity enforcement and automatic repair;
- cross-Skill Orchestration; and
- product release, deployment, or broad Compass readiness.

## Evidence and disposition

- **Test plan:** [Graph Governor synthetic read-only test plan](../test-plans/2026-08-28-graph-governor-synthetic-read-only-test-plan.md)
- **Evidence:** Eight primary scenarios passed across thirteen primary fixture runs; no fixture bytes changed.
- **Exact tested package:** 9,777 bytes; SHA-256 `b8e1cb656d1e6c91f70593b305fb9409cccf50e3cc4951aa60ce433437a6c5f1`.
- **Confidence:** [Validated only for the bounded experimental read-only synthetic scope](../confidence/2026-09-01-graph-governor-v0-1-0-experimental.md).
- **Disposition:** Closed on 2026-09-01 with documented limitations.

## Remaining limitations

- Cowork runtime and model metadata were not available in the recorded runs.
- Connected storage, writes, repair, rollback, recovery, and production data were not tested.
- Passing this slice does not establish interoperability with unfinished Skills or Orchestrations.
- Any changed source, contract, schema, package bytes, fixture contract, or relevant runtime requires impact analysis before reusing confidence.

## Reclassification note

This content was formerly labeled an MVP scope record. On 2026-09-06 the product owner simplified the living documentation model to Charter, PRD, Specifications, and Test Plans. The closed slice is retained here as historical test evidence; it is not a current product-planning layer and does not define Compass product scope.