# Decision: Use Work IQ to inform synthetic testing from the user's perspective

- **Date:** 2026-08-28
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Prior Skill static review](../findings/2026-08-28-prior-skill-static-review.md)

## Context

The user wants to work with Copilot Cowork using authorized Work IQ context so Compass content reflects the user's work perspective. Graph Governor still needs controlled, reproducible tests that do not expose real Microsoft 365 content or make unverified connected-write claims.

## Decision

Add a bounded **Perspective Discovery** phase to the Installation Interview before creating the synthetic graph:

1. A separately packaged experimental Installation Interview slice runs in Copilot Cowork.
2. After displaying an exact plan and receiving explicit `Run` authorization, it retrieves read-only Work IQ evidence from the signed-in user's Email and Teams activity for the previous seven complete local calendar days.
3. Retrieval is limited to 10 inspected evidence units per source and 20 total. The Skill stops for narrowing rather than exceeding a limit.
4. It derives a concise perspective brief containing candidate role language, work categories, customer or stakeholder relationship patterns, recurring topic shapes, and meaningful activity signals.
5. Every derived item remains a proposal. The user confirms, edits, excludes, or generalizes each item before it can inform test design.
6. Raw messages, transcripts, excerpts, addresses, links, source identifiers, tenant identifiers, participant names, and unconfirmed organization names are neither returned in the brief nor stored in Dexter.
7. The confirmed brief is transformed into fictional test content. Real names and facts are replaced; only approved structural patterns and preferred language are carried forward.
8. Graph Governor receives only the resulting synthetic graph. It receives no Work IQ access and no raw or confirmed real-work evidence.

The Perspective Discovery slice is read-only. It does not create the Compass graph, write OneDrive files, send messages, modify Microsoft 365 records, or invoke Graph Governor.

The user explicitly accepted this boundary on 2026-08-28. This acceptance establishes the design direction only; it does not authorize Skill implementation, package creation, Cowork upload, Work IQ retrieval, or test execution.

## Alternatives considered

- **Give Graph Governor direct Work IQ access:** Rejected because graph validation does not require evidence retrieval and the extra access would obscure its responsibility boundary.
- **Copy real Work IQ content into the fixture:** Rejected because it would create privacy, reproducibility, and repository-handling risks.
- **Use a generic synthetic fixture only:** Retained as a fallback, but it would not reflect the user's vocabulary and work patterns as closely.
- **Use the received Installation Beta 1 unchanged:** Rejected because static review found mixed Installation and Daily Scan responsibilities and missing current bootstrap contracts.

## Consequences

- Perspective discovery and Graph Governor validation remain independently testable.
- Synthetic scenarios can feel relevant without containing Microsoft 365 content.
- Work IQ availability and retrieval behavior require their own Cowork evidence; success cannot be inferred from documentation or prior-project claims.
- A connected Perspective Discovery run requires exact-package, environment, source, date, limit, retention, and no-write authorization.
- If Work IQ is unavailable or incomplete, the Skill reports the limitation and continues only with user-supplied perspective information; it does not substitute web, OneDrive, calendar, or broader enterprise search.

## Follow-up

- Define and separately authorize an experimental Installation Interview Perspective Discovery package.
- Execute the linked test plan before using any derived brief to author synthetic fixture content.
