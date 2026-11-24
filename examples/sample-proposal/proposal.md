# Proposal: US standard deduction, single filer, tax year 2025 (SAMPLE for feasibility test)

This is a hand-written sample used to test the reviewer. It is not a product of the Changeling Kit workflow.

## Change
Add rule version `standardDeduction.single@2025-revised`.

- Value: 1575000 (US cents, i.e. $15,750)
- appliesFrom: 2025-01-01
- appliesTo: 2025-12-31
- knownFrom: 2025-07-04
- Supersedes: `standardDeduction.single@2025-original` (value 1500000, knownFrom 2024-11-04, the IRB issue date) for knowledge dates on or after 2025-07-04.

## Citation
- sourceId: us-irb-2025-45
- snapshotSha256: 990554f1113fcf41f9be878868cd8e9c2b9f14ae9c75e721c055568a9c703517
- quote: "the basic standard deduction amounts provided in § 63(c)(2) are increased to $15,750 for single individuals and married individuals filing separate returns"

## Notes from the drafter
- The same section also raises head of household to $23,625 and married filing jointly to $31,500. Those are out of scope for this proposal.
