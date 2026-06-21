# Deployment runbook

Use this runbook for development, staging, and production deployments.

The canonical environment policy is defined in `docs/engineering/environment-strategy.md`.

## Environment deployment rules

| Environment | When to deploy | Trigger | Required outcome |
| --- | --- | --- | --- |
| `dev` | During active development or branch validation | Non-main push or manual dispatch | Basic integration confidence |
| PR preview | During PR review | Pull request workflow | Reviewer can exercise changed UI/API safely |
| `stg` | After merge to `main` | Main branch workflow | Production-like release validation |
| `prd` / `prod` | After staging is healthy and release is approved | Release event, protected tag, or approved manual promotion | Customer-facing release |

## Pre-deploy

1. Confirm the target environment and deployment source are valid.
2. Confirm required checks are green for that environment.
3. Confirm affected critical journeys have test evidence.
4. Review security, infra, data, and cost impact.
5. Confirm rollback path.
6. Confirm observability for the changed behavior.

## Deploy to development

1. Deploy from a non-main branch or manual workflow dispatch.
2. Use synthetic or disposable data only.
3. Confirm service starts and basic health checks pass.
4. Treat dev deployment as temporary and non-release-authoritative.

## Deploy to staging

1. Deploy from `main` only.
2. Run smoke tests after deployment.
3. Run targeted regression for affected journeys.
4. Confirm logs and health checks are normal.
5. Do not promote to production while a critical journey is failing.

## Deploy to production

1. Confirm staging is healthy.
2. Confirm release-readiness review recommends `Go` or a human owner has explicitly approved a waiver.
3. Deploy from a release event, protected tag, or approved manual promotion from `main`.
4. Run production smoke tests immediately.
5. Monitor production metrics and user-reported issues.

## Post-deploy

Monitor:

- error rate
- latency
- queue depth, if relevant
- failed jobs or webhook events
- conversion or key business events
- user-reported issues

## Agent release loop

An agent can summarize release evidence and recommend go/no-go. Required checks, environment approvals, and human release ownership remain authoritative.
