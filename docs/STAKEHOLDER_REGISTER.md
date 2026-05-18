# Stakeholder Register — Brickly

> Phase 1 (Initiation) deliverable. Closes issue [#2](https://github.com/kaanzapkinus/brickly-project-plan/issues/2).

## Identified stakeholders

| ID | Name / Role | Type | Interest | Influence | Communication preference | Engagement strategy |
|---|---|---|---|---|---|---|
| S1 | Course instructor | Sponsor | High | High | Email + repo link | Manage closely. Mid-project email update + final demo. |
| S2 | Kaan Yazıcıoğlu | PM + Frontend | High | High | All channels | Manage closely. Owns daily decisions. |
| S3 | Caner Akcasu | Backend + AI + QA | High | High | WhatsApp + GitHub | Manage closely. Co-decision on tech and scope. |
| S4 | Classmates (audience) | Observer | Low | Low | In-class presentation | Inform. Deliver a clear demo. |
| S5 | DeepSeek (AI vendor) | Supplier | Low | Medium | Vendor status page / docs | Monitor. Check status before demo; have fallback. |
| S6 | Vercel / Railway | Hosting suppliers | Low | Medium | Status pages | Monitor. Pre-deploy by Day 8. |
| S7 | Future Brickly users | End users | High | Low | (Hypothetical) | Inform via charter language; design with personas. |
| S8 | Open-source library maintainers | External dependency | Low | Low | GitHub | Monitor. Pin versions; don't auto-update mid-project. |

## Power / Interest grid

```
  Influence
    High |  [S1]                  [S2, S3]
         |  Manage Closely        Manage Closely
    Med  |  [S5, S6]
         |  Monitor
    Low  |  [S4, S8]              [S7]
         |  Inform-only           Inform / design for
         +-----------------------------------------
              Low                  High
                          Interest
```

## Engagement frequency

| Stakeholder | Touchpoint | Frequency |
|---|---|---|
| Instructor | Repo activity (public) | Continuous |
| Instructor | Mid-project email | Once, end of Week 1 |
| Instructor | Final presentation | Once, May 19 |
| Caner | Daily standup | Every working day, 09:30 |
| Caner | Async via Issues | Continuous |
| DeepSeek status | Status page check | Daily 09:00 |
