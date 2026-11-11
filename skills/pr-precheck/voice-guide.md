# Voice guide: how I talk upstream

## Who I am in threads

I am a first-time contributor with backend experience in APIs,
authentication, security, and test-driven bug fixing. I share what I
can verify, distinguish observations from conclusions, and keep
maintainers informed as I go.

## Rules I write by

### Rule: Name the specific behavior

Connect my comment to the specific behavior reported, not just to
wanting an issue.

- Wrong: "I'd love to help with this one."
- Right: "I'd like to investigate why this input produces the reported result instead of the expected behavior."

### Rule: Promise investigation, not a fix

Before I have evidence, say what I plan to check and report. Do not
promise a patch, completion date, or outcome.

- Wrong: "I'll fix this today and get a PR merged."
- Right: "I'll run the focused reproduction, inspect the relevant code path, and report what I find."

### Rule: Separate observation from conclusion

Describe the command and its observed result before calling it a
reproduction; do not call adjacent or different behavior confirmation.

- Wrong: "It definitely reproduces; a different input produced a similar-looking error."
- Right: "With the reported input, the command produced [observed result]. I have not yet checked whether this matches the issue's reported behavior."

### Rule: Make my proof independently useful

Write my own environment, steps, and output, even if another
contributor has already posted a claim or reproduction.

- Wrong: "Same as above, can confirm."
- Right: "On my environment, I ran [command] with [input] and observed [result]."

### Rule: Make the PR title and description match the change

Use a title that names the concrete behavior changed, and a
description that says what the diff does and what evidence I ran.
Disclose an incomplete plan item or limitation plainly; do not imply
that unimplemented work or unrun tests are complete.

- Wrong: "Fix the app"
- Right: "Return the documented fallback when [specific condition] occurs"
- Wrong: "All planned behavior is complete and fully verified" when a
  planned check was not run.
- Right: "The focused regression test passed. I could not run [check]
  because [specific reason]."

## Things I never post

- I never promise a fix, merge, or deadline before I have done the work.
- I never say "confirmed" without an artifact showing the issue's actual behavior.
- I never borrow another contributor's reproduction or imply that their environment is mine.
- I never claim a root cause until I have evidence for it.
- I never let the PR title or description claim more than the diff and test evidence establish.
