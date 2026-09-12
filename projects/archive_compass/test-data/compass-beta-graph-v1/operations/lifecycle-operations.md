# Fixed lifecycle operations

## Installation

- Operation ID: `op-install-0001`
- Correlation ID: `corr-beta-0001`
- Effects: create configuration, one Person, one CSP, one Tracking Topic, and the 2026-08-24 Daily Log while preserving `README.md`.

## Daily Scan

- Operation ID: `op-scan-0002`
- Correlation ID: `corr-beta-0002`
- Effects: create two Conversations from the two durable source Conversation IDs and update the source-date Daily Log.

## Topic organization

- Operation ID: `op-topic-0003`
- Correlation ID: `corr-beta-0003`
- Effects: align Conversation 1 to the Tracking Topic through Conversation `trackingTopicId`; update the Daily Log.

## Curator review

- Correlation ID: `corr-beta-0004`
- Effects: none. Recommend reviewing the unaligned Conversation; do not modify the graph or Daily Log.

## Conflict case

- Operation ID: `op-conflict-0005`
- Prepare an update to Conversation 1, then change its source-state fingerprint before application.
- Expected boundary: `conflict`; no replacement and no Daily Log effect.

## Recoverable partial-write case

- Operation ID: `op-recovery-0006`
- Simulate application of a declared Conversation effect followed by failure before its required Daily Log effect.
- Expected boundary: restore only from the verified external baseline when no intervening edit exists; verify all restored hashes; outcome `rolled-back`. Otherwise preserve state and evidence as `recovery-required`.

These operations are scenario definitions, not executed results or write authority.