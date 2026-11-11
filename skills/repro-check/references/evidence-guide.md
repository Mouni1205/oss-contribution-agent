# Evidence guide: where proof lives in a reproduction package

## Environment

Where it lives: In eval mode, inspect the repro report's environment
record and compare it with the issue context and repo-facts block. In
live mode, inspect the draft report and the issue body for version,
platform, configuration, or dependency constraints; use the project's
documented setup only to interpret what the report says, not to fill in
facts the author omitted.

Good evidence names the versions and platform that matter to the trigger
and makes any relevant difference from the issue's target explicit. Do
not demand details unrelated to the reported behavior, but do not treat
an unmentioned version or platform mismatch as a match. A thread's
speculation or note that a fix shipped does not negate an artifact that
directly shows the symptom on the report's stated environment; compare
the observed behavior and versions rather than assuming the thread is
conclusive.

## Steps

Where it lives: In eval mode, read the repro report's commands, input,
configuration, setup notes, and references alongside the issue's own
steps. In live mode, inspect the candidate repro draft and any linked
public artifacts or setup documentation it relies on.

Good evidence lets a reader with the stated environment and access to
the public project recreate the relevant starting state and trigger
without guessing a material command, input, or configuration. A private
monorepo, unshared config, or missing prerequisite that controls the
result makes the attempt non-rerunnable. Judge the information, not the
numbered-list shape or report length.

## Behavior shown

Where it lives: In the repro report's quoted output, logs, screenshots,
measurements, or other artifacts. Compare the exact trigger and
observable result with the issue's description and any maintainer
clarification in the thread.

For a claimed reproduction, good evidence exhibits the issue's
distinctive symptom under the relevant trigger. A startup banner,
unrelated error, graceful argument-validation failure, or output from a
modified trigger does not establish the reported behavior. For an
explicit cannot-reproduce report, good evidence records an attempt to
exercise the scenario and its observable result; the bug need not
appear. Whether the stated conclusion is justified belongs to the
Honesty check. A control run can isolate the trigger; where the artifact
itself is already diagnostic, its absence is not a defect.

## Honesty

Where it lives: Compare the report's expected/actual statements and
conclusion with its artifacts, issue target, and environment record.
Also compare claim-comment assertions such as "reproduced" or a stated
root cause with the report that is supplied alongside it.

Good evidence supports the conclusion at the level stated. A genuine
cannot-reproduce report can pass without demonstrating the bug when it
states what was tried, what happened, and which material condition
differed. It must not present a different result or missing evidence as
confirmation of the issue. Repeated certainty does not strengthen an
artifact that shows the wrong behavior.

## Comms

Where it lives: Read the candidate claim and repro comments, then check
the eval bundle's repo-facts block for issue-template asks and
contribution or AI-use policy. In live mode, read the corresponding
repository contribution guide, issue template, and AI policy when
present; do not infer a rule from silence.

Good communication ties the claim to this issue and names a plausible
next action or completed evidence without generic self-assignment,
unsupported diagnosis, or guarantees about fixes and timing. Satisfy
explicit repo requirements. When policy requires disclosure, the
comment must identify the AI tool and extent of assistance; when no
such requirement is stated, do not fail the package for omitting it.
