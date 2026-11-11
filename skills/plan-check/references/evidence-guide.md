# Evidence guide: where evidence lives in a plan package

## Diagnosis and grounding

Where it lives: In an eval package, read the issue context, repro-evidence
block, and the plan's diagnosis and evidence quotes. In live mode, read
the issue description, the contributor's posted repro comment, and the
corresponding diagnosis in `plan.md` and `comment.md`.

Good evidence links the stated cause to an observed behavior from the
reproduction and explains the issue symptom. A plausible cause without
support in the quoted repro is not established.

## Scope

Where it lives: In an eval package, inspect the plan's scope, exclusions,
named files, and approach beside the issue request and diagnosis. In live
mode, inspect those plan statements and compare them with the issue and
repository facts.

Good scope names the behavior being changed and keeps implementation to
the code and tests needed for that cause. It excludes unrelated cleanup
or feature work and does not leave the diagnosed cause unaddressed.

## Executability

Where it lives: In the plan's file list and ordered approach, compared
with repository facts in the eval bundle or the repository's relevant
source and tests in live mode.

Good evidence identifies a valid starting point and concrete actions a
contributor can begin without guessing a material file or step. A vague
intention such as "fix the handler" does not identify an executable
approach.

## Test plan

Where it lives: In the plan's test plan and quoted reproduction evidence.
Compare commands, inputs, and expected results with the trigger and
observed output in the repro block or posted repro comment.

Good evidence exercises the relevant path in the real code and names an
observable result that would fail before the fix and pass after it. A
test that cannot reach the trigger or has no expected result cannot
establish the fix.

## Honesty

Where it lives: In the plan's risks, unknowns, assumptions, and
deviations. Read these alongside the diagnosis and test plan to identify
unresolved dependencies or claims not established by the evidence.

Good evidence labels material uncertainty and avoids presenting an
assumption as a fact. If implementation deviated, a useful note names
the change and its reason; the absence of deviations needs no invented
issue.

## Comms

Where it lives: In the candidate plan comment compared with issue-thread
highlights and the repo-facts block. In live mode, read the thread and
the repository's contribution, issue-template, and AI-use rules when
present.

Good communication gives this contributor's own evidence-based
diagnosis, bounded change, and test plan. It responds to relevant
maintainer direction and meets stated repository requirements; do not
invent requirements when the repo facts are silent.

