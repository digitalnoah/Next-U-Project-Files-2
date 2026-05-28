# Agent workflow — Vibe Code Academy orchestrator

## Loop (one phase at a time)

```text
Pick phase N → BUILD (build-plan) → TEST (QA-plan) → gate → next phase only if pass
```

**Gate:** `pass` | `pass_with_risks` | `fail` | `blocked`

## Orchestrator commands

| Command | Action |
| --- | --- |
| `Build phase N with the orchestrator` | Implement build file only; run validations in that file |
| `QA test phase N with the orchestrator` | Run QA outcomes; gate decision; no build unless FAIL fix round |
| `Build and test phase N with the orchestrator` | Full loop including fix rounds on fail |
| `Build and test next phase with the orchestrator` | Next incomplete phase per `QA-plan/QA-results/00-index.md` |
| `Human test done for phase N` | Close `pass_with_risks` after HTML checklist |

## Folders

```text
build-plan/phases/NN-phase-NN-<slug>.md
QA-plan/NN-phase-NN-<slug>.md
QA-plan/QA-results/
QA-plan/QA-human-test/     # HTML checklists (pass_with_risks only)
project-plan/09-build-order.md
demo-1B/prototype.html     # deliverable
```

## Human QA

On **pass_with_risks**, open `QA-plan/QA-human-test/phase-N-*.html` in a browser, complete every item, then reply: `Human test done for phase N` with evidence.

Seed and templates: `orchestrator-seed.md`
