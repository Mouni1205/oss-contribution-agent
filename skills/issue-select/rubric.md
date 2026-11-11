# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Maintainer alive | The last 5 default-branch commits under Repo facts, the maintainer first-response sample under Repo facts, and maintainer comments in the issue's Comments section | Pass if either the last 5 default-branch commits include human maintainer activity within 365 days before the bundle capture date, or an Owner, Member, or Collaborator replies in the first-response sample or this issue thread. Bot-only activity and older history alone do not count as current maintainer life | required |
| Repo in use | The `archived` flag, `latest release`, `last push to any branch`, and adoption counts under Repo facts, using the Family 2 signals in `references/evidence-guide.md` | Pass if the repository is not archived and the evidence shows current use through a release, a moving branch, or meaningful adoption such as stars or a `Used by` count. An archived repository fails regardless of other signals | required |
| Scope fits a newcomer | The issue body and Comments section, using the Family 3 guidance in `references/evidence-guide.md` | Pass if the issue asks for one bounded contribution and gives a concrete specification through reproduction steps, expected behavior, acceptance criteria, a named documentation home, or a maintainer diagnosis. A concrete issue filed by an Owner, Member, or Collaborator can pass even when the body is brief. Related file or documentation updates can be one contribution, and a detailed technical checklist, diagnostic environment dump, or several implementation suggestions for one reported symptom is evidence of scope rather than evidence of excess scope. Do not require a maintainer to have confirmed a contributor-authored issue or to have commented on a clear issue. Fail explicit umbrella or tracking issues, pure usage questions, unresolved design debates, unresolved product decisions or required assets, years of unresolved discussion, multiple abandoned attempts showing the real difficulty, issues with no actionable specification, or work explicitly involving broad core-internal changes. A short issue, missing reproduction steps, or a good-first-issue label is not automatically a failure | required |
| Unclaimed | The issue's `assignees` and `linked PRs` under Repo facts, plus claim comments and PR mentions in the Comments section | Pass if there is no assignee, no open linked or mentioned pull request, and no current contributor claim or implementation comment. A closed unmerged pull request or an old abandoned claim is not an active claim | required |
| Contribution policy permits the work | The repository's contribution policy and any AI policy files, templates, or linked contributor documents under Repo facts | Pass if the policy is silent or permits AI-assisted contributions under stated conditions. Fail only when the policy explicitly bans AI-generated code or documentation; disclosure, review, testing, and understanding requirements are conditions to follow, not bans | required |

## Verdict rule

Accept only if all five required checks pass. Reject if any required check
fails. Treat `unclear` as fail for a required check because a newcomer
should not take an issue whose suitability cannot be verified.
