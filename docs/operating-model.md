# Agent-loop operating model

This document defines how agent teams should operate around a software delivery lifecycle.

## Model

```txt
Requirement intake
  -> clarify product outcome
  -> convert into repo-native acceptance criteria
  -> implementation plan
  -> code/docs/tests change
  -> specialist agent reviews
  -> deterministic CI gates
  -> staging or preview validation
  -> release decision
  -> post-release smoke and monitoring
```

## Standard agent team

| Role | Responsibility | Output |
| --- | --- | --- |
| Planner | Clarifies goal, scope, impacted journeys, and acceptance criteria | Plan and risk list |
| Builder | Implements the change | Code, tests, docs |
| Backend reviewer | Checks API, data, auth, migrations, and reliability | Review findings |
| Frontend reviewer | Checks UX, state, accessibility, and browser behavior | Review findings |
| Security reviewer | Checks auth, secrets, injection, data leakage, and abuse cases | Security findings |
| Infra/cost reviewer | Checks Terraform, cloud resources, scaling, and cost impact | Infra/cost findings |
| E2E reviewer | Checks whether human-like user flows prove the change | Test coverage findings |
| Docs reviewer | Checks docs, release notes, and acceptance criteria drift | Documentation findings |

## Rules of engagement

1. Agent opinions are advisory unless backed by tests, logs, diffs, or reproducible evidence.
2. Each PR should contain a compact evidence section explaining what was changed and how it was verified.
3. Required CI checks should be enforced through branch protection before production-bound branches can merge.
4. Agent loops may propose releases or rollbacks, but should not silently bypass release controls.
5. External context from MCP tools should be summarized and mirrored into repo-native docs before it becomes release-critical.

## Loop types

| Loop | Trigger | Purpose |
| --- | --- | --- |
| PR review loop | Every PR | Catch missing tests, docs drift, security gaps, regression risk |
| E2E journey loop | PR and nightly | Verify critical user journeys in a real browser |
| Security loop | PR and weekly | Review auth, secrets, dependencies, and data exposure |
| Infra/cost loop | Infra changes and weekly | Review cloud spend, Terraform drift, scaling, and cleanup |
| Docs freshness loop | PR and weekly | Keep repo docs aligned with product and implementation reality |
| Release readiness loop | Before deploy | Confirm go/no-go evidence, rollback path, and monitoring |
| Incident loop | Alert-driven | Reproduce, triage, propose rollback or fix |
