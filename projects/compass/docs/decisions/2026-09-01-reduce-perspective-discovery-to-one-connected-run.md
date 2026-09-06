# Decision: Reduce Perspective Discovery to one connected run

- **Date:** 2026-09-01
- **Status:** accepted
- **Deciders:** User / product owner
- **Related findings:** [Perspective Discovery package inspection](../test-results/2026-09-01-perspective-discovery-package-inspection.md)

## Context

The reviewed Perspective Discovery package is ready for connected-test scope review. The original test plan split authorization, bounded retrieval, candidate review, minimization, source gaps, injection resistance, and fictionalization handoff across seven scenarios. Executing each as a separate connected run would repeatedly expose real work context and add process cost without proportionate evidence value.

On 2026-09-01, the user directed Project Dexter to reduce the seven-scenario plan to one lean, privacy-bounded connected run before requesting authorization.

## Decision

Replace the seven planned standalone connected executions with one staged scenario, [PD-LEAN-001](../scenarios/workiq-perspective-discovery/pd-lean-001-bounded-discovery-session.md). One Cowork conversation will exercise the authorization gate, bounded Email and Teams retrieval, user disposition of naturally supported candidates, minimized handoff, honest source-gap behavior when encountered, and terminal effect accounting.

The original PD-001 through PD-007 files remain preserved as unexecuted design assertions and traceability references. They are not separate exit requirements for the lean slice. Injection resistance and source-gap behavior are scored only when naturally observable; the test must not create live injection content, alter permissions, or manufacture a source failure.

Retained Dexter evidence must exclude raw messages, excerpts, names, addresses, links, source identifiers, participant identities, tenant details, timestamps tied to activity, distinctive facts, screenshots containing work content, and evidence-to-pattern mappings. A candidate or handoff may be retained only after human minimization review. Unsafe output is recorded only as rejected and not retained.

This decision changes the test plan only. It does not change the accepted Skill specification, package bytes, or source. It does not authorize Cowork import, Work IQ retrieval, Microsoft 365 access, or execution.

## Alternatives considered

- **Run all seven scenarios separately:** Rejected because repeated access increases privacy exposure and test fatigue.
- **Skip connected testing:** Rejected because package inspection cannot establish authorization gating, Work IQ availability, minimization, or runtime behavior.
- **Create synthetic live Email or Teams injection content:** Rejected because modifying a live work environment to manufacture evidence is outside scope and unnecessary for the primary decision.
- **Retain the complete Cowork transcript:** Rejected because it may contain source-derived or identifying work content.

## Consequences

- One connected conversation becomes the complete primary runtime slice.
- The run may honestly finish `completed`, `completed-with-source-gaps`, `empty`, `blocked`, or `failed`; evidence quality is assessed without forcing a successful-data outcome.
- Unobserved optional branches remain explicit confidence gaps rather than generating more runs automatically.
- A later additional run requires a specific unresolved decision, new authorization, and privacy review.

## Follow-up

- Project Dexter: register the lean scenario and revise the test plan and scenario index.
- User / product owner: review the lean scope, provide the IANA timezone needed to establish exact dates, and separately authorize the exact package and one connected conversation.