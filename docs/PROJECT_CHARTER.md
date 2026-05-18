# Project Charter — Brickly

> First-day Initiation deliverable for the IT Project Management course final assignment. Version 1.0, prepared 2026-05-05.

| Field | Value |
|---|---|
| **Project name** | Brickly — AI-powered micro-task to-do app |
| **Charter version** | 1.0 |
| **Date prepared** | 2026-05-05 |
| **Prepared by** | Kaan Yazıcıoğlu, Project Manager |
| **Approved by** | Kaan Yazıcıoğlu (PM) · Caner Akcasu (Developer) · Course Instructor (Sponsor) |
| **Project duration** | 2026-05-05 → 2026-05-18 (10 working days) |
| **Submission / live presentation** | 2026-05-19 (one day after project close) |
| **Budget** | 0 € (student project; all tools used at free tier) |

---

## 1. Project Purpose & Business Justification

Existing to-do apps fall into two camps: lightweight list managers (Todoist, TickTick, Microsoft To Do, Any.do) that don't help with task paralysis, and AI-powered planners (Motion, Reclaim.ai) that cost $30+/month and target busy professionals. Casual users — students, hobbyists, people with ADHD — are stuck choosing between a tool that's too dumb or a tool that's too expensive.

**Brickly closes that gap.** It uses Socratic AI questioning to clarify big tasks, then automatically breaks them into 30–90 minute micro-steps. Duolingo-style gamification (XP, streaks, badges) rewards completion and prevents drop-off. The product hypothesis is that *clarity + small wins* is a better answer to procrastination than *better lists or stricter scheduling*.

**For the course**, Brickly is the vehicle for demonstrating the full PMBOK 5-phase project management lifecycle. The grade is measured on the *quality of the plan*, not the working code; the 10-day execution timeline is the deliverable.

---

## 2. SMART Project Objectives

Each objective is **S**pecific, **M**easurable, **A**chievable, **R**elevant, **T**ime-bound.

### Objective 1 — Plan completeness
By **2026-05-18**, produce a GitHub Projects board containing **at least 50 issues** distributed across **5 PMBOK-phase milestones**, with 100% of issues tagged with a priority, type, phase, assignee, and effort estimate.

### Objective 2 — Documentation depth
By **2026-05-06** (end of Day 2), publish six core planning documents in the repo's `docs/` folder: Project Charter, Stakeholder Register, Risk Register, Communication Plan, Work Breakdown Structure, and SMART Goals brief — each ≥ 1 page of substantive content.

### Objective 3 — Schedule realism
**100% of milestones** must close on or before their due date. Schedule variance (planned vs actual finish, in days) must be **≤ 1 day** for each milestone.

### Objective 4 — Team load balance
By project close, **work hours assigned to Kaan and Caner must be within ±15%** of each other. Tracked via the `Effort (hours)` custom field, reviewed at the end of each phase.

### Objective 5 — Presentation readiness
By **2026-05-18 17:00**, deliver a **5–7 minute live presentation** that covers the four mandatory discussion questions (tool choice rationale, planning methodology, responsibility split, challenges faced) with the GitHub Projects board open and demonstrated.

---

## 3. High-Level Project Description

Brickly is a responsive web application. The user enters a large goal in free text. The frontend submits it to the backend, which forwards a structured prompt to the DeepSeek API. The AI responds with 3–5 Socratic clarifying questions. After the user answers, a second prompt asks the AI to produce a structured list of 15–25 micro-tasks (each scoped to 30–90 minutes of work) with suggested ordering. The user can edit, reorder, accept, or reject each. Accepted tasks enter the user's task list. Completing a task awards XP (10–50 based on estimated difficulty), advances a daily streak, and may unlock badges. Levels are gated by total XP. A weekly summary view shows progress.

### Tech stack (planned)

