# Test result: Fresh installation package-set validation

## Metadata

- **Date:** 2026-09-08
- **Status:** complete static package-set validation
- **Owner:** Project Dexter laboratory assistant
- **Package set:** [Fresh installation HPI narrative candidates](../inventory/compass-hpi-narrative-candidate-package-set.md)
- **Prior evidence:** [HPI narrative static validation](2026-09-08-hpi-narrative-static-validation.md)

## Direct observations

1. Installation Interview source and behavior contract declare `0.6.0-hpi-narrative-compatible-candidate`, Shared Contracts and Graph Schema `0.7-hpi-narrative-baseline`, and lifecycle orchestration `0.6.0-hpi-narrative-candidate`.
2. Installation retains its accepted setup flow and keeps optional Topic narrative, `tags`, and `reviewBullet` outside bootstrap. Offered intent routes to Tracking Topic Interview only after verified setup.
3. The Installation archive is 8,216 bytes with SHA-256 `53fed88327382393d86a1e79c99817e5f38ff1cf6ad47e6a805ac02fa5be1a9a`.
4. The Installation archive contains `SKILL.md` and `references/behavior-contract.md`. An independent rebuild was byte-identical; members are safe, unique, sorted, DEFLATE-compressed, mode `0644`, fixed timestamp `2026-09-04 00:00:00`, and byte-equal to current source.
5. The dedicated `ready-for-test/2026-09-08-fresh-installation/` directory contains exactly five `.skill` files: Installation Interview, Daily Scan, Tracking Topic Interview, Curator, and Graph Governor.
6. Each collected file is byte-identical to its independently inspected source archive and matches the size and SHA-256 in the package-set inventory.
7. The five Skills target one schema-version-2 contract and orchestration family. Their responsibility boundaries cover setup, daily capture, Topic management, review, and structural governance.
8. Perspective Discovery is intentionally absent. Its latest experimental candidate is optional and has not completed package inspection or runtime evaluation.

## Result

Pass for Installation compatibility declarations, deterministic packaging, exact five-file collection, byte identity, manifest accuracy, and current contract alignment.

## Interpretation

This is the recommended package set for the next fresh Installation Interview because it removes known version skew and excludes the optional uninspected Perspective Discovery variable. Static compatibility does not prove Cowork import, Skill selection, interface behavior, OneDrive access, graph writes, or Graph Governor runtime decisions.

## Effects

- Compass graph effects: none.
- Connected systems accessed: none.
- Cowork packages imported or executed: none.
- Prior completed results modified: none; the earlier HPI result retains its original four-package scope.
