# Release Process

## Versioning

When formal releases begin, use consistent semantic versioning where appropriate:

```text
MAJOR.MINOR.PATCH
```

## Preparation

Before release:

- [ ] Review changelog.
- [ ] Build successfully.
- [ ] Run tests.
- [ ] Review migrations.
- [ ] Review security-sensitive changes.
- [ ] Verify API compatibility.
- [ ] Verify mobile build.
- [ ] Verify desktop build where applicable.
- [ ] Verify deployment configuration.
- [ ] Update documentation.

## Git Tags

Released versions should use immutable Git tags:

```bash
git tag v1.0.0
git push origin v1.0.0
```

Create tags only after approval of the release commit.

## Hotfixes

Critical fixes should be isolated, tested, reviewed, documented, and merged back into the appropriate development branch.

## Pre-1.0

Before a stable 1.0 release, APIs and implementation details may change without the compatibility guarantees of a mature production release.
