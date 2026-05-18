# Risk Register — Brickly

> Phase 1 (Initiation) deliverable. Closes issue [#4](https://github.com/kaanzapkinus/brickly-project-plan/issues/4). Updated through the project — see issue #4 comments for living changes.

## Risk categories used

- **TECH** — technical, AI, hosting, dependencies
- **TIME** — schedule, deadlines
- **SCOPE** — feature creep, requirements drift
- **TEAM** — communication, availability, capability
- **EXT** — external (vendor, infrastructure)

## Risks

| ID | Category | Description | Likelihood (L/M/H) | Impact (L/M/H) | Score | Owner | Mitigation | Contingency |
|---|---|---|---|---|---|---|---|---|
| R1 | EXT | DeepSeek API downtime or rate-limit hit during demo | M | H | 6 | Caner | Pre-cache 3 sample responses; adapter interface so swap to OpenAI/Gemini takes 5 min | Demo runs against cached responses, narrated as "in case of outage we use these" |
| R2 | SCOPE | Scope creep — team keeps adding AI features (voice, calendar, social) | H | H | 9 | Kaan (PM) | Charter's out-of-scope list is the contract; weekly scope check | All new ideas logged as "Brickly v2" backlog; deferred without debate |
| R3 | TEAM | One team member ill or absent ≥ 1 day | L | H | 3 | Both | Daily standup catches early; cross-train on key tasks | Weekend reserve day in calendar; partner takes critical-path issues |
| R4 | TIME | Schedule slip due to Caner's mid-week university exam (May 13) | M | M | 4 | Caner | High-priority backend issues front-loaded to May 11 and May 12 | Buffer day on May 15 absorbs slip |
| R5 | TECH | AI hallucination produces nonsensical micro-tasks | M | M | 4 | Caner | Prompt engineering iterations (issue #15); structured JSON output; Zod validation | Frontend lets user edit/reject each task; document as known limitation |
| R6 | EXT | Vercel or Railway free-tier limit hit during demo | L | M | 2 | Kaan | Deploy by May 15 (Day 9); monitor usage; cap test traffic | Local dev demo as fallback (run on laptop, use phone hotspot) |
| R7 | TIME | Prompt template iteration takes longer than 2h | M | M | 4 | Caner | Time-box to 4h max; ship a "good enough" v1 even if v2 quality is better | Defer R1 model to v2; demo with V3 only |
| R8 | TECH | Database migration fails on Railway | L | H | 3 | Caner | Migrations tested locally first; idempotent migration files | Roll back via Prisma; reapply manually; worst case redeploy fresh DB |
| R9 | TEAM | Async communication breaks down — one of us misses a decision | M | M | 4 | Kaan | All decisions documented in issue comments or ADRs; verbal-only decisions explicitly forbidden | Mid-project review (#48) catches drift; reset scope at that point |
| R10 | SCOPE | We over-promise in the charter and can't deliver MVP | M | H | 6 | Both | MVP definition locked Day 2; every feature has acceptance criteria | Drop gamification animations first, then daily-goal, then badges — preserve auth + AI + task CRUD |

## Risk heat map (likelihood × impact)

```
              Low impact      Medium impact    High impact
High likelihood    -              -              R2
Medium likelihood  -      R5 R7 R9 R4            R1, R10
Low likelihood     R6        R8                  R3
```

## Top-3 risks for weekly review

- **R2** (scope creep) — most likely + highest impact combined.
- **R1** (DeepSeek outage) — biggest external dependency.
- **R10** (MVP overshoot) — strategic risk to the whole plan.
