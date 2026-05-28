# Orchestrator seed

Copy the **Seed prompt** into a new Cursor chat to scaffold the layout. Use the **user commands** in any project that has `build-plan/` and `QA-plan/`.

---

## The loop (one phase at a time)

```text
Pick phase N
    ↓
Read build-plan/phases/*-phase-N-*.md  →  BUILD (when user asks to build)
    ↓
Read QA-plan/*-phase-N-*.md            →  TEST (when user asks to QA / test)
    ↓
┌─ PASS ──────────────→ write QA-results, update index, phase done
├─ PASS_WITH_RISKS ───→ write QA-human-test/*.html, user runs checklist, reports back
├─ FAIL ──────────────→ edit BUILD file (Fix round n), rebuild, retest until PASS
└─ BLOCKED ───────────→ stop; tell user what is missing
```

**Rules**

- **One phase** per run unless the user names another.
- **Build file** = what to implement. **QA file** = goals, outcomes, pass/fail.
- **FAIL** → update the **build file** (`## Fix round <n>`), then build again and test again.
- **PASS_WITH_RISKS** → create an **HTML** human QA checklist; phase not closed until the user completes it (or explicitly waives).
- Do not start phase N+1 until phase N is `pass` (or `pass_with_risks` with human test done).

**Gate decisions:** `pass` | `pass_with_risks` | `fail` | `blocked`

---

## User commands

The orchestrator should recognize natural commands like these (phase number may vary):

| Command                                          | Orchestrator does                                                                                                                                                               |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Build phase 2 with the orchestrator**          | Read build file for phase 2 → implement in scope → run build validations → report (no QA gate unless user also asked for test).                                                 |
| **QA test phase 2 with the orchestrator**        | Read QA file for phase 2 → test against all goals/outcomes → decide pass / pass_with_risks / fail / blocked → act per decision (no new build unless FAIL requires a fix round). |
| **Build and test phase 2 with the orchestrator** | Build phase 2, then QA test phase 2 in the same run (full loop including fix rounds on fail).                                                                                   |

Also support:

- **Build and test next phase with the orchestrator** — next phase not `pass` in `QA-plan/QA-results/00-index.md` per `project-plan/09-build-order.md`.
- **Human test done for phase 2** — user finished the HTML checklist; record evidence and close `pass_with_risks`.

Parse the phase number from the user message. If omitted on “next phase”, infer from the index.

---

## Folder layout

```text
build-plan/phases/NN-phase-NN-<slug>.md
QA-plan/NN-phase-NN-<slug>.md
QA-plan/QA-results/
QA-plan/QA-human-test/          # HTML checklists only (pass_with_risks)
project-plan/09-build-order.md
QA-plan/QA-results/00-index.md
.cursor/skills/phase-orchestrator/SKILL.md
.cursor/rules/orchestration-*.mdc
AGENTS.md
```

---

## Run prompt (project already scaffolded)

