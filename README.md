# Changeling Crew

A Kiro Crew app that reviews rule-change proposals produced by [Changeling Kit](https://github.com/koheismh/kiroween-2026). It writes a review note and never approves anything.

Status: feasibility spike (S4), verified on 2026-11-24 with Kiro Crew on Windows. Not published to the Crew App Store.

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

Do not uninstall and reinstall to pick up changes: uninstalling revokes the trust grant. Use the dashboard's Update action instead.

## Try it
Point the reviewer at `examples/sample-proposal/`. The sample gate report has a missing required gate, so the expected recommendation is `DO NOT APPROVE`. `examples/sample-proposal/review.md` is the output of a real Crew run.

## Limits
- Tools: `fs_read` and `fs_write` only. Crew's governance empties `allowedTools`, so reads are not auto-approved. Writes to `**/review.md` are auto-approved through `toolsSettings`. Other writes need approval. This is an approval guard, not a hard deny.
- The reviewer can only check a quote if the proposal points to a snapshot file it can read.
- A reviewer comment is advice. It is not a gate.
