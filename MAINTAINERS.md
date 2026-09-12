# Maintainers

## Responsibilities

Maintainers are responsible for:

- Reviewing contributions.
- Protecting the stability of `main`.
- Coordinating releases.
- Reviewing security-sensitive changes.
- Maintaining architecture/API documentation.
- Keeping documentation aligned with implementation.

## Decision Principles

Technical decisions should prioritize:

1. Patient and operational safety.
2. Data integrity.
3. Security and privacy.
4. Offline reliability.
5. Maintainability.
6. Appropriate architectural simplicity.

Significant architectural changes should be documented before implementation.

## Branch Protection

The intended flow is:

```text
feature/* → develop → main
```

Changes to `main` should be reviewed and validated.

## Sensitive Changes

Additional review is recommended for authentication, authorization, patient data, consent, database migrations, synchronization, cryptography, notifications, healthcare integrations, and deployment infrastructure.
