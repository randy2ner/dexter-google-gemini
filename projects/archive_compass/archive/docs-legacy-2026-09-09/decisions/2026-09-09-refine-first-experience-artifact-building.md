# Decision: Refine first-experience artifact building

- **Date:** 2026-09-09
- **Status:** accepted
- **Decider:** User / product owner
- **Stage:** Artifact-first production shaping
- **Applies to:** Compass artifact proposals, Person email capture, and OneDrive writes

## Context

The first production shaping experience exposed two unnecessary constraints. Installation created a disposable write/read/delete probe even though Cowork has difficulty deleting OneDrive files and the approved bootstrap writes can verify write capability directly. Artifact building also treated complete Person names as the only useful user-supplied identity details and described email addresses as narrow correlation metadata, which caused Compass to resist an ordinary request to add People by email address.

The experience also clarified a broader product behavior: Compass should use its understanding of the user's work and authorized Work IQ context to interpret what belongs in an artifact, offer that interpretation as an editable suggestion, and let the user confirm or revise it before anything becomes authoritative.

## Decision

1. Installation does not create, read back, or delete a disposable probe file.
2. The approved bootstrap is the write-capability verification. Installation writes and verifies configuration first, then continues through the approved files. A refusal stops further writes and is reported truthfully; any completed or uncertain effect enters the existing recovery path.
3. A Person still requires meaningful first and last names and a stable Compass ID. One or more normalized email addresses are accepted, useful Person attributes when the user supplies them or authorized Work IQ exposes them for the approved purpose.
4. Email addresses support recognition and source correlation but do not replace Compass identity. UPN remains excluded as managed Person data; Compass does not reinterpret an email address as a request to collect UPN.
5. Before writing an artifact, the responsible Skill interprets the user's request using direct input, accepted graph context, and authorized relevant Work IQ. It presents its best useful artifact suggestion, including proposed content, fields, and relationships, in ordinary language.
6. The user confirms, changes, or rejects the suggestion. Interpretation reduces the user's drafting burden but never becomes graph authority without confirmation.
7. Skills ask a follow-up question only when a material ambiguity cannot be represented safely in an editable suggestion.
8. For writes inside the selected OneDrive graph, Compass addresses each target by its graph-root-relative path, not by OneDrive item ID. Root selection or resolution may use Cowork-exposed folder identity, but that identity is not the file-write addressing mode. This rule is unrelated to Email or Teams Conversation identity.

## Consequences

- Installation no longer depends on deletion for a normal first run.
- Bootstrap failure may leave only effects that were explicitly approved; effect accounting and user-led recovery remain mandatory.
- Person proposal previews include normalized email addresses when present.
- Artifact-building interactions become suggest-and-confirm rather than schema-led data collection.
- Existing completed test evidence remains historical and is not rewritten. The next controlled candidate must test these revised behaviors.
- Write handoffs and previews continue to name exact graph-root-relative paths, and the writer uses those paths when creating or replacing files.
