# Post-Mortem — Brickly

> Phase 5 (Closure) deliverable. Closes issue [#53](https://github.com/kaanzapkinus/brickly-project-plan/issues/53). Authored jointly by Kaan Yazıcıoğlu and Caner Akcasu on 2026-05-18.

## Project scorecard

| Dimension | Result |
|---|---|
| Issues created | 55 ✅ (target ≥ 50) |
| Planning issues closed | 28 ✅ (Phases 1, 2, 4, 5-prep) |
| Execution backlog defined | 27 issues, scoped & estimated ✅ |
| Milestones on time | 4/4 closed phases on time, 0-day variance ✅ |
| Documentation depth | 12 files in `docs/` ✅ (target ≥ 6) |
| Load balance (Kaan/Caner) | 1.05 ratio ✅ (target 0.85–1.15) |
| Risks materialized | 1 of 10 (R7 prompt iteration) ✅ (target < 30%) |
| Presentation delivered | 6:10 timing in dry-run ✅ (target 5–7 min) |

## What went well

### 1. Charter-before-anything
We invested most of Day 1 on the Project Charter, Stakeholder Register, Risk Register, and Communication Plan before opening any technical issue. Felt slow at the time. Paid back immediately:
- Day 2's WBS slotted neatly into the charter's scope.
- When AI-feature scope creep surfaced on Day 3, the out-of-scope list shut down the conversation in 30 seconds.
- Risk R7 (prompt iteration time) was identified on Day 1 and added to the register; when it materialized on Day 3, we already had the time-box mitigation ready.

### 2. Plan-only scope discipline
At the mid-project review (Day 7, [reviews/2026-05-13-midproject.md](reviews/2026-05-13-midproject.md)) we explicitly chose to keep the deliverable as the plan rather than half-implement Brickly. This freed the back half of the project to deepen the plan (mockups, prompt templates, ADRs) instead of context-switching between PM and code. The board ended up with **substantive planning artifacts** rather than 30 half-finished features.

### 3. WBS dependency graph forced sequencing discipline
The 3-level WBS made it obvious that DB schema (#12) and API spec (#13) had to precede AI integration design (#15) which had to precede frontend Q&A design (#38). The board's Timeline view rendered this dependency chain visually — when we drifted, the chart told us.

## What didn't go well

### 1. No real burn-down chart
We tracked progress by gut feeling and end-of-phase counts. A daily "remaining planning issues vs day" chart would have caught the Day 3 effort imbalance (K4 KPI variance) a day earlier. We have the data — we just never plotted it.

### 2. Prompt research scheduled too late
DeepSeek research (#14) and prompt templates (#15) landed on Day 3. With hindsight: this was the highest-uncertainty work in the entire plan and should have been Day 1 — or at worst Day 2 — so that any nasty surprises had buffer left. We treated it like normal "Phase 2 planning" work; it deserved special placement.

### 3. Effort estimates were optimistic on AI tasks
Issues #14, #15, #33, #34 collectively were estimated at 10h. Actual planning effort for the parts we did was ~14h (and the implementation issues would likely be 1.4× their estimates too based on prompt-iteration empirics from #15). Lesson: AI tasks deserve a 1.4× effort multiplier when there's no team prior experience.

## Surprises

### 1. The 6 supporting artifacts naturally split into separate files
We initially bundled them in one document for editing speed. When we tried to commit, we realized closed-issue acceptance criteria explicitly reference individual files (`docs/STAKEHOLDER_REGISTER.md` etc.). Splitting was easy because the sections were self-contained — but the bundling-first approach was wrong; we should have split from the start.

### 2. GitHub Projects v2 doesn't let you create views via CLI
Provisioning the entire board (issues, milestones, labels, custom fields, item field values) via `gh` CLI worked beautifully. But the 5 views (Sprint Board, Timeline, Master Backlog, By Assignee, PMBOK Phase) had to be created in the web UI. Not a blocker, but breaks the "fully automated provisioning" story we'd have liked to claim in the presentation.

### 3. Em-dash byte handling in PowerShell 5.1
Trivial-sounding but real. PowerShell 5.1 reads BOM-less UTF-8 files as Windows-1252 by default. Em-dash characters in the regex source got mojibake'd and the parser silently matched zero issues. Cost ~10 minutes. Lesson: always pass explicit `[System.Text.Encoding]::UTF8` to `ReadAllText` when scripting on Windows.

## Recommendations for "Brickly v2" (or any future planning cycle)

1. **Front-load the highest-uncertainty research.** Anything we haven't done before goes in Day 1 or 2, not Day 3+. Prompt research, API integration probes, vendor research.
2. **Maintain a plot, not a feeling.** A simple daily count of remaining issues in a `docs/BURN_DOWN.md` table would have flagged the load imbalance a day earlier.
3. **Multiply AI-task estimates by 1.4×.** Apply this until empirical data says otherwise.
4. **Split docs from day 1.** Don't bundle planning artifacts for editing speed — go straight to standalone files matching acceptance-criteria paths.
5. **Tag execution vs planning issues explicitly.** A label like `tier: planning` vs `tier: execution` would have prevented narrative tension at submission time over which issues were expected to be Done vs Todo.
6. **Have a fallback for any tool dependency.** The adapter pattern we spec'd for DeepSeek (#32) is the model — apply the same thinking to Vercel, Railway, GitHub itself.

## Sign-off

| Role | Name | Date |
|---|---|---|
| Project Manager | Kaan Yazıcıoğlu | 2026-05-18 |
| Developer / QA | Caner Akcasu | 2026-05-18 |
