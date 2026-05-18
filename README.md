# Brickly — Project Plan

> **IT Project Management course final assignment.**
> This repository contains the **project plan** and management artifacts for Brickly. The assignment is to plan the project, not to ship the app — Brickly is the case study used to demonstrate end-to-end IT project planning in GitHub Projects.

| Field | Value |
|---|---|
| **Course** | IT Project Management |
| **Team** | Kaan Yazıcıoğlu (#97364, SD1) + Caner Akcasu (#97334, SD1) |
| **Tool** | GitHub Projects (Projects v2) |
| **Framework** | PMBOK 5 phases — Initiation → Planning → Execution → Monitoring & Control → Closure |
| **Project window** | 2026-05-05 → 2026-05-18 (10 working days) |
| **Submission / live presentation** | 2026-05-19 |

---

## Brickly — the concept

An AI-powered to-do app concept that solves big-task paralysis. The user types a large task ("write my thesis"), Brickly asks 3–5 Socratic clarifying questions, then uses the DeepSeek API to break the task into 15–25 micro-steps (30–90 minutes each). Duolingo-style gamification (XP, streaks, badges, levels) rewards each completed step.

**Differentiator:** combines Claude-style Socratic questioning with Duolingo-style gamification — neither big-list apps (Todoist, TickTick) nor expensive AI planners (Motion, Reclaim at $30+/mo) do both for a casual audience.

---

## Where the plan lives

| Artifact | Where |
|---|---|
| **Project board** (milestones, issues, custom fields, multiple views) | [Projects tab](https://github.com/kaanzapkinus/brickly-project-plan/projects) |
| **Issues** (55 work items across 5 PMBOK phases) | [Issues tab](https://github.com/kaanzapkinus/brickly-project-plan/issues) |
| **Milestones** (5 — one per PMBOK phase, with due dates) | [Milestones](https://github.com/kaanzapkinus/brickly-project-plan/milestones) |
| **Project Charter** (SMART objectives, scope, risks, deliverables) | [docs/PROJECT_CHARTER.md](docs/PROJECT_CHARTER.md) |
| **Scope Statement** (in/out-of-scope, baseline) | [docs/SCOPE_STATEMENT.md](docs/SCOPE_STATEMENT.md) |
| **Stakeholder Register** | [docs/STAKEHOLDER_REGISTER.md](docs/STAKEHOLDER_REGISTER.md) |
| **Risk Register** (10 risks, heat map, top-3) | [docs/RISK_REGISTER.md](docs/RISK_REGISTER.md) |
| **Work Breakdown Structure** (3 levels + mermaid diagram) | [docs/WBS.md](docs/WBS.md) |
| **Communication Plan** | [docs/COMMUNICATION_PLAN.md](docs/COMMUNICATION_PLAN.md) |
| **SMART Goals Brief** | [docs/SMART_GOALS.md](docs/SMART_GOALS.md) |
| **KPI Tracking** (with variance log) | [docs/KPI_TRACKING.md](docs/KPI_TRACKING.md) |
| **Mid-Project Review minutes** | [docs/reviews/2026-05-13-midproject.md](docs/reviews/2026-05-13-midproject.md) |
| **Schedule Variance Analysis** | [docs/reviews/SCHEDULE_VARIANCE.md](docs/reviews/SCHEDULE_VARIANCE.md) |
| **Tech Stack ADR** | [docs/adr/0001-tech-stack.md](docs/adr/0001-tech-stack.md) |
| **Post-Mortem** | [docs/POST_MORTEM.md](docs/POST_MORTEM.md) |
| **Contribution standards** | [CONTRIBUTING.md](CONTRIBUTING.md) |

---

## PMBOK 5 phases — at a glance

| Phase | Window | Key deliverables |
|---|---|---|
| 1. Initiation | 2026-05-05 | Project charter, stakeholder register, SMART goals, initial risk register, communication plan, infrastructure setup |
| 2. Planning | 2026-05-06 → 08 | Scope statement, WBS, user personas, user flow, wireframes, hi-fi mockups, design system, gamification UI, component inventory, DB schema, API spec, DeepSeek research, prompt templates, tech-stack ADR |
| 3. Execution | 2026-05-11 → 15 | Frontend & backend scaffolding, authentication, task CRUD, AI integration (clarify + decompose), Q&A UI, hierarchical task list, gamification (XP, streaks, badges, daily goal, notifications) |
| 4. Monitoring & Control | continuous through Phases 2–3, formal close 2026-05-18 | KPI tracking, mid-project review, schedule variance analysis, code-review standards |
| 5. Closure | 2026-05-18 | E2E testing, deployment, post-mortem, presentation prep, dry run |

The Phase 3 execution issues are scoped, prioritized, and estimated — they represent the implementation backlog that a future team could pick up from issue #22 onwards. For this course assignment, the plan itself is the deliverable.

---

## Team responsibilities

| Member | Role | Areas |
|---|---|---|
| Kaan Yazıcıoğlu ([@kaanzapkinus](https://github.com/kaanzapkinus)) | Project Manager + Frontend Developer + UX Designer | UI, Figma, gamification visuals, project board management, charter |
| Caner Akcasu ([@Canerakcasu](https://github.com/Canerakcasu)) | Backend Developer + AI Integration Specialist + QA | Node/Express, PostgreSQL, DeepSeek integration, prompt engineering, testing |

The charter has an explicit load-balance rule: assigned effort hours must stay within ±15% between team members, reviewed at each phase boundary.

---

## How to navigate this repo for a review

1. **Start with the Project board** ([Projects tab](https://github.com/kaanzapkinus/brickly-project-plan/projects)) — switch to the **Timeline view** for the visual Gantt of all 5 PMBOK phases.
2. Open **[docs/PROJECT_CHARTER.md](docs/PROJECT_CHARTER.md)** — read the 5 SMART objectives, scope, and high-level risks.
3. Open **[docs/SUPPORTING_ARTIFACTS.md](docs/SUPPORTING_ARTIFACTS.md)** — full stakeholder register, risk register, WBS, communication plan, SMART goals brief, KPI tracking.
4. Browse **[Issues](https://github.com/kaanzapkinus/brickly-project-plan/issues)** — every issue has an acceptance-criteria checklist, labels, milestone, assignee, and effort estimate.
