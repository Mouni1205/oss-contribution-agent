# Procedure: how this skill grades a plan package

## Read order

1. In live mode, read `scope.md` first and confirm the issue belongs to
   the repository configured on its `Repo:` line. Stop if it is outside scope or
   the repo line is still a placeholder. In eval mode, do not consult
   scope or outside sources.
2. Read `rubric.md`, `references/evidence-guide.md`, and this procedure;
   list each check and its evidence sources before grading.
3. Read the whole package in this order: issue context and thread
   highlights, repo facts, reproduction evidence, candidate plan, then
   candidate plan comment. Record the issue symptom, what the repro
   actually showed, relevant maintainer direction, and stated repo
   requirements.
4. In live mode, read the contributor's posted reproduction comment and
   relevant issue thread; use repository docs only for stated repo
   facts. If no contributor reproduction comment is available, use only
   reproduction evidence quoted in the candidate drafts and record that
   limitation. Do not fail a check solely because the posted repro
   comment is absent when the drafts contain concrete repro evidence.
   In eval mode, treat the bundle as the complete evidence.

## Evidence gathering

1. For diagnosis, extract the plan's causal claim and the quoted repro
   observation that supports it; compare both with the issue symptom.
2. For scope, list the planned change, exclusions, and named files or
   areas. Compare the list with the stated cause and requested behavior.
3. For executability, record the plan's target files and implementation
   actions in their proposed order, then check those targets against
   available repository facts.
4. For testing, record the command, input, code path, expected result,
   and any regression case. Compare them with the reproduction trigger
   and observed failure.
5. For uncertainty, note explicit assumptions, risks, unknowns, and
   deviations. For communication, compare the candidate comment with
   thread direction and explicit repo-facts requirements.
6. In eval mode, quote or identify only facts in the bundle. In live
   mode, identify the issue or repository location for each external
   fact; never fill gaps with assumptions.

## Check execution

1. Grade each rubric row using only its named evidence, in table order.
   Use the evidence guide to locate the plan section or source.
2. Mark `pass` only when every condition in that row's pass condition is
   supported. Mark `fail` when evidence contradicts a condition. Mark
   `unclear` only when the package genuinely lacks evidence needed for
   that decision; do not use it to avoid checking an available source.
3. For each grade, keep one concise quote or concrete fact that explains
   the decision. Do not let a polished comment compensate for a weak
   diagnosis, scope, approach, or test.

## Verdict assembly

1. Apply the verdict rule in `rubric.md`: accept only if every required
   check passes; any required fail or unclear means reject. Preferred
   checks do not affect the verdict.
2. Report every check with its name, grade, and deciding quote or fact.
   State the binary verdict and use the required fenced JSON output
   format from `SKILL.md`, with no text after the JSON block.

