# Packages

This directory is for shared libraries and contracts used across apps.

Recommended layout:

```txt
packages/
  shared-types/    # generated or hand-maintained cross-service types
  ui/              # shared frontend components
  test-utils/      # factories, fixtures, and test helpers
```

## Rules

- Do not duplicate shared contracts across apps.
- Keep package boundaries explicit.
- Add tests for shared logic because package changes can affect multiple apps.
- Document breaking changes in the PR and release notes.
