# Data Handling and Privacy Principles

This document describes engineering principles. It is **not a legal privacy policy** and does not replace applicable law, regulation, organizational policy, or professional guidance.

## Data Minimization

Collect and retain only information necessary for the intended workflow.

Do not put patient information into logs, analytics, debug output, screenshots, or issue reports.

## Patient Identity

CareGrid supports workflows for patients without an ABHA identifier. ABHA should not be treated as a universal prerequisite.

Use the minimum appropriate identity information and follow applicable consent and organizational policies.

## Consent

Consent-sensitive workflows should:

- Record the relevant consent state.
- Enforce authorization.
- Avoid assuming consent merely because a record exists.
- Make consent-related failures explicit.

## Offline Data

Local/offline storage should minimize sensitive information, protect stored data, use controlled retention, synchronize securely, and expose synchronization/freshness state.

## Logs

Do not log:

- Passwords.
- Access/refresh tokens.
- Database credentials.
- Unnecessary patient information.
- Sensitive healthcare information.

## Test Data

Use synthetic data for development and automated tests. Never use real patient records as test fixtures.

## Imports and Exports

Treat spreadsheet imports and exports as sensitive operations. Validate untrusted input and enforce authorization.

## Retention

Production retention periods must be defined by the responsible organization based on applicable requirements.

## Incidents

Suspected exposure of sensitive information should be handled through the organization's incident-response process. See `SECURITY.md`.
