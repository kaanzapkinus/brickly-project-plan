# ADR-0001: Tech Stack Decision

> Phase 2 (Planning) deliverable. Closes issue [#16](https://github.com/kaanzapkinus/brickly-project-plan/issues/16).

| Field | Value |
|---|---|
| **Date** | 2026-05-07 |
| **Status** | Accepted |
| **Authors** | Kaan Yazıcıoğlu, Caner Akcasu |
| **Supersedes** | — |

## Context

We needed to choose the technology stack for the Brickly execution-phase backlog (issues #22–46). Constraints:

- Two-person team, 5 working days of execution (later re-scoped to plan-only).
- Zero budget — all tools must be free tier.
- Both members are full-stack capable but have different strengths (Kaan = frontend; Caner = backend).
- The product is a single-user task app with an AI integration. Not at scale.
- Must integrate with DeepSeek (or be easily swappable to another LLM).

## Decision summary

| Layer | Chosen | Why |
|---|---|---|
| Frontend framework | **Next.js 14 (App Router)** | Familiar; great DX; deploy-anywhere; layout pattern matches our routing tree. |
| Styling | **Tailwind CSS** | Token-driven; pairs with our `tailwind.config.js` design-system snippet; no CSS-in-JS runtime cost. |
| Animation | **Framer Motion** | Celebratory animations (level-up, badge unlock) are first-class. |
| Backend | **Node.js + Express** | Lightweight; minimal boilerplate; ecosystem maturity. |
| ORM | **Prisma** | Type-safe; migrations are first-class; works on Railway. |
| Database | **PostgreSQL 16** | Relational fits the task hierarchy. Free tier on Railway. |
| Auth | **JWT (custom)** | No vendor lock-in; learning value; 7-day token TTL keeps it simple. |
| AI | **DeepSeek API** | Free tier; OpenAI-compatible surface; strong Turkish; DeepSeek-R1 reasoning model for decomposition. Adapter pattern lets us swap. |
| Hosting (frontend) | **Vercel** | Native Next.js host; generous free tier. |
| Hosting (backend + DB) | **Railway** | Combined Node + Postgres in one platform; free credits sufficient for demo. |

## Alternatives considered

### Frontend framework: Vite + React vs Next.js

- **Vite + React** — leaner, faster local dev. Rejected because the auth-protected layout pattern is more idiomatic in Next.js App Router, and we get SSR for free if we ever need it.
- **Remix** — strong server-form story but smaller ecosystem; team less familiar.

### Backend: Next.js Route Handlers vs separate Express

- **Next.js Route Handlers** — would collapse the stack into one app and one deploy. Rejected because bcrypt's native bindings break Vercel serverless builds, and we wanted backend to live where it could keep a long-lived DB connection.
- **Fastify** — faster than Express. Rejected for ecosystem familiarity; speed is not the bottleneck for a 1-user demo.

### Database: Supabase vs PostgreSQL + Prisma

- **Supabase** — would give us auth + Postgres + storage in one. Tempting. Rejected because it makes the JWT auth flow opaque (Supabase handles it), and the assignment values understanding the auth flow ourselves over vendor abstraction.

### AI: OpenAI vs DeepSeek vs Gemini

- **OpenAI (GPT-4o, GPT-4o-mini)** — most familiar; reliable; ~10× the cost of DeepSeek. Rejected on cost grounds for a free-tier student project, but the adapter design (#32) keeps it as a 5-minute swap if DeepSeek fails.
- **Gemini (Google)** — also free tier and capable; rejected because the team has more DeepSeek experience from prior course work.

### Hosting: Single platform (Railway) vs split (Vercel + Railway)

- **Railway only** for both frontend and backend — simpler. Rejected because Vercel is significantly better at Next.js deploys (build perf, edge runtime) and the cost is zero.

## Consequences

- **Positive:**
  - Stack is portfolio-shaped (Next.js + Tailwind + Postgres is industry-standard).
  - Zero ongoing cost for the demo.
  - DeepSeek adapter pattern means R1 (vendor outage) is mitigated.
- **Negative / risks:**
  - Tied to two free-tier hosts; if either hits a limit during execution, we'd need to migrate.
  - JWT-only auth means no refresh-token flow; if a user's token expires mid-session, they re-login. Documented in #28 as accepted limitation.
- **Tradeoffs we accept:**
  - Custom auth is more code than Supabase. Worth it for learning value and decoupling.
  - Two hosts means two deploy targets and two `.env`s. Worth it for the build-time advantages of Vercel for Next.js.

## Follow-ups

- ADR-0002: Source of truth for "current XP" (server vs client) — to be written when issue #42 is picked up in the execution phase.
- ADR-0003: AuthZ pattern for cross-user resource access (404 vs 403) — to be written alongside #29.

## Status sign-off

- Kaan Yazıcıoğlu (PM, Frontend lead) — Accepted 2026-05-07.
- Caner Akcasu (Backend / AI lead) — Accepted 2026-05-07.
