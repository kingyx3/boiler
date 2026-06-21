# Environment strategy

This repository uses three long-lived deployment environments plus optional pull-request previews.

## Environment definitions

| Environment | Alias | Purpose | Data policy | Deployment source | Deployment condition |
| --- | --- | --- | --- | --- | --- |
| Development | `dev` | Fast integration for active engineering work | Synthetic or disposable data only | Non-main branches and manual workflow runs | Deploy after basic CI passes, or manually for a named branch |
| Staging | `stg` | Production-like validation before release | Production-like synthetic or sanitized data | `main` branch | Deploy automatically after merge to `main` and required checks pass |
| Production | `prd` / `prod` | Customer-facing live environment | Real production data | GitHub Release, protected tag, or manual promotion from `main` | Deploy only after staging validation, release-readiness review, and required approvals |
| Pull request preview | `pr-*` | Ephemeral review app for a specific PR | Synthetic seeded data only | Pull request branch | Create/update for PRs when app code exists; destroy on close/merge |

## Branch and event policy

```txt
feature branch / non-main push
  -> CI
  -> optional dev deployment
  -> optional PR preview

pull request to main
  -> CI
  -> structure/security/terraform checks as applicable
  -> optional PR preview
  -> E2E smoke against preview when available

merge to main
  -> staging deployment
  -> staging smoke and targeted regression
  -> release-readiness loop

release tag or GitHub Release from main
  -> production deployment
  -> production smoke test
  -> post-release monitoring
```

## Required gates by environment

### Development (`dev`)

Required before deploy:

- repository structure check
- lint/typecheck/unit test placeholders once app code exists
- Terraform validation if infra changed
- no known secret leakage

Deployment behavior:

- can deploy frequently
- can be overwritten by later branch deployments
- may use lower-cost resources
- should never contain production customer data

### Staging (`stg`)

Required before deploy:

- merge to `main`
- required CI checks green
- security workflow green or explicitly waived
- Terraform plan reviewed if infra changed
- affected critical journeys identified

Deployment behavior:

- should be production-like enough for release confidence
- should run smoke tests after deployment
- should run targeted regression for affected journeys
- should block production promotion if critical journeys fail

### Production (`prd` / `prod`)

Required before deploy:

- production deployment source is traceable to `main`
- staging deployment is healthy
- release-readiness loop says `Go` or a human owner records a waiver
- rollback plan exists
- monitoring and smoke tests are ready
- required approvals are satisfied through GitHub Environments or equivalent release controls

Deployment behavior:

- deploy only from protected release events or manual promotion
- run production smoke tests immediately after deploy
- monitor error rate, latency, failed jobs, and key business events
- roll back quickly if a critical journey is broken

## Infrastructure separation

Terraform should keep environment state and configuration separated:

```txt
infra/terraform/envs/dev
infra/terraform/envs/staging
infra/terraform/envs/prod
```

Each environment should have explicit variables, outputs, IAM boundaries, and cost controls. Production permissions should be the narrowest and most heavily reviewed.

## Agent responsibilities

Agents may:

- summarize environment impact
- recommend the right target environment
- prepare PRs that update deployment configuration
- inspect smoke-test evidence
- recommend go/no-go

Agents must not:

- bypass required checks
- promote unreviewed changes to production
- treat dev or staging data as safe if it contains real customer data
- silently change production deployment conditions
