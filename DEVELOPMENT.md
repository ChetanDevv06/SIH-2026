# Development Guide

## Prerequisites

The project uses a pnpm workspace and includes Node.js/TypeScript applications, PostgreSQL, Redis, and Android tooling for mobile development.

Check the repository configuration for exact supported versions.

## Install

```bash
pnpm install
```

## Environment

API configuration is stored locally under:

```text
apps/api/.env
```

Never commit real secrets.

Example database format:

```env
DATABASE_URL=postgresql://USER:PASSWORD@HOST:5432/DATABASE
```

## PostgreSQL

Example local health check:

```bash
docker exec rhcp_postgres pg_isready -U rhcp -d rhcp_dev
```

## Redis

```bash
docker exec rhcp_redis redis-cli ping
```

Expected:

```text
PONG
```

## Prisma

```bash
pnpm --filter @rhcp/api prisma:generate
pnpm --filter @rhcp/api prisma:migrate
pnpm --filter @rhcp/api prisma:studio
```

## API

```bash
pnpm --filter @rhcp/api dev
```

## Mobile

Terminal 1:

```bash
pnpm --filter @rhcp/mobile start
```

Terminal 2:

```bash
cd apps/mobile
pnpm android
```

For Android emulators, the host machine is normally accessed through the emulator's host gateway rather than `localhost`.

## Validation

```bash
pnpm build
pnpm test
```

Run package-specific checks for changed components.

## Debugging

Identify the failing layer before changing configuration:

- PostgreSQL/container.
- Redis.
- Environment variables.
- Prisma.
- NestJS.
- Metro.
- Android build/emulator.
- API connectivity.
- Client state/offline synchronization.

Avoid destructive cleanup unless necessary.

## Generated Files

Do not commit build output, local Gradle state, caches, IDE metadata, or machine-specific configuration unless explicitly required.
