# `docs/` — Planning artifacts

This folder contains the planning artifacts referenced from the [Project Charter](PROJECT_CHARTER.md) and the closed [issues](https://github.com/kaanzapkinus/brickly-project-plan/issues?q=is%3Aissue+is%3Aclosed).

## File map

### Phase 1 — Initiation
| File | Closes issue |
|---|---|
| [PROJECT_CHARTER.md](PROJECT_CHARTER.md) | [#1](https://github.com/kaanzapkinus/brickly-project-plan/issues/1) |
| [STAKEHOLDER_REGISTER.md](STAKEHOLDER_REGISTER.md) | [#2](https://github.com/kaanzapkinus/brickly-project-plan/issues/2) |
| [SMART_GOALS.md](SMART_GOALS.md) | [#3](https://github.com/kaanzapkinus/brickly-project-plan/issues/3) |
| [RISK_REGISTER.md](RISK_REGISTER.md) | [#4](https://github.com/kaanzapkinus/brickly-project-plan/issues/4) |
| [COMMUNICATION_PLAN.md](COMMUNICATION_PLAN.md) | [#5](https://github.com/kaanzapkinus/brickly-project-plan/issues/5) |

### Phase 2 — Planning
| File | Closes issue |
|---|---|
| [SCOPE_STATEMENT.md](SCOPE_STATEMENT.md) | [#7](https://github.com/kaanzapkinus/brickly-project-plan/issues/7) |
| [WBS.md](WBS.md) | [#8](https://github.com/kaanzapkinus/brickly-project-plan/issues/8) |
| [adr/0001-tech-stack.md](adr/0001-tech-stack.md) | [#16](https://github.com/kaanzapkinus/brickly-project-plan/issues/16) |

### Phase 4 — Monitoring & Control
| File | Closes issue |
|---|---|
| [KPI_TRACKING.md](KPI_TRACKING.md) | [#47](https://github.com/kaanzapkinus/brickly-project-plan/issues/47) |
| [reviews/2026-05-13-midproject.md](reviews/2026-05-13-midproject.md) | [#48](https://github.com/kaanzapkinus/brickly-project-plan/issues/48) |
| [reviews/SCHEDULE_VARIANCE.md](reviews/SCHEDULE_VARIANCE.md) | [#49](https://github.com/kaanzapkinus/brickly-project-plan/issues/49) |
| [../CONTRIBUTING.md](../CONTRIBUTING.md) + [../.github/workflows/ci.yml](../.github/workflows/ci.yml) | [#50](https://github.com/kaanzapkinus/brickly-project-plan/issues/50) |

### Phase 5 — Closure
| File | Closes issue |
|---|---|
| [POST_MORTEM.md](POST_MORTEM.md) | [#53](https://github.com/kaanzapkinus/brickly-project-plan/issues/53) |

## What's not here (and why)

The detailed design / database / API / AI artifacts (`docs/design/`, `docs/db/`, `docs/api/`, `docs/ai/`, `docs/personas/`) were scoped in their respective closed issues (#9–#21) as planning outputs. The work behind those was done — sketches, schema drafts, prompt iteration — but the polished, committed artifacts are out of scope for this plan-only deliverable. The relevant decisions are summarized in the [ADR](adr/0001-tech-stack.md), the [POST_MORTEM](POST_MORTEM.md), and the [mid-project review](reviews/2026-05-13-midproject.md).

If you're a future team picking up the [execution backlog](https://github.com/kaanzapkinus/brickly-project-plan/issues?q=is%3Aopen): the spec lives in the issue acceptance criteria, the tech direction in the ADR, and the architectural intent in the WBS hierarchy.
