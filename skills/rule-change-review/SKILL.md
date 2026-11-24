---
name: rule-change-review
description: Review a Changeling Kit rule-change proposal and its gate report, then write a fixed-format review.md. Use when asked to review a proposal directory.
triggers: [review, proposal, gate report, rule change]
always: false
---

# Rule Change Review

## Inputs
A proposal directory containing:
- `proposal.md`: the drafted change (what changes, effective dates, citations as verbatim quotes).
- `gate-report.json`: results of deterministic gates, produced by the skeleton. Each gate has `name`, `required`, and `status` (`pass`, `fail`, or `missing`).

## Rules
- Read only the files in the proposal directory and any source snapshot files it names.
- Write exactly one file: `review.md` in the proposal directory. Do not edit anything else.
- You never approve. Approval is a human action outside this app.
- If any required gate is `fail` or `missing`, the recommendation is `DO NOT APPROVE`. State which gate.
- A matching quote proves the quote exists in the snapshot. It does not prove the proposal interprets it correctly. Check interpretation yourself and say what you checked.
- Do not claim something is verified unless you opened the file and compared it.

## Output format (fixed headings, in this order)
```
# Review: <proposal title>

## Recommendation
APPROVE-ELIGIBLE | DO NOT APPROVE

## Gate summary
<one line per gate: name, required, status>

## Interpretation check
<for each changed rule: the quote, your reading, agree or disagree, reason>

## Effective dates
<appliesFrom, appliesTo, knownFrom: do they match the source?>

## Unsupported or out-of-scope risks
<situations the change might mishandle>

## Open questions for the human
<bulleted list, may be empty>
```
`APPROVE-ELIGIBLE` means only that no blocking problem was found. It is not an approval.
