# Test result: Production-content package-set validation

## Metadata

- **Date:** 2026-09-08
- **Status:** complete static package-set validation
- **Owner:** Project Dexter laboratory assistant
- **Package set:** [Production-content candidates](../inventory/compass-production-content-candidate-package-set.md)
- **Decision:** [Use production content and native Work IQ capability](../decisions/2026-09-08-use-production-content-and-native-work-iq-capability.md)

## Direct observations

1. The exact set contains five production-test candidates: Installation Interview `0.7.0`, Daily Scan `0.7.0`, Tracking Topic Interview `0.7.0`, Curator `0.6.0`, and Graph Governor `0.8.0`.
2. All five declare Shared Contracts `0.8-production-evidence-baseline`, Graph Schema `0.7-hpi-narrative-baseline` / schema version 2, and orchestration `0.7.0-production-test-candidate` where applicable.
3. The four evidence-facing packages direct Cowork to use all relevant exposed Work IQ source types and continuation or pagination within the approved purpose and scope. They prohibit arbitrary numeric caps and sample-data substitution and require incomplete-coverage disclosure.
4. Governor explicitly does not access Work IQ and does not infer semantic values or judge narrative truth. It validates authority, identity, schema, preservation, and effect truth.
5. Production partial or unverifiable writes stop as `recovery-required`; the package instructions provide no automatic rollback or repair mode.
6. Curator and Governor evaluation-case files are absent. No package includes synthetic test fixtures or sample graph content.
7. Every package member is a safe unique sorted relative path, DEFLATE-compressed, Unix mode `0644`, timestamped `2026-09-04 00:00:00`, and byte-equal to the selected source file.
8. Each archive was independently rebuilt with the same selected source and metadata. All five rebuilds were byte-identical.
9. The dedicated import directory contains exactly the five expected `.skill` files and no temporary or extra files.

## Exact results

| Package | Members | Size | SHA-256 |
| --- | --- | ---: | --- |
| `compass-installation-interview-v0.7.0-production-test-candidate.skill` | `SKILL.md`, `references/behavior-contract.md` | 8,648 | `1ffe18ae79c24739f99d0df7e6ea0e29e86b9bf3a322f1c2a3c64778897ce509` |
| `compass-daily-scan-v0.7.0-production-test-candidate.skill` | `SKILL.md`, `references/behavior-contract.md` | 6,322 | `2648d308555bd7b633f6613ef1407a52dbd17d932df0da5e4a079794285b319e` |
| `compass-tracking-topic-interview-v0.7.0-production-test-candidate.skill` | `SKILL.md`, `references/behavior-contract.md` | 6,895 | `6f3cfc0ca3b27debea496025c91acf212c02a5601078f4ebf5d212c2c3cba55b` |
| `compass-curator-v0.6.0-production-test-candidate.skill` | `SKILL.md`, `references/behavior-contract.md` | 4,922 | `12dce6ec55c914ca785863739cb452a96497ea1af03f35ca4d5d8afbc9623074` |
| `graph-governor-v0.8.0-production-test-candidate.skill` | `SKILL.md`, `references/beta-contract.md`, `references/read-only-contract.md` | 12,506 | `c8b239c17fdd287d9340a0ea1bad884c5a556d11e8103e5db5dca673f3d0d3b8` |

## Result

Pass for source/package identity, deterministic rebuild, archive safety and metadata, exact five-file collection, version alignment, production-evidence instructions, role separation, and evaluation-fixture exclusion.

## Interpretation

This is the current package set for production-content testing. The instructions do not artificially reduce Cowork's relevant Work IQ use through source allowlists or arbitrary result limits. The remaining limits are platform-exposed capability, Microsoft permissions and protections, the user's explicit purpose and scope, relevance, data minimization, and exact review and approval.

This static result does not prove Cowork import, available Work IQ sources, retrieval completeness, pagination behavior, ranking quality, conversation identity availability, production writes, persistence, or training readiness. Those require the mediated production test and independent effect inspection.

## Effects

- Compass graph effects: none.
- Connected systems accessed: none.
- Cowork packages imported or executed: none.
- Prior completed results modified: none.
