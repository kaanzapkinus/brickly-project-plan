# Contributing to Brickly

> Phase 4 (Monitoring & Control) deliverable. Companion to issue [#50](https://github.com/kaanzapkinus/brickly-project-plan/issues/50).

This repository contains the **project plan** for Brickly. The execution-phase backlog (issues #22–46, #51, #52) describes how a future contributor would build the app. The conventions below apply to anyone picking up that work, and to ongoing maintenance of the plan documents.

## Branch protection

The `main` branch requires:
- 1 approving review per PR
- CI workflow (`.github/workflows/ci.yml`) to pass — lint, typecheck, tests

Direct pushes to `main` are not allowed.

## Branch naming

| Type | Prefix | Example |
|---|---|---|
| Feature | `feat/` | `feat/27-register-endpoint` |
| Bug fix | `fix/` | `fix/jwt-expiry-handling` |
| Docs / planning | `docs/` | `docs/update-risk-register` |
| Chore / infra | `chore/` | `chore/upgrade-prisma` |
| ADR | `adr/` | `adr/0002-xp-source-of-truth` |

Branch names include the issue number where applicable.

## Commit message convention

[Conventional Commits](https://www.conventionalcommits.org/) format with the issue number in square brackets:

```
[#N] <type>(<scope>): short summary

Optional body explaining why.

Closes #N (only on the final commit that completes the issue)
```

Types in use: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `style`, `design`, `db`.

Example:

```
[#27] feat(api): POST /auth/register with bcrypt + JWT

Hashes password at cost 10. Returns JWT with 7-day expiry. Rejects duplicate emails with 409.

Closes #27
```

## Code standards (for the execution-phase backlog)

- **TypeScript strict mode** is required everywhere. No `any` except when typing third-party callbacks that we control via wrapper.
- **ESLint + Prettier** run via husky pre-commit. Don't bypass with `--no-verify` — fix the issue.
- **No dead code.** If a function is unused after a refactor, delete it.
- **Comments explain *why*, not *what*.** Variable names explain *what*.
- **Tests must hit a real database**, not mocks. (See R8 in the risk register.)
- **Acceptance criteria are the definition of done.** A PR closes an issue only when every checkbox is verifiable.

## Authorization for risky actions

The following actions require both team members' sign-off (via a comment with thumbs-up reaction):

- Force push to any branch
- Database migration on Railway
- Change to `.env` shape (adding/removing required vars)
- Bumping a major version of a dependency
- Removing an issue or milestone

## Issue workflow

1. Open an issue (or pick one from the backlog).
2. Tag with type / priority / phase labels.
3. Move project board status to `In Progress` when work starts.
4. Open a draft PR early — discussion happens on the PR, decisions are reflected in the issue.
5. PR review: the *other* team member reviews. Approve = LGTM + at least one concrete comment.
6. Merge → status moves to `Done` → issue auto-closes via `Closes #N` keyword.

## Plan-document maintenance

When updating a planning document (charter, supporting artifacts, post-mortem):

- Version-bump the relevant header.
- Open a PR titled `docs: <document> <change-summary>`.
- The other team member reviews to catch drift between artifacts.
