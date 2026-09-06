# Graph Governor synthetic graph fixture version 1

This fixture is fictional test data for the bounded read-only Graph Governor scenarios.

- `baseline/graph/` contains the canonical valid synthetic graph.
- `variants/` contains complete replacement-file overlays for controlled mutations. Materialize a disposable test graph by copying `baseline/graph/` and replacing only the files under the selected variant's `overlay/graph/`.
- `manifest.md` records fixed identities, file hashes, and mutation lineage.

The fixture contains no Work IQ-derived content, credentials, tenant identifiers, live links, personal data, or customer data. It is not a real Compass graph and must never be connected to production data or treated as evidence that Graph Governor works.

Never combine overlays except for the explicitly defined `combined-m002-m003` case.
