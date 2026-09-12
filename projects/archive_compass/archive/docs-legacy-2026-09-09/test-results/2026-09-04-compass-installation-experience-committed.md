# Test result: Compass Installation experience committed

## Run metadata

- **Date:** 2026-09-04
- **Tester:** User / product owner
- **Skill/version:** `compass-installation-interview` `0.1.1-beta-candidate`; Graph Governor `0.2.0-beta-candidate` reported as validation participant
- **Scenario:** [Experience-led rehearsal](../scenarios/compass-experience-led-rehearsal.md)
- **Environment:** Approved managed Cowork client and real OneDrive `SampleCompass` folder
- **Result:** committed

## Direct observations

1. Cowork inferred `America/New_York` from profile information, disclosed it, and let the user accept it.
2. Installation conversationally collected a role statement, one CSP, three Tracking Topics, and three fictional People.
3. After read-only discovery, Cowork resolved the actual OneDrive folder rather than using the local Windows path or an `output` mirror.
4. Cowork classified the graph as new but not empty and identified `README.md` as protected unmanaged content.
5. Version `0.1.1` presented the complete bootstrap proposal as readable plain text with a usable typed decision prompt.
6. After the user typed `Approve`, Cowork presented repeated per-file Adaptive Card approvals. The user approved creation of all reviewed effects.
7. Cowork reported Graph Governor `valid` before writing and `committed` after verification.
8. Cowork reported 5 folders and 9 files created, 0 overwritten, with OneDrive as the only external system accessed.

## External graph inspection

- Exactly the 9 reported managed files plus the original `README.md` are present.
- Configuration parses with schema version 1, the reported graph ID, and `America/New_York`.
- One CSP, three Topics, and three People parse with required frontmatter.
- All three Topic `cspId` values resolve to Northstar Readiness.
- All People have `identityState: provisional`.
- The Daily Log parses with `daily-log:2026-09-04`, contains exactly one accepted marker pair, and includes Configuration, CSPs, Tracking Topics, and People sections.
- `README.md` remains 299 bytes with SHA-256 `2f344bdb89f8b2157bb8d313401402aef92dc13f9f1834d825b27d46272ff67a`.

## Shaping feedback

- The plain-text preview correction worked.
- Requiring another series of Adaptive Card approvals after one informed approval felt repetitive. Treat this as a shaping theme, not a failed installation or immediate repackaging trigger.
- Profile-informed timezone selection was accepted as useful, user-correctable behavior.

## Conclusion

Installation produced a recognizable, successful Compass foundation with reported effects matching the synchronized graph. Continue the same experience into Daily Scan. Do not rerun Installation or isolate timezone, path, frontmatter, or approval-card mechanics unless they become a recurring trust or control problem.