# Evidence guide: where evidence lives in a PR package

## Plan fidelity (eval category: silent-drift)

**Where it lives:** In an eval package, read the plan-context block's
scope, named files, intended behavior, and any deviation notes beside
the candidate PR's diff; read the title and description beside that
diff as well. In live mode, use `plan.md` and its deviation notes,
`git diff main...HEAD`, and `pr_draft.md`.

**What good looks like:** Each material change is inside the planned
boundary or tied to a clear, honest deviation, and the diff delivers
the behavior the plan claims. The title and description accurately
describe the diff; unrecorded additions, omissions, and overclaims are
silent drift.

## Test evidence (eval category: not-tested)

**Where it lives:** In an eval package, compare the plan-context
test plan and repro evidence with the candidate PR's test-evidence
section, including commands, inputs, and outputs. Use repo facts for
named required checks. In live mode, compare `test_evidence.md` with
the test plan and repro in `plan.md`, and
check the applicable requests in the repository's PR template and
`docs/CONTRIBUTING.md`.

**What good looks like:** Evidence shows a relevant command or test
ran against the branch, exercised the planned behavior, and produced
an observable result that can be compared with an expected result.
Record applicable repository-required check outcomes. A bare “tests
pass” or unsupported claim does not prove behavior; a disclosed,
justified limitation is distinct from silently untested work.

## Diff quality (eval category: unreviewable)

**Where it lives:** In an eval package, inspect the candidate PR's
unified diff and changed-file paths, with commits as context. In live
mode, inspect the changed-file list and hunks from `git diff
main...HEAD`; use the plan to identify the intended fix and related
tests.

**What good looks like:** A reviewer can find the planned fix and
relevant tests without unrelated changes obscuring them. Unrelated
drive-by edits, debug leftovers, dead or commented-out code, and
formatting churn matter when they materially bury the change; size or
commit count alone is not evidence of poor reviewability.

## Standards and comms (eval category: standards-wall)

**Where it lives:** In an eval package, read repo facts for PR-template
asks, contributing instructions, disclosure policy, and thread
highlights; compare them with the candidate title and description. In
live mode, read the repository's PR template, `docs/CONTRIBUTING.md`,
applicable issue-thread requests, and `pr_draft.md`. Compare explicit
AI-use disclosure requirements with the draft where applicable.

**What good looks like:** Every applicable request has substantive
content or a direct, candid response, including required disclosure
and relevant maintainer direction. Empty boilerplate or an ignored
stated requirement fails; do not infer requirements when the available
policy, template, and thread are silent. Whether claims match the diff
is judged under plan fidelity, not here.
