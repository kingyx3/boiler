# App template contract

This file defines what a future executable template should provide.

## Required capabilities

- Runnable web app.
- Runnable API service.
- Worker or background job pattern.
- Shared types, shared UI, and shared test utilities.
- Local development instructions for a clean clone.
- Environment setup for `dev`, `stg`, and `prd`.
- Real CI commands for linting, type checks, tests, and build.
- Browser E2E coverage for at least one critical user journey.
- Integration coverage for the API.
- Infrastructure examples for each environment.
- Deployment flow with documented promotion rules.
- Health checks, logs, metrics, and alerting guidance.
- Rollback and incident procedures.
- Agent loop instructions for planning, review, release readiness, and incident triage.

## Ready definition

The template is ready when a clean clone can be installed, run locally, tested, deployed through the documented environments, monitored, and safely changed through an agent-assisted pull request.
