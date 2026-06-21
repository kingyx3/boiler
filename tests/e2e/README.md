# E2E tests

This directory is reserved for browser-level tests that verify human-like product journeys.

Recommended layout:

```txt
tests/e2e/
  journeys/
    signup.spec.ts
    login.spec.ts
    core-action.spec.ts
    permissions.spec.ts
  fixtures/
  helpers/
```

## E2E principles

1. Test what a user can see and do.
2. Prefer stable, accessible locators.
3. Avoid depending on implementation details.
4. Verify persistence after reload where relevant.
5. Capture traces, screenshots, and videos on failure.
6. Seed test data explicitly and cleanly.
7. Keep critical smoke tests fast enough to run on every PR.

## Critical journey candidate list

- Sign up or log in
- Complete onboarding
- Execute the main product action
- Recover from validation or expected error
- Verify permission boundaries
- Upgrade or change plan, if billing exists
- Confirm dashboard or reporting views load correctly
