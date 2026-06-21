# System overview

This file describes the intended system boundaries for a monorepo that supports frontend, backend, infrastructure, testing, and agent loops.

## Target layout

```txt
apps/
  web/                 # Browser or mobile web frontend
  api/                 # Backend API
  worker/              # Async jobs, queues, schedulers
packages/
  shared-types/        # Cross-service contracts and generated types
  ui/                  # Shared UI components
  test-utils/          # Test factories, fixtures, and helpers
infra/
  terraform/           # Infrastructure-as-code
```

## Architecture rules

1. User-facing behavior should be described in `docs/product/` and protected by tests.
2. Service boundaries should be documented before becoming complex.
3. Shared contracts should live in `packages/` rather than being copied across apps.
4. Infrastructure changes should include Terraform validation and a cost/scaling note.
5. Security-sensitive flows should include explicit auth, authorization, and data-boundary documentation.

## Architecture decision records

Use `docs/architecture/adr/` for decisions that are expensive to reverse.

Examples:

- monorepo vs polyrepo
- frontend/backend hosting model
- database choice
- auth provider
- queueing strategy
- agent execution model
- observability stack
