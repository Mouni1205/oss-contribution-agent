# Rubric: is this pull request ready to submit?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Plan fidelity (silent drift) | The plan's stated scope, file boundary, intended behavior, and deviation notes compared with the branch diff's changed files and hunks; the PR title and description compared with what the diff actually delivers. | Pass when every material diff change is inside the plan's boundary or explained by an honest, specific deviation recorded in the plan, and the PR text describes the delivered behavior and any shortfall accurately. Fail when the diff silently adds or omits planned behavior, exceeds the boundary without a recorded reason, or the PR text claims behavior the diff does not implement. | required |
| Test evidence (not tested) | The plan's test plan and reproduction trigger compared with `test_evidence.md`'s commands, inputs, and observed results; repository-required checks found in the PR template or `docs/CONTRIBUTING.md` compared with their recorded outcomes. | Pass when evidence from the branch exercises the planned behavior and relevant regression behavior, gives observable expected and actual results, and records the outcome of applicable repository-required checks. A disclosed limitation or unrelated check failure does not fail by itself when the relevant behavior is demonstrably tested and the limitation is accurately explained. Fail when relevant behavior has no observable verification, a claimed result cannot be supported, or an applicable required check was not run and no justified limitation is disclosed. | required |
| Diff quality (unreviewable) | The branch diff's changed-file list and hunks, read against the planned fix and related test changes; inspect commits only to locate and understand changes, not as a proxy for diff contents. | Pass when a reviewer can identify the planned fix and its relevant tests without unrelated edits or debris obscuring them. Fail when unrelated changes, debug leftovers, dead or commented-out code, or avoidable churn materially bury or obscure the fix. Do not fail solely for a particular diff size or commit count. | required |
| Standards and communication (standards wall) | The repo's PR template, `docs/CONTRIBUTING.md`, and explicit maintainer requests in the issue thread compared with `pr_draft.md`'s title and description and the submission's required disclosures. | Pass when every applicable template request has substantive content, explicit repository and maintainer requirements are met or candidly addressed, and any required AI-use disclosure is present. Do not invent requirements when the template, policy, or thread is silent. Fail when an applicable ask is omitted, answered with empty boilerplate, or ignored. | required |

## Verdict rule

Accept only when every required check passes. Reject when any required
check fails or is unclear; `unclear` counts as fail because readiness
must be verifiable from the package. Preferred checks, if added, never
change the verdict. A shortfall does not automatically require
rejection when the plan records the deviation, the PR text discloses
what was and was not delivered, and the remaining required checks pass.
