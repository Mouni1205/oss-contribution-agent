# Procedure: how this tool grades a PR package

## Read order

1. In live mode, read `scope.md` first. Confirm the PR targets the
   repository on its `Repo:` line and apply its house rules. Stop
   without grading if the target is outside scope or the repo line is
   still an unfilled placeholder. In eval mode, ignore `scope.md` and
   do not fetch or read anything outside the selected package bundle.
2. Read `rubric.md`, `references/evidence-guide.md`, and this
   procedure. If the rubric has no authored checks or the procedure
   has no authored steps, refuse to grade and explain what is empty.
   List the checks in rubric order before gathering their evidence.
3. In live mode, read the contributor's package files: the
   contributor's `plan.md` including deviation notes, `test_evidence.md`,
   and `pr_draft.md`. Read
   the working-copy diff from the repo using `git diff main...HEAD`.
   Then read the issue's thread, the repository's PR template, and
   `docs/CONTRIBUTING.md`. Record the issue's requested behavior,
   plan boundary and test expectations, actual changes, PR claims,
   applicable repo asks, and relevant maintainer direction.
4. In eval mode, read the one selected frozen package completely.
   Record the package id and source, then locate the repo facts, issue
   and thread highlights, plan context (including scope, deviation
   notes, and test plan), candidate title and description, commits,
   diff, and test evidence. Treat the bundle as the whole world.
5. Read the plan before interpreting the diff so the intended change
   is known; read the diff before judging description claims so those
   claims are checked against the actual change. Do not start grading
   until all available evidence sources for the four rubric checks
   have been inventoried.

## Evidence gathering

1. For plan fidelity, extract the plan's intended behavior, named
   files, in-scope and out-of-scope boundary, and each deviation note.
   Compare them with every changed file and material diff hunk. Make a
   short list of implemented, missing, extra, and explicitly revised
   items. Compare each material claim in the PR title and description
   with the diff; record any overclaim or disclosed limitation.
2. For test evidence, extract the plan's test command, trigger/input,
   expected result, and regression expectations. Compare each with
   the commands, branch/context, and observed output in
   `test_evidence.md` or the package's test-evidence section. Check
   whether the tests exercise the same behavior and whether results
   are observable. Identify repository-required checks in the
   template and contribution docs or repo-facts block; record their
   outcome or the specific disclosed reason they could not be run.
3. For diff quality, inspect the changed-file list and hunks, noting
   which changes implement the plan and its tests. Identify unrelated
   edits, debug leftovers, dead or commented-out code, and churn only
   when they materially obscure review of the fix. Do not infer
   quality from the number of commits or lines changed.
4. For standards and communication, list each applicable PR-template
   request, stated contribution/disclosure requirement, and relevant
   maintainer request. Match each with substantive content in the
   draft or a direct response in the thread. Mark a requirement
   absent from the sources as not applicable; do not invent one.
5. In eval mode, cite only facts contained in the package. In live
   mode, cite the named local file, diff, or repository/issue source
   for each deciding fact. Use the evidence guide to locate sources;
   do not fill missing facts with assumptions.

## Check execution

1. Execute the rubric checks in table order, using only the evidence
   named for each check. Use the comparisons already gathered; reopen
   a source only to verify a specific fact.
2. Mark `pass` only when the full pass condition is supported. Mark
   `fail` when available evidence contradicts the condition. Mark
   `unclear` only when a necessary fact is genuinely absent or cannot
   be verified; an unsupported claim is not proof.
3. For a disclosed deviation, check that the plan records what
   changed and why, the diff matches that recorded scope, the PR text
   accurately describes the delivered result, and test evidence
   supports the behavior claimed. Do not reject solely because the
   delivered scope differs from the original plan when those
   conditions hold.
4. For every grade, preserve one concise, specific fact or quotation
   that decided the result. Report all checks; do not let a strong
   result on one check compensate for a different check's failure.

## Verdict assembly

1. Apply `rubric.md`'s verdict rule exactly: accept only if every
   required check passes; a required fail or unclear means reject;
   preferred checks never change the verdict.
2. In the readable summary, report every check's name, grade, and
   deciding evidence. If the verdict is reject, identify the first
   failing or unclear required check in rubric order as the decisive
   check, and quote or state its evidence. If the verdict is accept,
   state that all required checks passed.
3. End the reply with the valid fenced JSON block required by
   `SKILL.md`, containing one entry per rubric check, the same
   evidence and grades, and the binary verdict. Put nothing after the
   JSON block.
