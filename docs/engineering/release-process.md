# Release process

This release process is designed for agent-assisted teams where deterministic checks remain the source of release confidence.

See `docs/engineering/environment-strategy.md` for the canonical dev/stg/prd environment definitions and deployment conditions.

## Standard path

```txt
feature branch
  -> CI checks
  -> optional development deployment
  -> pull request
  -> CI checks
  -> optional PR preview environment
  -> E2E smoke tests
  -> merge to main
  -> staging deployment
  -> full or targeted regression
  -> release-readiness loop
  -> production deployment
  -> production smoke test
  -> monitoring and rollback readiness
```

## Environment promotion model

```txt
non-main branch / manual dispatch
  -> dev

pull request
  -> preview environment, when app infrastructure exists

main branch
  -> stg

GitHub Release / protected release tag / approved manual promotion from main
  -> prd
```

## Deployment conditions

| Target | Required source | Minimum gate |
| --- | --- | --- |
| `dev` | Non-main branch or manual workflow dispatch | Basic CI and no known secret leakage |
| PR preview | Pull request branch | CI and preview-safe synthetic data |
| `stg` | `main` | Required CI, security checks, Terraform plan review when relevant |
| `prd` | Release event or approved manual promotion from `main` | Healthy staging, release-readiness approval, rollback path, production smoke plan |

## Pull request evidence

Each PR should include:

- summary of changed behavior
- affected user journeys
- intended target environment, if deployment behavior changes
- tests run
- screenshots or traces for UI changes where useful
- security/data/infra/cost impact
- rollback notes
- documentation updates or reason not needed

## Release readiness checklist

- Required CI checks are green.
- The affected critical journey has test evidence.
- No unresolved security or data leakage risks remain.
- Infra changes have a reviewed plan and rollback path.
- Staging has been deployed and validated before production promotion.
- Observability exists for the changed behavior.
- A rollback path is documented.
- Production deployment conditions are unchanged or explicitly reviewed.

## Post-release loop

After release:

1. Run production smoke tests.
2. Check error rate, latency, and key business events.
3. Compare expected vs actual behavior.
4. Roll back quickly if a critical journey is broken.
5. Capture learnings in docs or tests.
