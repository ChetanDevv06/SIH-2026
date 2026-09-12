# CareGrid API

## Overview

The CareGrid API is implemented using NestJS and TypeScript.

Core domains include authentication, users, patients, facilities, doctors, availability, referrals, appointments, medicines, inventory, prescriptions, ambulance workflows, synchronization, notifications, and health checks.

## Base Path

The API uses a versioned global API prefix. The host and deployment URL are environment-specific.

## Authentication

Authentication includes registration, login, refresh, and logout operations.

Access and refresh tokens must be treated as sensitive credentials.

## Roles

The current application roles are:

- `ASHA_WORKER`
- `PHC_STAFF`
- `DOCTOR`
- `FACILITY_STAFF`
- `HOSPITAL_ADMIN`
- `AMBULANCE_STAFF`
- `SUPER_ADMIN`

Authorization must be enforced by the API, not only by the client.

## Domains

| Domain | Responsibility |
|---|---|
| Auth | Authentication/token lifecycle |
| Users | Users and roles |
| Patients | Patient/local records |
| Referrals | Cross-facility referrals |
| Appointments | Scheduling/conflict handling |
| Doctors | Doctor workflows |
| Facilities | Facility information |
| Availability | Operational availability |
| Beds | Bed availability |
| Equipment | Equipment availability |
| Medicines | Medicine catalog/alternatives |
| Inventory | Stock/freshness |
| Prescriptions | Prescription workflows |
| Ambulance | Emergency transport |
| Sync | Offline synchronization |
| Notifications | Notifications |
| Health | Service health |

## Contract Changes

When changing an API:

- Document request changes.
- Document response changes.
- Document errors.
- Update clients.
- Update tests.
- Consider backward compatibility.

Appointment conflicts are expected behavior and should be represented consistently.

## Error Handling

Clients should handle validation, authentication, authorization, not-found, conflict, rate-limit, server, and network errors.

## Swagger/OpenAPI

When Swagger is enabled in the development environment, use the generated Swagger UI as the interactive API reference. The implementation and current OpenAPI output are authoritative.
