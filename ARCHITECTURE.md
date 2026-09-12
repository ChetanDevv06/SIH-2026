# CareGrid Architecture

## Overview

CareGrid is a rural healthcare connectivity and coordination platform designed for healthcare workflows across facility tiers under intermittent connectivity.

The architecture uses a **modular monolith** for the central backend, local edge capabilities, and dedicated mobile/desktop clients.

## High-Level Architecture

```text
React Native Mobile ──┐
                      ├── HTTP / WebSocket ──> NestJS API
Electron Desktop ─────┘                         │
                                               ├── PostgreSQL / Prisma
                                               └── Redis / BullMQ
                                                        │
                                      Raspberry Pi facility/ambulance edge
                                                        │
                                                Intermittent WAN
```

## Technology

### API

- NestJS
- TypeScript
- PostgreSQL
- Prisma
- Redis
- BullMQ
- JWT authentication
- RBAC
- WebSockets/Socket.IO where required

### Mobile

- React Native
- TypeScript
- React Navigation
- React Native Paper
- Local/offline persistence
- Network-state awareness
- Localization

### Desktop

- Electron
- React
- TypeScript
- Local persistence where required

### Edge

- Raspberry Pi/Linux
- Local cache/data
- Synchronization with the central platform
- Connectivity-aware operation

## Data Freshness

Availability is human-verified. Beds, doctors, equipment, and medicine records should retain timestamps and freshness state.

Stale data must be visibly distinguished from current data.

## Appointment Concurrency

Appointment booking must be protected by database-level transactional/concurrency controls:

```text
Request A ─┐
           ├── transaction ──> one successful booking
Request B ─┘                    other request -> conflict
```

Application-only availability checks are insufficient for race-condition prevention.

## Referrals

Referral workflows coordinate:

1. Referring healthcare worker/facility.
2. Patient.
3. Receiving facility.
4. Receiving doctor.
5. Appointment/clinical coordination.
6. Doctor response.
7. Timeout and escalation.

## Offline Operation

Edge/local clients may provide recently synchronized data during WAN outages. Interfaces must expose synchronization time and freshness rather than silently treating cached information as real-time.

## External Integrations

Planned/experimental areas include:

- ABDM/ABHA.
- SMS.
- USSD.
- Raspberry Pi.
- LoRa.
- Ambulance hardware.

External integrations should be considered unvalidated until the relevant provider/device interfaces are tested.

## Design Principles

- Offline first where required.
- Human-verified availability.
- Explicit freshness.
- Transactional data integrity.
- Consent-aware workflows.
- Server-side authorization.
- Low-bandwidth compatibility.
- Clear failure states.
- Simple modular architecture.
