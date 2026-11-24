# Changeling Crew

A Kiro Crew app that reviews rule-change proposals produced by [Changeling Kit](https://github.com/koheismh/kiroween-2026). It writes a review note and never approves anything.

Status: feasibility spike (S4). Not published to the Crew App Store.

## What it contributes
- Agent `rule-change-reviewer`
- Skill `rule-change-review`, which defines the fixed review note format

## Contract with Changeling Kit
- Input: a proposal directory with `proposal.md` and `gate-report.json`.
- Output: one file, `review.md`, in the same directory.
- The app is not a runtime dependency of any Changeling Kit application. Approval is a separate human action and does not involve this app.

## Install (local, for development)
```
kirocrew app install <path-to-this-repo>
```
Crew refuses to enable a third-party app until you trust it: Settings, Security, Third-party apps, then trust `changeling-crew`. After that:
```
kirocrew app enable changeling-crew
```

## Try it
Point the reviewer at `examples/sample-proposal/`. The sample gate report has a missing required gate, so the expected recommendation is `DO NOT APPROVE`.

## Limits
- The agent uses the `@kirocrew-core` tool set. "Write only `review.md`" is enforced by the prompt, not by a sandbox.
- A reviewer comment is advice. It is not a gate.
