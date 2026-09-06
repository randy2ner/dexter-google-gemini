# Fixture manifest: gg-synthetic-graph-v1

## Identity

- **Fixture:** `gg-synthetic-graph-v1`
- **Version:** `1.0.0`
- **Created:** 2026-08-28
- **Graph ID:** `6f9619ff-8b86-4d7e-a4ea-8f4f6f7c2b11`
- **Reference date:** `2026-08-24`
- **Content basis:** Wholly generic fictional content; no Perspective Discovery or Work IQ input
- **Intended use:** Read-only Graph Governor synthetic scenarios only
- **Prohibited use:** Real graph, production data, runtime-success claim, or source evidence

## Governing documents

- Compass charter version 1.0
- Compass Shared Contracts Specification version 0.2-draft, bounded structural subset only
- Compass Graph Schema Specification version 0.2-draft, bounded structural subset only
- Graph Governor Skill Specification version 0.1-draft, read-only subset only
- Graph Governor Synthetic Fixture Specification version 1.0

Draft dependencies remain identified as drafts. Fixture creation does not approve or validate them.

## Baseline inventory

| Relative path under `baseline/graph/` | Bytes | SHA-256 |
| --- | ---: | --- |
| `_compass/config.yaml` | 96 | `87a3ba9e79055e2b06df6485003f5c179041e4a73c384283b4ca123e808891c1` |
| `people/avery-stone.md` | 270 | `6e62c01ee5a5c7aa848c881aeef14cad9fcca5bf6e7dbb3c01ac822522dbae3b` |
| `csps/aurora-csp.md` | 265 | `1334267aa5a0365954459d7e872150594e6a04b9b9b724932579358344f0885b` |
| `tracking-topics/aurora-readiness.md` | 349 | `d003f41b181825abae2df93a1675054c36f05728684a82607145e9db6c67a3f8` |
| `conversations/aurora-deployment-review.md` | 581 | `5b201290ff870c040654afa12677c84b1613cf01be69ccc9c44ef29c89f96f59` |
| `daily-logs/2026-08-24.md` | 1,500 | `fbe7eec505f12584c4050305ddf5356cd314bd565b6e4b8c40ae1004d81365b6` |

## Fixed object identities

| Type | ID |
| --- | --- |
| Graph | `6f9619ff-8b86-4d7e-a4ea-8f4f6f7c2b11` |
| Person | `person:10000000-0000-4000-8000-000000000001` |
| CSP | `csp:20000000-0000-4000-8000-000000000001` |
| Tracking Topic | `tracking-topic:30000000-0000-4000-8000-000000000001` |
| Conversation | `conversation:40000000-0000-4000-8000-000000000001` |
| Daily Log | `daily-log:2026-08-24` |

## Fictional-content declaration

All names, organizations, programs, identifiers, source activity, dates, and prose in the graph are fictional. No element was derived from Work IQ, Microsoft 365, a tenant, a customer, a person, or a prior-project test record.

## Variant lineage

Each variant stores complete replacement files under `variants/<variant>/overlay/graph/`. Materialization copies the canonical baseline and replaces only the listed paths.

| Variant | Replacement path | Bytes | SHA-256 | Declared delta |
| --- | --- | ---: | --- | --- |
| `m-001` | `conversations/aurora-deployment-review.md` | 580 | `5e2112ee0765b7d554c4478f62f30077508d44aedfc1c8e9ea0465e92d45f224` | Malformed YAML mapping entry |
| `m-002` | `conversations/aurora-deployment-review.md` | 516 | `7d64565113bfd63fee441affdeff362e5e4b9f203856f40c0443bcba65ecf595` | Missing `sourceConversationId` |
| `m-003` | `tracking-topics/aurora-readiness.md` | 349 | `0991630916db6644418483ae318905b694c5dd435709ce8765e803d4bfdac439` | Missing CSP target |
| `m-004` | `conversations/aurora-deployment-review.md` | 570 | `ba5df422052063a1627d6a37f0360e9eefc74dc63a76f45beaf980a57b728b0f` | Topic relationship points to CSP |
| `m-005` | `conversations/aurora-deployment-review.md` | 632 | `da9b4ec0d2951e6eaaee4c97d5d82fcc4062e7ad20bc4d10c939473d5d76331d` | Duplicate active participant ID |
| `m-006` | `_compass/config.yaml` | 96 | `c28c7fcb88ef0d9a13c79db59f5b24bff3d393c54c47ef2f7a266dd3664d8911` | Non-v4 graph UUID |
| `m-007` | `_compass/config.yaml` | 98 | `f1ab4f4e27169f1af6f2705edb6dc9763c279bfc5636b96ce3ee9d0eeecf0ea0` | Windows value stored instead of IANA timezone |
| `m-008` | `daily-logs/2026-08-24.md` | 1,542 | `4d051fcb3ec6f5215c25e7f3a042592e78069f4a54786f26f304d9246ee44f90` | Duplicate managed begin marker |
| `m-009` | `people/avery-stone.md` | 433 | `5fe76f1328d77b911528c542b1fbd5c20a9a1bd085a20eed4dc8af97727c3b53` | Accepted unknown field and unmanaged prose |
| `m-010` | `conversations/aurora-deployment-review.md` | 673 | `ede2b9995d5fddf7b99196d021410db0c36bcc20190d0c9132e6de97e9f11837` | Untrusted instruction-like body content |
| `combined-m002-m003` | `conversations/aurora-deployment-review.md` | 516 | `7d64565113bfd63fee441affdeff362e5e4b9f203856f40c0443bcba65ecf595` | M-002 component |
| `combined-m002-m003` | `tracking-topics/aurora-readiness.md` | 349 | `0991630916db6644418483ae318905b694c5dd435709ce8765e803d4bfdac439` | M-003 component |

The byte counts and hashes above were measured during disconnected fixture validation on 2026-08-28. Exact baseline-delta observations are recorded in the corresponding fixture validation result.
