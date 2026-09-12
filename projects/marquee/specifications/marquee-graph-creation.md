# Marquee Specification

## Document control

- **Status:** draft for review
- **Version:** 0.2
- **Owner:** User / product owner
- **Created:** 2026-09-09
- **Last updated:** 2026-09-11
- **Governed by:** [Marquee Project Charter](../CHARTER.md) and [`PR-001`, `PR-002`, `PR-008`](../PRD.md#product-requirements-and-acceptance-signals)
- **Verified by:** [Graph Consent and Creation](../test-plans/01-graph-consent-and-creation.md); [Knowledge Artifact Quality](../test-plans/02-knowledge-artifact-quality.md); [Unconfirmed Knowledge Follow-up](../test-plans/06-unconfirmed-knowledge-follow-up.md); [Outlet Guidance Value and Accuracy](../test-plans/07-outlet-guidance-value-and-accuracy.md); [CareerHub Development Plan](../test-plans/08-careerhub-development-plan.md); [Manager OneNote Questionnaire](../test-plans/09-manager-onenote-questionnaire.md)
- **Candidate implementation:** [Marquee Skill](../skills/marquee/SKILL.md) implements this draft for evaluation. Implementation and packaging do not establish acceptance or runtime success.
- **Implementation authority:** None. This Specification records intended behavior for review.

## 1. Create the Marquee graph

### Purpose

Marquee's first capability is to establish an Obsidian-style Markdown graph in a OneDrive folder confirmed by the user. This graph is the user-managed knowledge source Marquee will use for career knowledge and repeatable Outlet guidance.

### User experience

1. Marquee explains that it needs a OneDrive folder for the user's Marquee graph.
2. The user selects or confirms the graph's root folder.
3. Marquee presents its short default folder list and explains what each folder is intended to hold.
4. Marquee asks whether the user wants to add or edit anything in the starting structure.
5. Marquee shows the agreed starting structure before creating it.
6. After confirmation, Marquee creates the starting folders inside the confirmed graph root.
7. Marquee reports the root and folders it created. If creation is partial or blocked, it reports the actual result and does not claim the graph is ready.

Marquee uses natural language throughout. The user is not required to understand Obsidian, Markdown graph design, or storage mechanics to make the decision.

### Default folders

| Folder | Intended knowledge |
| --- | --- |
| `Profile` | The user's evolving professional identity, strengths, interests, and career story. |
| `Highlights` | Accomplishments, praise, contributions, outcomes, and other moments worth remembering. |
| `Goals` | Career directions, development goals, desired experiences, and progress. |
| `Perspectives` | Feedback and perspective knowledge the user wants Marquee to retain. |
| `Outlets` | Guidance for repeatable career exercises such as CareerHub plans, manager questionnaires, reviews, and LinkedIn work. |

These folders are a useful starting structure, not a fixed or complete schema. Marquee expects the graph to change as the user's career knowledge grows and new Outlets emerge.

### Requirements

| ID | Requirement | Acceptance criterion |
| --- | --- | --- |
| GRAPH-001 | Marquee uses a OneDrive graph root selected or confirmed by the user. | The displayed target matches the folder the user approved before creation begins. |
| GRAPH-002 | Marquee proposes the five default folders and their purposes. | The user can understand what each proposed folder will contain. |
| GRAPH-003 | The user may adapt the starting structure. | Marquee asks whether the user wants to add or edit anything before creating the default folders. |
| GRAPH-004 | Marquee confirms the proposed starting structure before writing. | No graph folder is created before the user confirms the root and starting structure. |
| GRAPH-005 | Marquee creates only the agreed starting structure within the confirmed root. | The resulting folders match the confirmed proposal and no Marquee folder is created outside the root. |
| GRAPH-006 | Marquee reports the actual creation result. | The user is told which root and folders were created and any folder that was not created. |
| GRAPH-007 | The graph remains user-managed and inspectable. | The user can browse, rename, add, or manage its folders and Markdown artifacts through OneDrive or an Obsidian-compatible view. |
| GRAPH-008 | The graph may evolve with use. | Marquee can propose new folders and files when new knowledge or a new Outlet makes them useful. |
| GRAPH-009 | Later structural changes remain transparent and user-agreed. | Before adding or changing graph structure, Marquee explains what it proposes and why, and the user can accept or edit the proposal. |

### Evolution over time

The confirmed setup is the graph's starting point, not its permanent shape. As Marquee learns what information is useful, it may propose additional folders or Markdown files to organize new kinds of career knowledge. When the user introduces a repeatable exercise, Marquee may propose the folders and files needed for that Outlet and its guidance.

Marquee explains each proposed addition or structural change in natural language and asks whether the user wants to accept or edit it. The graph evolves through use and agreement rather than through a universal folder design chosen in advance.

New structure remains within the user-confirmed Marquee root. Marquee does not reorganize or remove existing knowledge merely because a different structure later appears preferable.

### Existing-folder behavior

If the confirmed root already contains files or folders, Marquee first describes what it can observe and proposes only the additions or changes needed for the agreed structure. It does not delete, rename, move, replace, or reorganize existing content without the user's specific agreement.

An existing folder with the agreed purpose may be reused. Marquee does not create a duplicate merely because its name differs from the default.

### Failure and cancellation

- Cancellation before creation leaves the target unchanged.
- An unavailable or unconfirmed target blocks creation.
- A name conflict or uncertain existing purpose returns to the user for agreement.
- Partial creation is reported folder by folder and remains incomplete until the user decides how to proceed.
- Marquee never reports the graph as ready unless the confirmed structure exists in the confirmed root.

### Boundaries

Creating the graph authorizes only the agreed folder structure inside the confirmed root. It does not authorize Marquee to populate career knowledge, retrieve Work IQ, create Outlet guidance, modify existing content, publish material, or complete an Outlet exercise. Those behaviors will be specified separately as the living Specification develops.

## Open questions

None are required to review this first capability. Initial customization is resolved during setup, and later additions are resolved when growing knowledge or a new Outlet creates a reason for them.

## Revision history

| Version | Date | Change and reason |
| --- | --- | --- |
| 0.2 | 2026-09-09 | Clarified that adaptability primarily means creating useful new folders and files over time as career knowledge and Outlets grow. |
| 0.1 | 2026-09-09 | Defined the user-confirmed creation of an adaptable default Marquee graph as the first specified capability. |