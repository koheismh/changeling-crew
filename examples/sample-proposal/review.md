# Review: US standard deduction, single filer, tax year 2025 (SAMPLE for feasibility test)

## Recommendation
DO NOT APPROVE

Blocking: required gate `ground-truth` has status `missing`.

## Gate summary
- schema: required=true, status=pass
- citation-quote: required=true, status=pass
- no-change-before-effective-date: required=true, status=pass
- ground-truth: required=true, status=missing

## Interpretation check
I opened `proposal.md` and `gate-report.json`. I did not open a source snapshot. The proposal gives a sourceId (`us-irb-2025-45`) and a SHA-256 but names no snapshot file, so I could not compare the quote against the source myself. The `citation-quote` pass is the gate's result, not something I verified.

Changed rule: `standardDeduction.single@2025-revised`, value 1575000 cents.
- Quote: "the basic standard deduction amounts provided in § 63(c)(2) are increased to $15,750 for single individuals and married individuals filing separate returns"
- My reading: the basic standard deduction becomes $15,750 for single filers (and for married filing separately).
- Agree or disagree: agree on the value. $15,750 equals 1575000 cents, and the quote covers single filers. Restricting this proposal to single is consistent with the quote. It also covers married filing separately, which this proposal does not change (see risks).
- Caveat: the quote as written does not say which tax year it applies to. I could not check that against the snapshot.

## Effective dates
- appliesFrom 2025-01-01 and appliesTo 2025-12-31: consistent with a tax-year-2025 amount. The quote does not state the year, so I could not confirm them against the source text.
- knownFrom 2025-07-04: not verified. The proposal describes the superseded rule's knownFrom (2024-11-04) as "the IRB issue date". The cited sourceId is `us-irb-2025-45`, and by that naming the issue would fall in late 2025, not 2025-07-04. Either knownFrom comes from a different event (for example enactment of a law) than the cited source, or the sourceId is wrong. The proposal does not say which.
- Supersession: the original (1500000, knownFrom 2024-11-04) is superseded for knowledge dates on or after 2025-07-04. That is internally consistent, but it depends on the knownFrom question above.

## Unsupported or out-of-scope risks
- Married filing separately is raised to $15,750 by the same quote. If the pack has a separate rule for that status, it will be stale after this change.
- Head of household ($23,625) and married filing jointly ($31,500) are explicitly out of scope per the drafter. Those statuses stay at the old values until a separate proposal.
- Additional standard deduction for age 65+ or blind, and any dependent-filer limit, are not addressed.
- Knowledge dates between 2025-07-04 and the real publication date of the cited source would use a value the cited source did not yet publish, if knownFrom is wrong.
- The proposal is labelled a hand-written sample, not a product of the Changeling Kit workflow. Its provenance is unverified.

## Open questions for the human
- Why is the `ground-truth` gate missing, and can it be run before any decision?
- Which snapshot file corresponds to `us-irb-2025-45`, and does it contain the quote and a date that supports knownFrom 2025-07-04?
- Is knownFrom meant to be the legal enactment date or the publication date of the cited source?
- Should a companion proposal cover married filing separately, head of household and married filing jointly?
