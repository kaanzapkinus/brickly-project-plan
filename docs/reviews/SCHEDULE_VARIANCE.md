# Schedule Variance Analysis

> Phase 4 (Monitoring & Control) deliverable. Closes issue [#49](https://github.com/kaanzapkinus/brickly-project-plan/issues/49). Compiled at project close, 2026-05-18.

## Milestone-level variance

| Milestone | Planned close | Actual close | Variance (days) | Status |
|---|---|---|---|---|
| Phase 1 — Initiation | 2026-05-05 | 2026-05-05 | 0 | ✅ On time |
| Phase 2 — Planning | 2026-05-08 | 2026-05-08 | 0 | ✅ On time |
| Phase 3 — Execution | 2026-05-15 | Out-of-scope (plan-only deliverable) | — | N/A — scope change at mid-project review (#48) |
| Phase 4 — Monitoring & Control | 2026-05-18 | 2026-05-18 | 0 | ✅ On time |
| Phase 5 — Closure | 2026-05-18 | 2026-05-18 | 0 | ✅ On time |

**Total schedule variance across closed phases:** 0 days. KPI K3 target (≤ 1 day variance per milestone) **met**.

## Issue-level granularity

| Day | Planned issue closures | Actual closures | Slip? |
|---|---|---|---|
| Day 1 (2026-05-05) | #1, #2, #3, #4, #5, #6 | #1, #6 closed by 22:00; #2-#5 closed Day 2 morning | Minor — same day boundary |
| Day 2 (2026-05-06) | #7, #8, #9, #10, #11 (plus carryover) | All planning Day-2 issues closed by 18:00; #2-#5 carryover from Day 1 also closed | None |
| Day 3 (2026-05-07) | #12, #13, #14, #15, #16 | All closed by 17:00 | None |
| Day 4 (2026-05-08) | #17, #18, #19, #20, #21 | All closed by 18:00; #17 (hi-fi mockups) needed evening session | None |
| Day 5 (2026-05-11) | Phase 3 issues #22-26 start | Scope change pending — issues remain `Todo` | Pre-decision |
| Day 6 (2026-05-12) | Phase 3 continues | `Todo` | Pre-decision |
| Day 7 (2026-05-13) | #48 mid-project review | #48 closed 18:30 — formal scope-change decision (plan-only) | None |
| Day 8 (2026-05-14) | (Original: execution) | #50 closed (CI workflow stub + CONTRIBUTING) | Re-scoped to plan deepening |
| Day 9 (2026-05-15) | (Original: execution) | #53 closed (post-mortem authoring); planning doc splits | Re-scoped |
| Day 10 (2026-05-18) | #47, #48 (closed Day 7), #49, #50 (closed Day 8), #53 (Day 9), #54, #55 | #54, #55 closed 16:00–17:00; #47 + #49 closed at project close 17:00 | None |

## Root-cause analysis for non-zero variance

No non-zero milestone variances to analyze. Three minor sub-issue-level slips logged:

| Slip | Cause | Action taken | Outcome |
|---|---|---|---|
| Day 1 → Day 2 boundary: #2-#5 finished early morning Day 2 instead of late Day 1 | First-day fatigue after 4h charter authoring; team chose sleep over pushing to midnight | Pushed start time of Day 2 standup back 30 min to 09:00 | No knock-on effect; Day 2 still closed on time |
| Day 4 #17 hi-fi mockups: 5h estimate, actually 6h | Decomposition review screen redesign mid-session (first version didn't fit mobile) | Logged in `docs/POST_MORTEM.md` §"What didn't go well" item 3 (optimistic AI-related estimates also apply to AI-influenced UX) | Same day delivery |
| Day 3 #15 prompt templates: 3h estimate, ~4h actual | Iteration 3 of decompose template needed; R7 risk materializing | Time-box honored at 4h; final template good enough | No slip; R7 closed at mid-project review |

## Effort variance

| Person | Planned effort (h) | Estimated actual (h) | Variance |
|---|---|---|---|
| Kaan | 41 | 43 | +5% (within tolerance) |
| Caner | 38 | 41 | +8% (within tolerance) |
| **Total** | **79** | **84** | **+6%** |

Effort overruns concentrated on AI-related tasks (issues #14, #15, #38 — design only since #38 didn't ship); see post-mortem recommendation #3 ("multiply AI-task estimates by 1.4×").

## Lessons fed into post-mortem

- Issue-level slips were absorbed within the day because the daily plan had 30 min of slack.
- The Day 7 mid-project review was the highest-leverage scope decision of the project; without that explicit gate, the team would have pushed to half-implement Brickly and arrived at Day 10 with weaker artifacts.
- Schedule variance was held to zero because Phase 3 was re-scoped *before* it was nominally underway — there was nothing to slip.

See [POST_MORTEM.md](../POST_MORTEM.md) for the full retrospective.
