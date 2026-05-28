# Release decision model

## Gate decisions

| Decision | Meaning | Next step |
| --- | --- | --- |
| **pass** | All QA outcomes met with evidence | Update index; phase closed |
| **pass_with_risks** | Automated checks OK; subjective UX/voice needs human eyes | HTML checklist in `QA-human-test/`; phase open until human test done |
| **fail** | Objective gap vs build/QA spec | Fix round in build file → rebuild → retest |
| **blocked** | Cannot test (missing files, env, approval) | Stop; user unblocks |

## Phase completion

A phase is **done** when index status is `pass`, or `pass_with_risks` → human HTML complete → recorded as `pass`.

## Release readiness

All five phases `pass` in `00-index.md` and `demo-1B/prototype.html` passes Phase 5 QA (responsive, a11y, single-file, no lorem, simulated form disclaimer).
