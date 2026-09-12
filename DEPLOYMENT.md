# Deployment Guide

## Status

This is the production deployment checklist. Exact hosting infrastructure should be finalized and reviewed before production use.

## Components

A deployment may include:

- NestJS API.
- PostgreSQL.
- Redis.
- Background workers/queues.
- Notification integrations.
- Mobile application.
- Desktop application.
- Raspberry Pi facility/ambulance edge nodes.

## Production Requirements

Before deployment:

- Use production-grade PostgreSQL.
- Secure Redis.
- Store secrets outside Git.
- Use TLS.
- Use strong JWT secrets.
- Restrict database access.
- Enforce server-side authorization.
- Configure backups and restore procedures.
- Configure monitoring/logging.
- Verify notification delivery.
- Test offline synchronization and recovery.
- Validate edge-device authentication.

## Database Migrations

Review production migrations before deployment:

```bash
pnpm --filter @rhcp/api prisma:migrate:prod
```

Do not run development migration workflows against production.

## Secrets

Never store production credentials in source code, README files, issues, CI logs, or committed `.env` files.

## Edge Devices

Each Raspberry Pi should have controlled identity/credentials, protected local data, update/recovery procedures, and observable synchronization status.

## Pre-Release Checklist

- [ ] Build succeeds.
- [ ] Tests pass.
- [ ] Authentication verified.
- [ ] Authorization verified.
- [ ] Migrations reviewed.
- [ ] Logs checked for sensitive data.
- [ ] Online/offline behavior tested.
- [ ] Sync recovery tested.
- [ ] Referral workflow tested.
- [ ] Appointment concurrency tested.
- [ ] Consent workflow tested.
- [ ] Backups and restore tested.
- [ ] Monitoring configured.

CareGrid should not be used for real clinical deployment until security, privacy, reliability, regulatory, clinical, and operational requirements have been independently reviewed.
