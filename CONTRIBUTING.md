# Contributing to CareGrid

Thank you for contributing to **CareGrid — Rural Healthcare Connectivity Platform**.

## Before You Start

1. Read `README.md`.
2. Review `ARCHITECTURE.md` and `DEVELOPMENT.md`.
3. Search existing issues and pull requests.
4. Never commit secrets, credentials, patient information, database dumps, or real healthcare data.

## Development Workflow

```bash
pnpm install
pnpm build
pnpm test
```

API:

```bash
pnpm --filter @rhcp/api dev
```

Mobile:

```bash
pnpm --filter @rhcp/mobile start
cd apps/mobile
pnpm android
```

## Branching

Use:

- `main` — stable code
- `develop` — integration
- `feature/<name>` — features
- `fix/<name>` — bug fixes
- `docs/<name>` — documentation
- `chore/<name>` — maintenance

Normal feature work should flow through pull requests rather than direct pushes to `main`.

## Commits

Keep commits focused. Prefer Conventional Commit-style messages:

```text
feat: add referral appointment workflow
fix: prevent duplicate appointment booking
docs: update deployment guide
test: add appointment concurrency tests
refactor: simplify inventory service
chore: update dependencies
```

## Pull Requests

A PR should explain:

- What changed.
- Why it changed.
- How it was tested.
- Database/migration impact.
- API contract impact.
- Frontend impact.
- Security implications.

Before review:

```bash
pnpm build
pnpm test
```

Include screenshots for meaningful UI changes.

## Database

The API uses PostgreSQL and Prisma. Schema changes should include reviewed migrations and appropriate tests. Avoid destructive migrations unless explicitly approved.

## API

Update API documentation/contracts when request or response behavior changes. Breaking changes require a migration strategy.

## Frontend

Mobile and desktop changes should handle loading, empty, error, offline, and stale-data states. User-facing text should support localization.

## Security

Do not report vulnerabilities through public GitHub issues. Follow `SECURITY.md`.
