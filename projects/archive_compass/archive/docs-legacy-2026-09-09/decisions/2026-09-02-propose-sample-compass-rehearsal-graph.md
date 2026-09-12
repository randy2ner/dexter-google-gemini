# Decision: Authorize SampleCompass rehearsal graph

- **Date:** 2026-09-02
- **Status:** accepted
- **Deciders:** User / product owner
- **Related plan:** [Experience-led rehearsal plan](../test-plans/2026-09-02-compass-experience-led-rehearsal-plan.md)
- **Prior result:** [Local graph access blocked](../test-results/2026-09-02-compass-experience-rehearsal-local-graph-blocked.md)

## Context

Cowork could not access the local Windows fixture path. The product owner supplied `C:\Users\randt\OneDrive - Microsoft\SampleCompass` as a Cowork-accessible candidate location.

Read-only verification observed exactly one member, `README.md`. It is 299 bytes with SHA-256 `2f344bdb89f8b2157bb8d313401402aef92dc13f9f1834d825b27d46272ff67a`, matching the local restore baseline. The folder and file are OneDrive reparse points, so graph writes may synchronize externally.

## Decision

Authorize `C:\Users\randt\OneDrive - Microsoft\SampleCompass` as the sole writable graph root for the one fictional-data experience rehearsal already authorized.

Authority would be limited to:

1. the five exact candidate packages in the session kit;
2. the fixed fictional rehearsal content;
3. files created or changed beneath this exact folder for the rehearsal journey; and
4. restoration from the verified local baseline if a stop condition occurs and no intervening user edit exists.

## Explicit exclusions

- No parent, sibling, personal, production, or other OneDrive folder.
- No real Email, Teams, OneDrive, or other work evidence.
- No development beta, deployment, publication, or release.
- No silent scope expansion if Cowork cannot use this folder.
- No overwrite of an intervening user edit during recovery.

## Consequences

- The product owner explicitly accepted this synchronized write boundary before resuming Installation Interview.
- The local `restore-baseline/graph` remains the external recovery source.
- Runtime effects must be inspected against this exact folder and compared with Cowork's terminal report.