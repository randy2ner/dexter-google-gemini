# Test result: Compass development-beta Installation committed with warning

## Run metadata

- **Date:** 2026-09-04
- **Tester:** User / product owner with laboratory assistant
- **Skill/version:** `compass-installation-interview` `0.1.1-beta-candidate`
- **Scenario:** [Development-beta opening experience](../scenarios/compass-development-beta-opening-session.md)
- **Environment:** Approved managed Cowork client and dedicated OneDrive development-beta graph
- **Result:** committed with warning

## Direct observations

1. Cowork discovered the new dedicated graph root and reported it empty before proposing effects.
2. Installation confirmed `America/New_York` and accepted one user-supplied CSP title without using WorkIQ history.
3. Its first proposal used noncanonical directories and omitted required common object and Daily Log fields. Cowork disclosed that it did not have the accepted schema content available and invited correction.
4. The laboratory assistant supplied the accepted `0.3-beta-baseline` requirements. Cowork revised the proposal through three user-authorized `Change` turns.
5. The final preview contained the approved configuration, one CSP, and one installation-date Daily Log. The user approved it.
6. Cowork reported the graph committed and verified, with no Email, Teams, or WorkIQ access and no changes outside the dedicated graph.

## External graph inspection

- The graph contains exactly three files in three expected directories: `_compass/config.yaml`, one CSP under `CSPs/`, and `Daily Logs/2026-09-04.md`.
- Configuration contains only `schemaVersion`, a lowercase UUID v4 `graphId`, and `America/New_York`.
- The CSP contains all required common fields, a stable ID, the user-supplied title, and no unsupported lifecycle field.
- The Daily Log contains required frontmatter, exactly one accepted marker pair, accepted CSPs and Configuration sections, a navigable CSP link, stable IDs, and `created` action records.
- No unexpected files were observed.

The external inspection did not establish what Cowork stores outside the graph. Cowork's phrase `saved its identity for next time` is accepted only as a reference to the durable graph identity in `_compass/config.yaml`; no hidden persistence claim is established.

## Assessment

The dedicated beta graph is suitable for continued use. Installation's final effects are valid and match the approved proposal. However, the candidate did not independently produce its declared schema in a clean task and would have seeded an incompatible graph without laboratory correction. This is a material candidate packaging or instruction-dependency finding, not ordinary wording variation.

## Next action

Add the minimum user-selected Tracking Topic, `Project Dexter`, aligned to the existing CSP before the first real WorkIQ Daily Scan. Keep real work content out of Dexter records.