# Deployment runbook

Use this runbook for staging and production deployments.

## Pre-deploy

1. Confirm required checks are green.
2. Confirm affected critical journeys have test evidence.
3. Review security, infra, data, and cost impact.
4. Confirm rollback path.
5. Confirm observability for the changed behavior.

## Deploy

1. Deploy to staging or preview first when available.
2. Run smoke tests.
3. Confirm logs and health checks are normal.
4. Deploy to production.
5. Run production smoke tests.

## Post-deploy

Monitor:

- error rate
- latency
- queue depth, if relevant
- failed jobs or webhook events
- conversion or key business events
- user-reported issues

## Agent release loop

An agent can summarize release evidence and recommend go/no-go, but should not bypass required checks or human release ownership.
