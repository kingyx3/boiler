# Testing strategy

Testing is the deterministic foundation beneath agent review loops.

## Test pyramid

```txt
Unit tests
  -> validate pure logic and edge cases quickly
Integration tests
  -> validate service boundaries, persistence, queues, and APIs
Contract tests
  -> validate shared contracts across frontend/backend/services
E2E tests
  -> validate critical human user journeys in a real browser
Synthetic smoke tests
  -> validate production-critical paths after deployment
```

## Required standards

1. Every meaningful behavior change should include automated test evidence or a reviewed exception.
2. E2E tests should use visible UI behavior, not internal implementation details.
3. Critical journeys should be tested against preview or staging before release.
4. Failed E2E runs should keep screenshots, videos, traces, logs, or equivalent artifacts.
5. Test data should be isolated, repeatable, and safe to run in CI.
6. Agents should not mark a feature as verified unless the relevant test command has actually run.

## Human-like E2E expectations

A useful E2E test should:

- open the app like a user
- log in or create a test session
- click visible controls
- submit forms
- wait for user-visible state changes
- verify persistence after reload
- exercise expected errors where relevant
- capture failure artifacts

## Minimum release checks

Before release, confirm:

- lint/typecheck pass
- unit tests pass
- integration tests pass for touched services
- E2E smoke passes for affected critical journeys
- migrations or infra plans are reviewed when relevant
- monitoring and rollback path are known
