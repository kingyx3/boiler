# Release process

This release process is designed for agent-assisted teams where deterministic checks remain the source of release confidence.

## Standard path

```txt
feature branch
  -> pull request
  -> CI checks
  -> preview environment when available
  -> E2E smoke tests
  -> merge to main
  -> staging deployment
  -> full or targeted regression
  -> production deployment
  -> production smoke test
  -> monitoring and rollback readiness
```

## Pull request evidence

Each PR should include:

- summary of changed behavior
- affected user journeys
- tests run
- screenshots or traces for UI changes where useful
- security/data/infra/cost impact
- rollback notes
- documentation updates or reason not needed

## Release readiness checklist

- Required CI checks are green.
- The affected critical journey has test evidence.
- No unresolved security or data leakage risks remain.
- Infra changes have an reviewed plan and rollback path.
- Observability exists for the changed behavior.
- A rollback path is documented.

## Post-release loop

After release:

1. Run production smoke tests.
2. Check error rate, latency, and key business events.
3. Compare expected vs actual behavior.
4. Roll back quickly if a critical journey is broken.
5. Capture learnings in docs or tests.
