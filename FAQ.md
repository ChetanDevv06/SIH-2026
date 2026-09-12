# Frequently Asked Questions

## What is CareGrid?

CareGrid is a rural healthcare connectivity and coordination platform designed to improve coordination between healthcare facilities under intermittent network conditions.

## Is ABHA mandatory?

No. CareGrid is designed to support non-ABHA patients. ABDM/ABHA functionality is intended to be consent-aware.

## Does CareGrid require continuous internet?

No. Offline-first behavior is a core requirement for relevant workflows, with local/edge capabilities for recently synchronized information.

## Is availability automatically verified?

No. Facility availability is intended to be human-verified and timestamped. Stale information should be visibly distinguished.

## What if two users book the same appointment?

Database-safe concurrency control is intended to ensure one booking succeeds and the conflicting request receives a conflict response.

## What if a doctor does not respond?

The referral workflow includes a configurable response timeout. After timeout, the referring worker/facility should be notified so they can rebook or escalate.

## What technologies are used?

- React Native + TypeScript
- Electron + React + TypeScript
- NestJS + TypeScript
- PostgreSQL + Prisma
- Redis + BullMQ
- Raspberry Pi/Linux edge capabilities

## Does it support constrained networks?

The architecture targets intermittent/low-bandwidth environments and includes planned keypad/USSD/SMS workflows. Actual carrier/provider capabilities require deployment-specific validation.

## Is it production-ready?

Readiness depends on implementation status, security/privacy review, field validation, infrastructure, and applicable healthcare requirements. A development/hackathon build should not be assumed suitable for real clinical deployment.
