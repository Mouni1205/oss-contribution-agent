---
name: pr-precheck
description: Grade a PR package (a candidate pull request read against the plan it claims to implement and the issue that plan belongs to) and decide whether it is ready to submit. Use when checking your own branch, draft PR title, and description before opening the pull request, or when grading an eval package bundle.
---

# pr-precheck: rubric-driven PR grading

## The question

Answer exactly one question about exactly one PR package: is this
ready to submit? A PR package is a candidate pull request—its plan,
branch diff, draft title and description, and test evidence—read
against the plan it claims to implement and the issue that plan
belongs to. Do not grade multiple PRs, answer a different question,
or decide from gut feel; follow the components in this directory.

## Inputs and modes

Run in exactly one of these modes:

- **Live mode:** Grade the contributor's own PR. Read the package files,
  including the contributor's plan and any deviation
  notes, draft PR title and description, and test evidence. Read the
  branch diff from the working copy using `git diff main...HEAD` and
  compare it with the plan. Read the issue's thread, the repository's
  PR template, and `docs/CONTRIBUTING.md` for issue-side evidence and
  repo requirements. Do not treat unlisted working-copy files as package
  evidence.
- **Eval mode:** Grade one frozen PR package (a markdown bundle from the eval set).
  Use only the package bundle text for evidence. Do not fetch anything
  or read any other repository files. Grade a complete package by
  running every check and applying the full verdict rule.

## The scope seam (live mode only)

In live mode, read `scope.md` before anything else. Use its `Repo:`
line to determine whether the PR's target repository is in scope, and
apply its house rules when reading the package. Refuse to grade a PR
outside that repository. If the `Repo:` line is still an unfilled
placeholder, stop without grading and tell the contributor to fill it
with the target repository; never guess the repo.
Ignore `scope.md` entirely in eval mode.

## The voice seam (live mode only)

In live mode, also read `voice-guide.md`. Check the outgoing PR title
and description against its rules, and report any broken rule in the
readable summary, quoting or identifying the rule. The voice guide
does not change the verdict by itself; it affects the verdict only if
the rubric defines a check that uses it. Ignore `voice-guide.md`
entirely in eval mode.

## Component reads

Read `rubric.md` for the checks and verdict rule,
`references/evidence-guide.md` for where each evidence family lives,
and `procedure.md` for the operating steps. Execute the procedure as
written; if it is silent on a step, report the gap rather than
inventing a step. If the rubric has no authored check content or the
procedure has no authored step content, refuse to grade and explain
that the required component is empty. Do not invent checks or
procedure steps at runtime.

## Verdict and output

Return only one of the binary verdicts: `accept` means ready to submit;
`reject` means hold. You may provide a readable per-check summary
first. End the reply with the fenced JSON block below, valid and
exactly as specified, with nothing after it. Include one check entry
per rubric check and a one-line evidence fact or quote for each.

```json
{
  "item": "<PR URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear",
     "evidence": "<one line: the fact or quote that decided it>"}
  ],
  "verdict": "accept|reject"
}
```

## Grading discipline

Grade with evidence: name the fact or quote that decided every check;
“looks fine” is not evidence. Grade the PR artifacts against the plan,
issue, and stated standards, not their polish or formatting. Apply the
rubric's stated conditions even if a result feels wrong; the rubric,
not the individual run, determines what passes. Follow the procedure
for how to gather and apply evidence, and report its gaps rather than
improvising. Treat `unclear` as the rubric's verdict rule directs; if
that rule is silent, treat `unclear` as a failure because an
unverifiable claim does not establish readiness.
