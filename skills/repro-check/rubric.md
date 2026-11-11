# Rubric: is this reproduction package ready to post?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Claim is specific and honest | The candidate claim comment compared with the issue title/body and thread highlights; compare any claim that reproduction is complete with the report's evidence. | Pass when the comment identifies the issue symptom or a relevant technical target. Pass when it names a bounded next step or reports work already done. Pass when any reproduction or diagnosis claim is supported by the report. Fail generic assign-me language, unsupported certainty, or guarantees about fixes, timing, or outcomes. | required |
| Environment is interpretable | The repro report's environment record compared with the issue's target version, platform, configuration, and relevant repo facts. | Pass when the report names environment details material to the trigger. Pass when relevant conditions match, or differences are explicitly named and accounted for. Fail when missing context prevents interpretation or a material mismatch is silent. A direct artifact showing the issue behavior in the stated environment remains evidence even if the thread suggests a fix shipped. | required |
| A stranger can rerun the attempt | The repro report's commands, inputs, configuration, setup references, and artifact locations; check whether any required private files or inaccessible services are supplied or described. | Pass when a stranger with the stated environment and access to the named public project can reconstruct the trigger. Pass when they can run it without guessing a material input or relying on unavailable private state. Do not require a fixed number of steps or a particular format. | required |
| Artifact shows the attempted behavior | The report's output, logs, screenshots, measurements, or other artifacts compared with the issue's trigger and scenario. | For a claimed reproduction, pass when an artifact shows the issue's symptom under the relevant trigger. For a cannot-reproduce report, pass when an artifact records an attempt to exercise the issue's scenario and its observable result. Fail when the artifact shows only adjacent behavior or no observable result. Do not judge whether the author's conclusion is justified here. | required |
| Outcome is evidence-calibrated | The report's stated expected and actual behavior and conclusion compared with its artifacts and the issue's description. | Pass when the conclusion stays within what the artifact shows. A cannot-reproduce result may pass without demonstrating the bug. Fail when a different result or missing evidence is described as confirming the issue. | required |
| Communication follows repo policy | The repo-facts block's bug-report and contribution-policy requirements compared with the claim and repro comments, including any AI-use disclosure requirement. | Pass when the comments meet each explicit repository requirement that applies to issue reports or AI disclosure. If policy requires naming AI tools and the extent of assistance, include both. Do not infer a disclosure requirement from silence. | required |

## Verdict rule

Accept only when every required check passes. A fail or unclear on any
required check means reject. Preferred checks, if added later, never
change the verdict.
