# User journeys

This file is the product-level inventory of critical journeys that should be protected by tests and release checks.

## Journey template

```md
## Journey: <name>

Primary user:
Business value:
Entry point:
Exit condition:
Systems touched:

### Happy path
1.
2.
3.

### Edge cases
-
-

### Required evidence
- Unit tests:
- Integration tests:
- E2E tests:
- Observability:
- Rollback consideration:
```

## Initial critical journeys

### Journey: New user can access the product

Primary user: New customer or internal tester  
Business value: Confirms onboarding and first-use path works end to end.  
Entry point: Landing page, invite link, or sign-up page.  
Exit condition: User reaches the authenticated application shell without errors.

Required evidence:

- E2E test for sign-up or login
- Backend/session verification
- UI state verification after reload
- Failure screenshot or trace on test failure

### Journey: Existing user can complete the core product action

Primary user: Returning user  
Business value: Protects the product's main value proposition.  
Entry point: Authenticated app.  
Exit condition: Core action is persisted and visible after reload.

Required evidence:

- E2E test using visible UI controls
- Integration test for backend persistence
- Observability for failed action attempts

### Journey: User can recover from expected errors

Primary user: Any user  
Business value: Prevents silent failure and support burden.  
Entry point: Any form, workflow, or async operation.  
Exit condition: User sees a useful error and can retry or exit safely.

Required evidence:

- UI test for error state
- Backend test for validation or failure mode
- Log or monitoring event for operational visibility
