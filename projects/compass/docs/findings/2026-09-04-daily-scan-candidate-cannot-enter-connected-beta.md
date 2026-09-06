# Finding: Daily Scan candidate cannot enter connected beta

- **Date:** 2026-09-04
- **Owner:** User / product owner
- **Status:** open; connected-capable revision required
- **Affected candidate:** `compass-daily-scan` `0.1.0-beta-candidate`
- **Severity:** beta-blocking capability mismatch

## Observation

The development-beta run reached a valid configured graph and an authorized selected-day WorkIQ intent. Daily Scan stopped before retrieval because its source explicitly states that this candidate is not authorized for connected execution and may write only to a supplied disposable synthetic graph.

## Impact

- Real WorkIQ usefulness and source-field behavior remain untested.
- The dedicated graph was not modified.
- No live data was accessed or fabricated.
- The synthetic rehearsal remains valid evidence for the exact candidate's synthetic mode.

## Root cause

Dexter authorized the next lifecycle phase without first reconciling that authority with the executable mode embedded in the exact candidate package. The responsibility specification describes connected behavior conceptually, but the packaged source intentionally excludes it.

## Required direction

A new candidate must explicitly support:

- connected WorkIQ Email and Teams retrieval after a displayed bounded plan and fresh user authorization;
- Cowork-exposed source capabilities and signed-in-user permissions only;
- durable source Conversation identity validation with honest blocking when fields are unavailable;
- proposal review and privacy-minimized retention;
- writes to the user-selected dedicated development-beta graph after exact approval and Graph Governor validation;
- truthful partial-source and blocked outcomes; and
- no use of the synthetic recovery protocol for personal connected state unless a separately accepted recovery design exists.

Perform source-of-truth impact analysis before implementation. Do not edit `0.1.0-beta-candidate` in place or reinterpret its completed synthetic evidence as connected confidence.