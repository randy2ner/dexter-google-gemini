# Cowork session kit: Compass experience-led rehearsal

## Session control

- **Status:** Curator review completed with zero changes; choice ambiguity was clarified and a direct Graph Governor health scan remains pending
- **Owner/tester:** User / product owner
- **Candidate:** Exact Gate 0 package set below
- **Orchestration:** `compass-work-memory-lifecycle` `0.1-beta-candidate`
- **Graph:** Disposable `compass-beta-graph-v1` materialized copy
- **Evidence:** Fixed fictional input only for this rehearsal
- **Authority:** [One bounded fictional-data rehearsal is authorized](../decisions/2026-09-02-authorize-experience-led-rehearsal.md). Development beta and real connected content remain unauthorized.

## Exact packages

| Import artifact | SHA-256 |
| --- | --- |
| [compass-installation-interview-v0.1.1-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-installation-interview-v0.1.1-beta-candidate.skill) | `e3f2363fa32c22cc02a3724ed92f9ea2da1a1cf842f23b80d3d14bd5566654ec` |
| [compass-daily-scan-v0.1.0-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-daily-scan-v0.1.0-beta-candidate.skill) | `b18e91a50b3c264fdc9b82264e10b8037ea41269a035be0a425f3cc50c2fd59f` |
| [compass-tracking-topic-interview-v0.1.0-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-tracking-topic-interview-v0.1.0-beta-candidate.skill) | `9e9b84884f78e3abca185a957bf7fbe43da1ebe688c3d5a315cd68f46ad221d7` |
| [compass-curator-v0.1.0-beta-candidate.skill](../../skill-exchange/ready-for-test/compass-curator-v0.1.0-beta-candidate.skill) | `96f14d27f034a2804424b31b4bbf8b6e9b847bdcf1d1425dc2f3dbbd4aadf49e` |
| [graph-governor-v0.2.0-beta-candidate.skill](../../skill-exchange/ready-for-test/graph-governor-v0.2.0-beta-candidate.skill) | `e0be28fb7d8c2ee1a0b21ace26fb35b6fc6ac4cd27218bae6348018c72b587c3` |

Import behavior and package order are currently unobserved. Record what Cowork actually requires; do not invent a dependency order.

## Setup boundary

The VS Code integrated automation browser was blocked by Conditional Access and must not be used to circumvent organizational policy. The product owner operates Cowork in an approved managed browser or client; the laboratory assistant may support the local package, fixture, inspection, and evidence-recording steps.

Before invocation, fill in the exact values visible to the operator:

| Boundary | Session value |
| --- | --- |
| Cowork environment/account | |
| Imported package names shown by Cowork | |
| Disposable graph root | `C:\Users\randt\OneDrive - Microsoft\SampleCompass`; verified baseline match and explicitly authorized for this rehearsal |
| External backup | `projects/compass/test-data/compass-beta-graph-v1/restore-baseline/graph/` or an explicitly recorded verified backup outside the graph root |
| Fixed fictional evidence | `projects/compass/test-data/compass-beta-graph-v1/inputs/daily-scan-2026-08-24.md` |
| Optional baseline transfer | `projects/compass/test-data/compass-beta-graph-v1/handoff/compass-beta-graph-v1-baseline.zip`; SHA-256 `e219c45332e1502d9556cd11eb00b7e2b26dd19dc41edeec68dae20ea698df8b` |
| Connected capabilities visible | |
| Graph writes authorized for this run | Yes, only beneath the [exact accepted synchronized-folder boundary](../decisions/2026-09-02-propose-sample-compass-rehearsal-graph.md) and only for fictional rehearsal effects approved by the user |
| Connected source content authorized | No |
| Development beta authorized | No |

The first invocation established that Cowork cannot access the local Windows graph path. Do not reuse that path as the runtime target. Before resuming, record an exact dedicated location visible to Cowork, its external backup, and a separate authorization for writes to that location.

The baseline transfer ZIP contains only `README.md`. Use it only to seed a dedicated accessible folder. The ZIP attachment itself is not the graph root, and the local `restore-baseline/` remains the authoritative external recovery source.

Do not use a personal or production graph. Do not retain source content, credentials, tenant identifiers, full transcripts, or identifying work details in Dexter.

## Conversational starting point

Start naturally with Installation Interview:

> Help me set up Compass around the work I am responsible for. Keep this conversational, show me what you propose before retaining anything, and make it easy for me to correct, skip, pause, or reject suggestions. For this rehearsal, use only the designated fictional evidence and disposable graph.

After that, converse as yourself. Ask Compass for help when it feels natural rather than following a script. Useful transitions include asking it to review the fictional day, help organize one thread, tell you what deserves attention, or explain what it changed. They are prompts, not required wording.

Use the fixture as a safe scenario seed, not an answer key. Accept or correct reasonable Cowork inference as you would during real use. Do not interrupt the experience to enforce exact timezone, wording, timestamp, filename, ordering, or scan-window details unless the difference materially affects meaning, trust, or graph integrity.

## Operator notes during the experience

Record only facts needed to preserve evidence integrity:

- actual Skill names Cowork shows or invokes;
- any unexpected substitution or broken handoff;
- approvals given and material effects reported;
- file effects observed outside Cowork;
- any stop condition and preserved recovery state.

Do not interrupt the user to complete a checklist unless a stop condition may have occurred.

## Compact observation sheet

### Run identity

- **Date/time:**
- **Cowork environment/version shown:**
- **Exact packages confirmed:** yes / no / uncertain
- **Graph and backup confirmed:** yes / no / uncertain
- **Journey reached:** setup / daily memory / organization / review / verification
- **Terminal outcome reported by Compass:**
- **Observed material effects:**

### User experience

- **One moment that helped:**
- **One moment of friction or mistrust:**
- **One correction or redirection I made:**
- **Did it feel like one assistant?** yes / partly / no — why:
- **Did I understand what it read, proposed, changed, and retained?** yes / partly / no — why:
- **Would I use it again in development beta?** yes / after one change / no — why:

### Safety and integrity

| Observation | Yes | No | Unobserved | Note |
| --- | --- | --- | --- | --- |
| Approval preceded consequential writes | | | | |
| Reported effects matched external inspection | | | | |
| Identity and history remained understandable | | | | |
| Rejected or out-of-scope content was not retained | | | | |
| Pause, correction, rejection, or stop remained available | | | | |
| Graph remained restorable | | | | |

### Conclusion

Choose one:

- `continue to beta decision`
- `focused follow-up needed`
- `revise candidate`
- `stop`

Reason:

## Evidence handling

Create one dated result after the run. Keep direct observations separate from conclusions. Do not convert blank or unobserved rows into passes, and do not claim beta confidence from package inspection alone.