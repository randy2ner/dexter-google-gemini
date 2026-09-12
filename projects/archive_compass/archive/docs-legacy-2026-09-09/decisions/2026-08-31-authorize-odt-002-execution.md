# Decision: Authorize ODT-002 execution

- **Date:** 2026-08-31
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [ODT-001 partial result](../test-results/2026-08-31-odt-001-isolated-folder-enumeration.md)

## Context

The user reviewed the exact ODT-002 revision 1 prompt and procedure after separately authorizing scenario creation. The existing isolated fictional baseline remains the intended test object. ODT-001 established partial native-picker evidence but did not preserve directory-qualified relative paths or independently demonstrate readability.

## Decision

Authorize one execution of [ODT-002 revision 1](../scenarios/onedrive-transport/odt-002-native-picker-hierarchy-and-readability.md) using the existing isolated fictional baseline and its documented read-only boundaries.

The execution may:

- verify the isolated copy's local inventory, bytes, and SHA-256 values before and after Cowork access;
- start one clean Cowork session;
- select only `gg-syn-001-valid-baseline` through Cowork's native OneDrive file-or-folder picker;
- submit the exact ODT-002 revision 1 prompt once; and
- preserve Cowork's complete response and visible capability evidence.

The execution does not authorize prompt variation, retry, another folder or account, broader OneDrive or SharePoint access, parent or sibling access, search, recent files, email, Teams, Work IQ, file modification, repair, normalization, Graph Governor upload or invocation, or any real or production data.

## Alternatives considered

- **Defer execution:** Not selected by the user.
- **Proceed directly to Graph Governor:** Rejected because hierarchy and readability transport remain under test.
- **Broaden access if native enumeration is incomplete:** Rejected; incomplete capability must be recorded honestly.

## Consequences

- One bounded native-picker run may proceed after the pre-test check passes.
- Any outside-root access or external change stops the experiment and is classified as failure.
- A blocked or partial result cannot be retried under this authorization.
- The result supports only the behavior directly observed in the tested Cowork environment.

## Follow-up

- Project Dexter: complete and record the pre-test local integrity check.
- User / product owner: execute the exact prompt once and return the complete response and visible environment details.
- Project Dexter: perform the post-test local integrity check and record the immutable result.