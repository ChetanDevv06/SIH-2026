# Testing Strategy

## Goal

Testing must cover normal operation as well as weak-network, offline, synchronization, and concurrency conditions.

## Unit Tests

Test:

- Validation.
- Domain logic.
- Authorization.
- Freshness calculations.
- Referral state transitions.
- Inventory logic.
- Notification logic.

## Integration Tests

Test:

- API/database behavior.
- Prisma transactions.
- Authentication.
- RBAC.
- Queues.
- Synchronization.
- Integration adapters.

## End-to-End Tests

Critical workflows should include:

1. Authentication.
2. Patient/referral creation.
3. Referral approval.
4. Appointment booking.
5. Concurrent booking conflict.
6. Appointment timeout.
7. Availability lookup.
8. Inventory lookup.
9. Offline synchronization.
10. Recovery after connectivity returns.

## Concurrency

For the same appointment slot:

- Exactly one conflicting request should succeed.
- The other should receive the expected conflict response.
- No duplicate booking should persist.

## Offline Testing

Simulate:

- Network loss.
- Network recovery.
- Stale local data.
- Local updates while offline.
- Synchronization.
- Sync conflicts.
- Partial sync failures.

## Freshness

Verify that stale availability is:

- Marked stale.
- Associated with its last-updated time.
- Not presented as real-time truth.
- Escalated where configured.

## Security

Test invalid credentials, expired tokens, unauthorized roles, object-level authorization, input validation, sensitive-data exposure, and untrusted spreadsheet/file input.

## Commands

```bash
pnpm test
pnpm build
pnpm --filter @rhcp/api test
pnpm --filter @rhcp/api test:e2e
pnpm --filter @rhcp/mobile test
```
