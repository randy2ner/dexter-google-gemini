# Production graph shaping technique ledger

## Document control

- **Status:** living; one technique recorded
- **Started:** 2026-09-08
- **Owner:** User / product owner
- **Plan:** [Artifact-first production shaping](../specifications/2026-09-08-artifact-first-production-shaping-plan.md)

## Recording boundary

This ledger records generalized methods and operational observations only. Keep identifying work content on the approved managed surface. Do not include names, message text, document titles, source links, tenant details, graph content excerpts, or other sensitive evidence.

A successful entry means the method helped produce a reviewed target artifact. It does not establish that a Compass Skill can reproduce the result.

## Technique entries

### TECH-2026-09-09-001 — Address OneDrive writes by path

- **Target artifact type:** Compass configuration YAML
- **Generalized intent:** Create the first approved configuration file inside the selected OneDrive graph.
- **Method or Cowork surface:** Cowork OneDrive file upload/write
- **Generalized conversational pattern:** Address the target file through the selected folder path and graph-root-relative file path.
- **Source capability types used:** OneDrive folder and file write
- **Result category:** partially successful
- **Quality dimensions satisfied:** The path-addressed retry created the intended file immediately.
- **Corrections required:** Replace folder item-ID addressing with folder-path addressing.
- **Friction or failure pattern:** The first upload attempt failed when the folder was addressed by item ID.
- **Implied Skill behavior:** Resolve the selected graph root through Cowork as needed, but address graph file writes by selected-root-relative path rather than OneDrive item ID.
- **Provenance class:** Operator-reported production shaping observation
- **Confidence and limits:** One failed item-ID attempt and one immediately successful path retry for configuration creation in the current environment. This supports a local write-transport rule; it does not concern or test Email or Teams Conversation IDs and does not prove universal OneDrive behavior.

Use this compact shape for each future entry:

```markdown
### TECH-YYYY-MM-DD-NNN — Short method name

- **Target artifact type:**
- **Generalized intent:**
- **Method or Cowork surface:**
- **Generalized conversational pattern:**
- **Source capability types used:**
- **Result category:** successful / partially successful / unsuccessful
- **Quality dimensions satisfied:**
- **Corrections required:**
- **Friction or failure pattern:**
- **Implied Skill behavior:**
- **Provenance class:**
- **Confidence and limits:**
```

## Synthesis queue

The first observation is sufficiently discriminating for the current environment to prefer graph-root-relative path addressing for writes. The accepted first-experience decision records this environment-specific transport rule. Additional observations should test whether the same behavior holds for create and replace operations across object types.
