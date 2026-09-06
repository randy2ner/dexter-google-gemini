# Decision: Adopt shaping-first vibe-coding standard

- **Date:** 2026-09-04
- **Status:** accepted
- **Deciders:** User / product owner
- **Related plan:** [Experience-led rehearsal plan](../test-plans/2026-09-02-compass-experience-led-rehearsal-plan.md)

## Context

During the Installation rehearsal, Cowork inferred `America/New_York` from profile information, disclosed it, and asked the user to confirm or replace it. The fixed fixture had used `America/Los_Angeles`, and the laboratory assistant initially treated that mismatch as a reason to pause.

The product owner clarified that deterministic control of low-consequence behavior is not the purpose of Dexter. LLM, host, and session variation will remain. Compass should be shaped through representative use, with individual correction and adaptation handled through the user's relationship with Cowork when consequences are minor.

## Decision

Use a shaping-first standard for Compass instruction development:

1. Evaluate recognizable product experiences before isolated implementation details.
2. Treat disclosed, user-correctable variation as feedback rather than failure when it does not threaten trust, privacy, identity, history, or recoverability.
3. Do not require exact fixture wording, timestamps, timezone, filenames, ordering, or scan boundaries unless the difference materially changes meaning or safety.
4. Let the user accept or correct reasonable Cowork inference, including profile-informed defaults.
5. Record themes worth shaping; do not revise and repackage after every non-blocking variation.
6. Stop only for unauthorized or unexplained effects, privacy violations, destructive history loss, identity corruption, unusable control, unrecoverable state, or false success.

## Current observation

The user accepted `America/New_York` for the fictional graph and classified the interaction as a success. Cowork inferred a plausible profile value, disclosed it, and preserved user choice. No deterministic comparison with the fixture timezone is required.

## Consequences

- Continue the current Installation experience without another timezone test or package revision.
- Daily Logs or Scans that differ by a few hours are development feedback unless they create meaningful loss, confusion, or incorrect effects.
- Exact technical assertions remain appropriate for high-consequence boundaries, but they do not become the default shape of product evaluation.
- Batch future instruction changes around recurring experience themes instead of responding to every session variation.