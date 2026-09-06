# Prior Skill artifact register

## Scope

This register identifies artifacts supplied from the unfinished prior effort. Registration preserves provenance and supports review; it does not accept prior responsibilities, runtime claims, compatibility, or test readiness.

## Intake record

- **Received:** 2026-08-28
- **Source:** User-provided prior unfinished effort
- **Intake location:** `skill-exchange/incoming/`
- **Inspection type:** Static archive and text review only
- **Cowork execution:** Not performed
- **Artifact modification:** None

## Artifacts

| Artifact | Bytes | SHA-256 | Observed package contents | Claimed identity | Static disposition |
| --- | ---: | --- | --- | --- | --- |
| `compass-daily-scan-beta-1.skill` | 8,343 | `508c2265c730e047954eb21fe7acc4117e7b7989337a78d9520bbd8896136285` | Root `SKILL.md`; `references/behavior-contract.md`; `references/synthetic-eval-cases.md` | Compass Daily Scan Beta 1 | Revise |
| `compass-knowledge-graph-installation-beta-1.skill` | 10,047 | `59cc4f5356875ce97faafb6ee38ecb150e23947a4b1fd0c9c0d4058870308d83` | Root `SKILL.md` only | Compass Knowledge Graph Installation Beta 1 | Split and revise |
| `compass-tracking-topic-conversation.skill` | 7,980 | `1edf384ae164179162ddee85da2adfd962a70fa1869ea087bf97ebd354810f3d` | Root `SKILL.md`; `references/behavior-contract.md`; `references/synthetic-eval-cases.md` | Compass Tracking Topic Conversation Beta 2 | Revise |

## Static safety observations

- All three artifacts are ZIP-compatible archives with a root `SKILL.md`.
- Every archive member is Markdown text. No executable, script, link, binary payload, absolute path, or path-traversal member was observed.
- A pattern scan found no apparent password, API key, client secret, access token, tenant identifier, or individual email address.
- The Installation text contains the generic suffix `@microsoft.com` as a classification rule. It is not an observed personal address or tenant identifier.
- Static inspection cannot establish runtime safety, data handling, Cowork compatibility, or conformance.

## Integrity rule

The listed hashes identify the received specimens. Keep them unchanged in `incoming/`. Any revised candidate must be created as separately versioned Skill source and packaged as a new artifact; it must not replace or rewrite these specimens.

## Related review

See the [2026-08-28 prior Skill static review](../findings/2026-08-28-prior-skill-static-review.md).
