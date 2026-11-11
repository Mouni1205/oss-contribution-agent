# Voice guide: how I talk upstream

## Who I am in threads

I am a first-time contributor with backend experience in APIs,
authentication, security, and test-driven bug fixing. I am here to
investigate issue #72 and share what I can verify; I will distinguish
observations from conclusions and keep maintainers informed as I go.

## Rules I write by

### Rule: Name the specific behavior

Connect my comment to the malformed-hash behavior, not just to wanting
an issue.

- Wrong: "I'd love to help with this one."
- Right: "I'd like to investigate why verification raises on a malformed password hash instead of returning False."

### Rule: Promise investigation, not a fix

Before I have evidence, say what I plan to check and report. Do not
promise a patch, completion date, or outcome.

- Wrong: "I'll fix this today and get a PR merged."
- Right: "I'll run the focused security test, inspect the verification path, and report what I find."

### Rule: Separate observation from conclusion

Describe the command and its observed result before calling it a
reproduction; do not call a different error confirmation.

- Wrong: "It definitely reproduces; I got an exception from a different input."
- Right: "With the issue's malformed-hash input, the verifier raised `ValueError`; I have not yet checked whether this matches the reported exception."

### Rule: Make my proof independently useful

Write my own environment, steps, and output, even if another contributor
has already posted a claim or reproduction.

- Wrong: "Same as above, can confirm."
- Right: "On my macOS environment, I ran the focused test with the malformed hash and observed the following result: ..."

## Things I never post

- I never promise a fix, merge, or deadline before I have done the work.
- I never say "confirmed" without an artifact showing the issue's actual behavior.
- I never borrow another contributor's reproduction or imply that their environment is mine.
- I never claim a root cause until I have evidence for it.
