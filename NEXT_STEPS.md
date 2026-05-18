# Next Steps — Brickly

> Planning cycle closed **2026-05-18**. This file tracks the immediate post-close work for **presentation day (2026-05-19)** and the conceptual v2 roadmap.

---

## 1. Presentation day — 2026-05-19

### 1.1 Project board polish — manual, 5–10 min (web UI only)

The board has 55 items with all fields populated, but it needs **5 views** for the live demo. `gh` CLI doesn't support view creation, so this is the only manual step left.

Open https://github.com/users/kaanzapkinus/projects/2 → click `+ New view` for each row:

| # | View name | Layout | Group by | Sort / notes |
|---|---|---|---|---|
| 1 | **Sprint Board** | Board | `Status` | Default Kanban. Rename "View 1" to this. Sort by Priority desc, then Due Date asc. |
| 2 | **Timeline / Gantt** | Roadmap | `Phase` | Target field: `Due Date`. Zoom level: Day. ← **This is the hero shot of the demo.** |
| 3 | **Master Backlog** | Table | `Milestone` | Show all custom fields. Sort by Phase asc, Priority desc. |
| 4 | **By Assignee** | Board | `Assignees` | Two columns: Kaan vs Caner. Answers Q3 of the discussion. |
| 5 | **PMBOK Phase View** | Board | `Phase` | 5 columns, one per phase. Demonstrates framework alignment at a glance. |

### 1.2 Pre-class checklist (30 min before class)

- [ ] Laptop charged + adapter packed
- [ ] Browser tabs pre-loaded in demo order (see §1.3)
- [ ] Sync with Caner on speaking order
- [ ] Local screenshots of all 5 board views saved in case wifi dies
- [ ] Print or open on phone: [04-PRESENTATION_SCRIPT.md cheat-sheet](https://github.com/kaanzapkinus/brickly-project-plan/blob/main/README.md) (or local copy)

### 1.3 Browser tab order

Open these tabs left-to-right in this exact sequence before clicking "share screen":

1. Repo home — [github.com/kaanzapkinus/brickly-project-plan](https://github.com/kaanzapkinus/brickly-project-plan)
2. **Project board Timeline view** — primary visual artifact
3. PMBOK Phase view
4. Master Backlog (Table view)
5. By Assignee view
6. One open issue (suggest **#14 DeepSeek research** or **#12 DB schema**) — shows depth
7. [docs/PROJECT_CHARTER.md](docs/PROJECT_CHARTER.md) — scroll to SMART objectives
8. [docs/POST_MORTEM.md](docs/POST_MORTEM.md) — for Q4 challenges

### 1.4 Rehearsal

- [ ] Full run-through with Caner, time it (target **5:30–6:30**)
- [ ] Repeat any rough section
- [ ] Decide who handles which question:
  - Q1 (tool choice) — Kaan
  - Q2 (planning) — Kaan
  - Q3 (responsibilities) — Caner
  - Q4 (challenges) — Kaan (Caner adds AI-design sentence if time allows)

### 1.5 Submission

- [ ] Email instructor with repo link + project board link (per Communication Plan)
- [ ] Upload via course LMS if required
- [ ] Deliver presentation
- [ ] Take 1 screenshot post-presentation for portfolio

---

## 2. Discussion-question prep recap

The 4 mandatory questions, with the live page to switch to during the answer:

| Q | Question | Switch to | One-line answer |
|---|---|---|---|
| Q1 | Why this tool? | (stay on current view) | GitHub Projects — software project lives where code lives; industry-standard; satisfies every requirement; differentiated from teams that picked Trello. |
| Q2 | How did you plan? | [PROJECT_CHARTER.md](docs/PROJECT_CHARTER.md) → SMART objectives | PMBOK 5 phases. Day 1 Initiation (charter, risks). Days 2–4 Planning. Days 5–9 Execution. Day 10 Closure. Monitoring runs throughout. SMART objectives are numbered, Phase 4 measures against them. |
| Q3 | How did you divide responsibilities? | By Assignee view | By strength, not equally. Kaan: PM + frontend + design. Caner: backend + AI + QA. Charter rule: hours within ±15%. Tracked in KPI doc. |
| Q4 | What challenges did you face? | [POST_MORTEM.md](docs/POST_MORTEM.md) | Three: scope discipline (out-of-scope list became the lifeboat), designing for AI unpredictability (planned validation + retry layer), schedule realism around Caner's exam (front-loaded backend issues, buffer day). |

---

## 3. If hoca asks "where's the code?"

Rehearsed answer:

> "The assignment is to demonstrate IT Project Management methodology using a tool. We chose GitHub Projects, defined the project as a 10-day execution of Brickly, and produced the full plan — charter, WBS, risk register, design specs, API specs, AI prompts, gamification design, communication plan. The 27 execution-phase issues you see in `Todo` are the scoped, estimated, prioritized backlog. If someone wanted to build Brickly, they could open issue #22 today and start. We treated planning as the deliverable because that's what the assignment specifies."

If pressed further:

> "Choosing not to half-build the app was a scope decision recorded in the [mid-project review](docs/reviews/2026-05-13-midproject.md). A half-finished implementation would have weaker planning quality than a fully scoped plan with no implementation. We prioritized plan depth over partial execution."

---

## 4. Conceptual v2 backlog (post-class roadmap)

### Product features deferred from MVP
- [ ] Weekly summary chart (deferred at mid-project review #48)
- [ ] Calendar integration (Google / Outlook / iCal)
- [ ] Multi-user collaboration / shared lists
- [ ] Voice input
- [ ] PWA / offline mode
- [ ] Social streak features (friends, leaderboards)
- [ ] Native mobile apps

### Plan / methodology improvements (from post-mortem)
- [ ] Add a planning burn-down chart from Day 1 (lesson from this cycle)
- [ ] Multiply AI-task effort estimates by 1.4× by default
- [ ] Tag execution vs planning issues from day 1 (avoid narrative tension at submission)
- [ ] Front-load highest-uncertainty research (Day 1 or 2, not Day 3+)
- [ ] Apply adapter pattern (DeepSeek-style) to every external dependency including hosting

### ADRs to write when execution starts
- [ ] ADR-0002: Source of truth for "current XP" (server vs client)
- [ ] ADR-0003: AuthZ pattern for cross-user resource access (404 vs 403)

---

## 5. If picking up the execution backlog

The 27 open issues are scoped, estimated, and prioritized. To start implementation:

1. Pick the earliest dependency: **[Issue #22 — Initialize Next.js Frontend Repo](https://github.com/kaanzapkinus/brickly-project-plan/issues/22)** or **[#23 — Initialize Express Backend Repo](https://github.com/kaanzapkinus/brickly-project-plan/issues/23)**
2. Set its board status to `In Progress`
3. Create a branch: `feat/22-init-frontend`
4. Follow [CONTRIBUTING.md](CONTRIBUTING.md) standards (TS strict, conventional commits)
5. Acceptance criteria in the issue = definition of done
6. Open a PR, get partner review per branch protection rules
7. Merge → status auto-flips to `Done` → issue closes via `Closes #N` keyword

The [WBS](docs/WBS.md) dependency graph shows which issues unblock which.

---

**You've got this. Charter before code, plan before product. See you on stage. 🧱**
