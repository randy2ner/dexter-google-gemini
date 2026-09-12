# Disposable fixture restore procedure

This procedure applies only to `compass-beta-graph-v1` under separate test authorization.

1. Confirm the target is exactly `materialized/graph/` within this fixture.
2. Confirm no writer is active and preserve any recovery evidence outside the target.
3. Compare the current target with the operation's recorded preconditions. Stop if an intervening edit may exist.
4. Remove only contents inside the disposable materialized target.
5. Copy all contents from `restore-baseline/graph/` into `materialized/graph/` without changing the baseline.
6. Recompute every materialized byte count and SHA-256.
7. Compare them with the baseline inventory in the construction-validation record.
8. Report `rolled-back` only when every file and hash matches. Otherwise report `recovery-required` and preserve the observed state.

Never point this procedure at another directory, a synchronized location, OneDrive, a personal graph, or a production graph.