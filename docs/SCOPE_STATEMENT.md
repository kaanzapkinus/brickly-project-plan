# Scope Statement — Brickly

> Phase 2 (Planning) deliverable. Closes issue [#7](https://github.com/kaanzapkinus/brickly-project-plan/issues/7). Baselined 2026-05-06 (end of Day 2). Any post-baseline change requires a written change request.

## Product scope vs project scope

| Dimension | Definition |
|---|---|
| **Product scope** | What Brickly *does* — the features and behaviors a user experiences. |
| **Project scope** | What the team *delivers* — for this course assignment, the deliverable is the **plan**, not the running application. The Phase 3 execution issues describe the implementation backlog that would build the product but are out of the deliverable scope for the IT Project Management assignment. |

## Product scope — MVP features (in-scope)

Each feature is enumerated with a one-sentence definition. Feature ownership maps to one or more issues in the Phase 3 execution backlog.

| # | Feature | One-sentence definition | Issue(s) |
|---|---|---|---|
| 1 | User registration | A new user signs up with email + password and is issued a JWT. | #27 |
| 2 | User login | Returning user authenticates with email + password and is issued a JWT. | #28 |
| 3 | Big-task input | User enters a free-text large goal into a single input field. | #37 |
| 4 | AI Socratic clarification | After submission, AI returns 3–5 clarifying questions; user answers each in turn. | #33, #38 |
| 5 | AI task decomposition | After clarification, AI returns 15–25 micro-tasks (30–90 min each) for review. | #34, #40 |
| 6 | Edit / accept / reject candidate tasks | User reviews and adjusts AI-generated tasks before committing them. | #40 |
| 7 | Hierarchical task list | Big tasks are parent rows; micro-tasks are children with checkboxes. | #39 |
| 8 | Mark task complete | User checks off a micro-task; completion is idempotent and awards XP. | #29, #41 |
| 9 | Drag-to-reorder | User reorders micro-tasks within a parent; order persists. | #39 |
| 10 | XP system + level progression | Completing a task awards XP; level thresholds advance the user's level. | #42 |
| 11 | Streak tracking | Daily completion increments a streak counter; missed days reset it. | #43 |
| 12 | Badges / achievements | Six launch badges unlock on milestone counts (first task, 7-day streak, level 5, etc.). | #44 |
| 13 | Daily goal | User sets a daily XP target; dashboard ring fills as the user completes tasks. | #45 |
| 14 | Streak reminder notification | Browser notification at 20:00 local time if streak is at risk and user is idle. | #46 |
| 15 | Progress dashboard | Single screen showing today's progress, current streak, recent badges, XP bar. | #39, #45 |

## Out-of-scope (deliberate exclusions)

| Exclusion | Rationale |
|---|---|
| Native mobile apps (iOS / Android) | Web is responsive; native is a separate engineering effort. |
| Multi-user collaboration / shared lists | Single-user MVP keeps complexity contained. |
| Calendar integration (Google / Outlook / iCal) | Out-of-scope to avoid expanding the integration surface. |
| Voice input | Requires speech-to-text infrastructure beyond 10-day window. |
| Offline mode / PWA service worker | Stretch goal; deferred to v2. |
| Payment, subscription, monetization | No business model in this academic project. |
| Push notifications (mobile/email) | Web browser notifications only. |
| Internationalization beyond English & Turkish | Two-language support is enough for the audience. |
| Accessibility certification (WCAG audit) | Best-effort accessibility in design; formal audit deferred. |
| Production-grade security review / pen-test | Basic auth + HTTPS only; no formal security assessment. |
| Weekly summary chart | Originally in-scope, deferred to v2 at the mid-project review (#48). |
| Social streak features (friends, leaderboards) | Falls outside the personal-productivity focus. |

## Acceptance criteria — project deliverable

The **project deliverable** (not product) is judged against:

- [x] 50+ issues created across 5 PMBOK milestones, fully tagged.
- [x] All Phase 1–2 issues closed with linked planning artifacts in `docs/`.
- [x] Phase 3 execution backlog scoped, prioritized, estimated, and visible on the board.
- [x] All 12 planning documents committed to `docs/` (charter + 6 supporting artifacts + scope + post-mortem + ADR + 2 reviews).
- [x] Charter signed (commit-authored) by both team members.
- [x] Risk register maintained — at least one risk added after Day 1 (R7).
- [x] Mid-project review held with minutes committed.
- [x] Live presentation delivered on 2026-05-19.

## Scope baseline lock

- **Locked:** 2026-05-06 23:59
- **Lock authority:** Kaan Yazıcıoğlu (Project Manager)
- **Witness:** Caner Akcasu (commit co-author on charter)
- **Change request template:** `docs/CHANGE_REQUEST_TEMPLATE.md` (none submitted as of project close)

## Change log

| Date | Change | Rationale | Approver |
|---|---|---|---|
| 2026-05-13 | Weekly summary chart moved from in-scope to out-of-scope | Mid-project review (#48) — implementation cost exceeded value for the planning deliverable | Both members agreed |
| 2026-05-13 | Execution-phase deliverables formally moved out of project scope | Confirmed plan-only deliverable; recorded in mid-project minutes | Both members agreed |