| Layer | Technology | Rationale |
|---|---|---|
| Frontend | Next.js 14 (App Router) + Tailwind CSS + Framer Motion | Modern React stack; Tailwind for fast iteration; Framer for celebratory animations on task completion. |
| Backend | Node.js + Express | Lightweight, familiar, minimal boilerplate for a 10-day project. |
| Database | PostgreSQL | Relational structure fits the task hierarchy (project → milestone → subtask) cleanly. |
| AI | DeepSeek API | Free tier; OpenAI-compatible API surface; strong Turkish support; reasoning model (DeepSeek-R1) ideal for decomposition. |
| Auth | JWT | Industry standard; no third-party dependency. |
| Hosting | Vercel (frontend) + Railway (backend + DB) | Both have generous free tiers; both support GitHub auto-deploy. |

---

## 4. Scope

### In-scope (MVP)

- User registration and login (email + password, JWT-based session).
- Single-user task lists (one user's data is isolated).
- Big-task input field with AI-driven Socratic clarification flow.
- AI-driven decomposition into micro-tasks (15–25 per big task).
- Manual edit of generated micro-tasks before acceptance.
- Task list view with hierarchical display (big task → sub-tasks).
- Mark task complete / undo / delete / edit.
- XP awarded per completion (10–50 by difficulty).
- Streak counter (consecutive days with at least 1 completion).
- Level progression (level 2 at 100 XP, level 3 at 250 XP, etc.).
- Badge unlocks for milestone counts (10 completions, 7-day streak, etc.).
- Daily goal setting.
- Weekly summary chart.
- In-app streak reminder notification (browser).

### Out-of-scope

- Native mobile apps (iOS/Android). Web is responsive, but not packaged.
- Multi-user collaboration (shared task lists, team mode).
- Calendar integration (Google Calendar, Outlook, iCal export).
- Voice input.
- Offline mode / PWA.
- Payment / subscription / monetization features.
- Email or push notifications (web-only browser notifications are in scope).
- Internationalization beyond English and Turkish.
- Accessibility certification (WCAG audit is documented as a future improvement).
- Production-grade security review (basic auth + HTTPS only; no penetration testing).

---

## 5. Key Deliverables

| # | Deliverable | Owner | Due |
|---|---|---|---|
| D1 | Project Charter (this document) | Kaan | 2026-05-05 |
| D2 | Stakeholder Register | Kaan | 2026-05-05 |
| D3 | Communication Plan | Kaan | 2026-05-05 |
| D4 | Initial Risk Register | Kaan + Caner | 2026-05-05 |
| D5 | Scope Statement | Kaan | 2026-05-06 |
| D6 | Work Breakdown Structure | Kaan + Caner | 2026-05-06 |
| D7 | User Personas (3) + User Flow Diagram | Kaan | 2026-05-06 |
| D8 | Wireframes (5 screens) | Kaan | 2026-05-06 |
| D9 | Database Schema + API Specification | Caner | 2026-05-07 |
| D10 | DeepSeek prompt templates | Caner | 2026-05-07 |
| D11 | Hi-fi Figma mockups | Kaan | 2026-05-08 |
| D12 | Functional MVP deployment (Vercel + Railway) | Kaan + Caner | 2026-05-15 |
| D13 | E2E test report | Caner | 2026-05-18 |
| D14 | Post-mortem + Lessons Learned report | Kaan + Caner | 2026-05-18 |
| D15 | Live class presentation | Kaan + Caner | 2026-05-18 |

---

## 6. Stakeholders Summary

(Full register in [06-SUPPORTING_ARTIFACTS.md](06-SUPPORTING_ARTIFACTS.md#stakeholder-register))

| Stakeholder | Role | Interest | Influence |
|---|---|---|---|
| Course instructor | Sponsor / approver of the plan | High (grades it) | High |
| Kaan Yazıcıoğlu | Project Manager + Frontend lead | High | High |
| Caner Akcasu | Backend + AI Integration lead | High | High |
| Classmates | Audience for live presentation | Low | Low |
| DeepSeek (vendor) | API provider | Low | Medium (service availability) |
| End users (post-class, hypothetical) | Consumers of the app | High | Low |

---

## 7. High-Level Milestones

| Phase | Name | Window | Key gate |
|---|---|---|---|
| 1 | Initiation | 2026-05-05 | All 4 initiation docs published, repo & board live |
| 2 | Planning | 2026-05-06 → 2026-05-08 | Scope baselined; WBS approved; design + tech specs done |
| 3 | Execution | 2026-05-11 → 2026-05-15 | Functional MVP deployed |
| 4 | Monitoring & Control | Continuous through Phases 2–3, formal review 2026-05-18 | All KPIs within thresholds |
| 5 | Closure | 2026-05-18 | Presentation delivered, post-mortem published |

---

## 8. Project Manager & Authority

**Project Manager:** Kaan Yazıcıoğlu.

The PM is authorized to:

- Make day-to-day scope adjustments within the in-scope list (re-prioritize, defer non-MVP items).
- Reassign issues between team members to balance load.
- Approve sub-1-day schedule slips on internal milestones.

The PM must escalate to (or co-decide with) the partner before:

- Removing or adding to the in-scope list.
- Slipping a phase-level milestone beyond 1 day.
- Changing the tech stack.
- Cancelling deliverables.

---

## 9. Assumptions

1. DeepSeek API free tier remains available and within reasonable rate limits through the project window.
2. Both team members have ≥ 4 hours/day available, including weekends if needed for catch-up.
3. No university examinations clash critically with the project window (a check has been done; one mid-week exam is acknowledged in the risk register).
4. GitHub services (Issues, Projects, Actions) remain available — incidents within 24h SLA are tolerable.
5. Vercel and Railway free tiers will absorb a 2-person dev/demo deployment.
6. The instructor accepts a planning-grade submission with a partial MVP — i.e., the plan is graded, the code is "evidence the plan was executed."

---

## 10. Constraints

1. **Time:** 10 working days, hard deadline 2026-05-18.
2. **Cost:** Zero budget. No paid SaaS subscriptions.
3. **Team:** Exactly 2 people. No external contractors, no AI agents acting as team members.
4. **Tooling:** Must use GitHub Projects as the project management tool (course requirement; assigned per the one-tool-per-group rule).
5. **Course constraint:** Final presentation is delivered live in the scheduled class on 2026-05-18.
6. **Skill constraint:** Kaan is primarily a frontend developer; Caner is primarily backend. Neither is an experienced ML engineer — the AI integration is API-call-level only.

---

## 11. High-Level Risks

(Full risk register in [06-SUPPORTING_ARTIFACTS.md](06-SUPPORTING_ARTIFACTS.md#risk-register))

| ID | Risk | Impact | Likelihood | Mitigation |
|---|---|---|---|---|
| R1 | DeepSeek API downtime or rate limit hit during demo | High | Medium | Pre-cache demo responses; fallback adapter ready for OpenAI/Gemini |
| R2 | Scope creep (team keeps adding features) | High | High | MVP-first; in-scope list is the contract; PM has authority to defer |
| R3 | Team member illness or absence | High | Low | Daily 15-min standup catches issues early; one weekend rezerv day |
| R4 | Schedule slip due to mid-week exam | Medium | Medium | Buffer day built into Phase 3; high-priority work front-loaded |
| R5 | AI hallucination produces nonsensical micro-tasks | Medium | Medium | Prompt engineering iteration; user can edit/reject; documented as limitation |
| R6 | Deployment platform free-tier limits hit | Medium | Low | Pre-deploy by Day 8; if hit, fall back to local demo |

---

## 12. Communication Cadence (Summary)

(Full plan in [06-SUPPORTING_ARTIFACTS.md](06-SUPPORTING_ARTIFACTS.md#communication-plan))

| Touchpoint | Channel | Frequency |
|---|---|---|
| Daily standup (15 min) | WhatsApp voice call | Every working day, 09:30 |
| Async status updates | GitHub Issues comments | Continuous |
| End-of-phase review | In-person, 30 min | After each phase milestone closes |
| Sponsor (instructor) report | Email / repo link | Once mid-project + final |

---

## 13. Charter Approval

By signing below (in commit history), the parties agree to the scope, schedule, and constraints described above.

| Role | Name | Date |
|---|---|---|
| Project Manager | Kaan Yazıcıoğlu | 2026-05-05 |
| Developer (Backend / AI) | Caner Akcasu | 2026-05-05 |
| Sponsor | Course Instructor | (acknowledged at submission) |

---

*Version 1.0 — initial charter. Subsequent versions tracked via Git history at `docs/PROJECT_CHARTER.md`.*
