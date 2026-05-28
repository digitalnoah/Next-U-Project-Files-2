---
name: phase-orchestrator
description: Build and/or QA test one phase from build-plan and QA-plan; HTML human checklist on pass_with_risks.
---

# Phase orchestrator

**Product:** Vibe Code Academy landing page  
**Codebase root:** `demo-1B/` (`prototype.html` deliverable)  
**Planning context:** `demo-1C-orchestrator/phase-plans/00-planning-decisions.md`, source files in `demo-1B/0*.md`

## Commands

| User says | Do |
| --- | --- |
| Build phase N with the orchestrator | Build only |
| QA test phase N with the orchestrator | Test only |
| Build and test phase N with the orchestrator | Build then test |
| Build and test next phase with the orchestrator | Infer N from `QA-plan/QA-results/00-index.md` + `project-plan/09-build-order.md` |
| Human test done for phase N | Close `pass_with_risks`; update QA-results + index |

## One phase per run

Read `build-plan/phases/*phase-<N>*` for build. Read `QA-plan/*phase-<N>*` for test. Sequence from `project-plan/09-build-order.md`. Do not advance until phase N is `pass` (or human test complete after `pass_with_risks`).

## FAIL

Append `## Fix round <n>` to the build file. Rebuild and retest until pass or blocked.

## PASS_WITH_RISKS

Create `QA-plan/QA-human-test/phase-N-<slug>.html` using the HTML template in `orchestrator-seed.md`. Tell the user to open it in a browser, complete the checklist, and report back.

## PASS

Write `QA-plan/QA-results/YYYY-MM-DD-phase-N-qa-results.md` and update `QA-plan/QA-results/00-index.md`.

## BLOCKED

Stop; list what the user must provide (missing assets, env, approval).

## Gate decisions

`pass` | `pass_with_risks` | `fail` | `blocked`