```markdown
You are the **phase orchestrator**.

Interpret the user’s request:

- **Build only** → implement from `build-plan/phases/*phase-<N>*`; run validations in that file.
- **QA test only** → verify every goal/outcome in `QA-plan/*phase-<N>*`; record evidence; gate decision.
- **Build and test** → build, then QA test, in one run.

Phase <N> comes from the user’s message, or “next” from `QA-plan/QA-results/00-index.md` + `project-plan/09-build-order.md`.

After QA test:

- **PASS** → `QA-plan/QA-results/YYYY-MM-DD-phase-<N>-qa-results.md` + update `00-index.md`.
- **PASS_WITH_RISKS** → create `QA-plan/QA-human-test/phase-<N>-<slug>.html` (HTML checklist template below). Ask the user to open the file, complete every item, and reply with results. Do not mark the phase closed until done or waived.
- **FAIL** → append `## Fix round <n>` to the **build file**, rebuild if build was in scope, retest until PASS or BLOCKED.
- **BLOCKED** → stop; list what the user must provide.

You own build-file updates and human-test HTML—not the subagents.

Start from the user’s latest message.
```

---

## Seed prompt (bootstrap)

````markdown
Bootstrap a **phase orchestrator** in this workspace.

Ask up to 3 questions if needed: product name, codebase roots, number of phases (default 3).

Create:

1. `.cursor/skills/phase-orchestrator/SKILL.md` — one phase; build / QA / build+test modes; FAIL → build file fix rounds; PASS_WITH_RISKS → HTML in `QA-plan/QA-human-test/`.

2. `.cursor/rules/orchestration-sources.mdc` (`alwaysApply: true`) — build from `build-plan/phases/*`; test from `QA-plan/*`; sequence from `project-plan/09-build-order.md`; no advance without pass (or human test complete after pass_with_risks).

3. `.cursor/rules/orchestration-output.mdc` (`alwaysApply: true`) — FAIL: edit build file, rebuild, retest; PASS_WITH_RISKS: **HTML** human-test file; PASS: QA-results + index.

4. `AGENTS.md` — loop, folders, user commands table (build / QA test / build and test).

5. `project-plan/09-build-order.md` — phase list.

6. Paired files per phase: `build-plan/phases/01-phase-01-<slug>.md` + `QA-plan/01-phase-01-<slug>.md`.

7. `QA-plan/QA-results/00-index.md`, `QA-plan/02-release-decision-model.md`, `QA-plan/QA-human-test/README.md`.

Keep phase count small (3–8). Keep files short.

### Skill (embed this)

```markdown
---
name: phase-orchestrator
description: Build and/or QA test one phase from build-plan and QA-plan; HTML human checklist on pass_with_risks.
---

# Phase orchestrator

## Commands

| User says                                    | Do              |
| -------------------------------------------- | --------------- |
| Build phase N with the orchestrator          | Build only      |
| QA test phase N with the orchestrator        | Test only       |
| Build and test phase N with the orchestrator | Build then test |

## FAIL

Append `## Fix round <n>` to the build file. Rebuild and retest until pass or blocked.

## PASS_WITH_RISKS

Create `QA-plan/QA-human-test/phase-N-<slug>.html` using the HTML template. Tell the user to open it in a browser, complete the checklist, and report back.

## PASS

Write `QA-plan/QA-results/YYYY-MM-DD-phase-N-qa-results.md` and update `00-index.md`.
```
````

### Human QA HTML template

Create `QA-plan/QA-human-test/phase-NN-<slug>.html` (never Markdown for human tests). Use this structure:

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="utf-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1" />
		<title>Phase NN — Human QA</title>
		<style>
			body {
				font-family: system-ui, sans-serif;
				max-width: 52rem;
				margin: 2rem auto;
				padding: 0 1rem;
				line-height: 1.5;
			}
			h1 {
				font-size: 1.35rem;
			}
			.meta {
				color: #444;
				font-size: 0.95rem;
				margin-bottom: 1.5rem;
			}
			.why {
				background: #f6f6f6;
				padding: 1rem;
				border-radius: 6px;
				margin-bottom: 1.5rem;
			}
			ol.steps {
				padding-left: 1.25rem;
			}
			ol.steps li {
				margin-bottom: 1.25rem;
			}
			.expected,
			.record {
				margin: 0.35rem 0;
			}
			.expected strong,
			.record strong {
				display: inline-block;
				min-width: 5.5rem;
			}
			.report {
				background: #e8f4fc;
				padding: 1rem;
				border-radius: 6px;
				margin-top: 2rem;
			}
			input[type="checkbox"] {
				transform: scale(1.15);
				margin-right: 0.35rem;
			}
		</style>
	</head>
	<body>
		<h1>Phase NN — Human validation</h1>
		<p class="meta"><strong>Gate:</strong> pass_with_risks &nbsp;|&nbsp; <strong>Build:</strong> build-plan/phases/… &nbsp;|&nbsp; <strong>QA spec:</strong> QA-plan/…</p>

		<section class="why">
			<h2>Why you need to run this</h2>
			<ul>
				<li><!-- agent fills: what automation could not verify --></li>
			</ul>
		</section>

		<h2>Checklist</h2>
		<p>Complete every item. Check the box when done. Record evidence in the notes column or in chat.</p>
		<ol class="steps">
			<li>
				<label><input type="checkbox" /> <strong>Step 1 title</strong></label>
				<p class="expected"><strong>Do:</strong> Clear instruction what to click, run, or observe.</p>
				<p class="expected"><strong>Expected:</strong> What success looks like.</p>
				<p class="record"><strong>Record:</strong> e.g. screenshot, session ID, command output.</p>
			</li>
			<!-- repeat per validation item -->
		</ol>

		<section class="report">
			<h2>Report back in chat</h2>
			<p>Reply with: <code>Human test done for phase NN</code> and for each step: pass/fail + evidence links or pasted output.</p>
			<p>The orchestrator will update QA-results and close the phase (or open a fix round on failure).</p>
		</section>
	</body>
</html>
```

### Build file fix round (append on FAIL)

```markdown
## Fix round 1

**QA decision:** fail
**Date:** YYYY-MM-DD

### Required fixes

- [ ] …

### Re-test focus

- …
```

### QA-human-test README

```markdown
# Human QA (HTML)

When automated QA returns **pass_with_risks**, the orchestrator adds `phase-N-<slug>.html` here.

Open the file in a browser, complete every checkbox, then tell the orchestrator: `Human test done for phase N` with evidence.
```

Begin bootstrap now.

````

---

## Phase file templates

**Build** — `build-plan/phases/01-phase-01-<slug>.md`:

```markdown
# Phase 1: <title>

**QA file:** QA-plan/01-phase-01-<slug>.md

## Objective
…

## In scope
- …

## Out of scope
- …

## Tasks
- [ ] …

## Exit criteria
- …

## Validation
- `command here`
````

**QA** — `QA-plan/01-phase-01-<slug>.md`:

```markdown
# Phase 1 QA: <title>

**Build file:** build-plan/phases/01-phase-01-<slug>.md

## QA goals

- …

## Outcomes (check each)

- [ ] …

## Pass criteria

All outcomes met with evidence.

## Fail conditions

- …
```

---

## AGENTS.md snippet (for bootstrap)

```markdown
# Agent workflow

## Orchestrator commands

- `Build phase N with the orchestrator` — implement build file only
- `QA test phase N with the orchestrator` — run QA file checks and gate
- `Build and test phase N with the orchestrator` — full loop for phase N

## Human QA

On **pass_with_risks**, open `QA-plan/QA-human-test/phase-N-*.html` in a browser, complete the checklist, then: `Human test done for phase N`.
```
