# Security Policy

CareGrid involves healthcare coordination workflows, so security is a high-priority engineering concern.

## Reporting a Vulnerability

**Do not report security vulnerabilities through public GitHub issues, pull requests, or discussions.**

Use the private security contact configured by the repository maintainers.

Include:

- Vulnerability description.
- Affected component/endpoint.
- Reproduction steps.
- Expected and actual behavior.
- Potential impact.
- Suggested mitigation, if known.

Never include real patient data, passwords, tokens, API keys, database credentials, or private certificates.

## Security-Sensitive Areas

Particular care is required around:

- Authentication and JWT handling.
- Role-based access control.
- Patient records.
- Consent and ABDM/ABHA workflows.
- Referrals and appointments.
- Offline synchronization.
- Device and edge communication.
- Notifications.
- Database access.
- Spreadsheet imports/exports.

## Development Rules

Never commit secrets. Use environment variables or an appropriate secret manager.

Production credentials must never be reused as development credentials.

Logs must not expose tokens, passwords, database credentials, or unnecessary patient information.

## Handling

Maintainers will assess reported issues, determine impact, develop and test fixes, and coordinate disclosure where appropriate.

CareGrid software must not be assumed to satisfy clinical, regulatory, privacy, or organizational requirements without independent review.
