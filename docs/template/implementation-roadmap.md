# Executable template implementation roadmap

This roadmap describes the recommended order for turning the current Markdown scaffold into a runnable production app template.

## Phase 2A: Toolchain foundation

Add the root workspace and quality tooling:

- package manager workspace
- TypeScript or equivalent shared config
- lint and format config
- local environment example
- repository ignore rules
- shared scripts for install, lint, test, build, and dev

Exit criteria:

- a clean clone can install dependencies
- lint, test, and build commands exist
- CI runs real commands instead of placeholder echoes

## Phase 2B: Minimal runnable apps

Add minimal implementations for:

- `apps/web`
- `apps/api`
- `apps/worker`

Exit criteria:

- web app starts locally
- API starts locally and exposes a health endpoint
- worker starts locally or has a runnable sample job
- web app can call the API in a sample journey

## Phase 2C: Testing gates

Add real tests at multiple levels:

- unit tests for shared logic
- integration tests for API behavior
- contract tests for shared types or API contracts
- E2E tests for the main human journey
- smoke tests for deployed environments

Exit criteria:

- CI fails when the sample journey breaks
- E2E tests capture useful failure evidence
- tests can run consistently in CI

## Phase 2D: Infrastructure and deployment

Add environment-aware deployment implementation:

- dev deployment path
- staging deployment path
- production release path
- Terraform or equivalent examples
- per-environment config boundaries
- rollback procedure validated against the sample app

Exit criteria:

- deployment conditions match `docs/engineering/environment-strategy.md`
- staging validates before production release
- production has a documented smoke test and rollback path

## Phase 2E: Security and observability

Add the minimum production safety layer:

- application security checks
- dependency checks
- sensitive-config handling guidance
- structured logs
- health checks
- basic metrics
- alerting guidance
- incident drill for the sample app

Exit criteria:

- template exposes health signals
- unsafe configuration patterns are documented and checked
- incidents can be triaged with logs and runbooks

## Phase 2F: Agent loop automation

Wire the agent roles and loops into repeatable commands or workflows.

Exit criteria:

- PR review loop can be run consistently
- release-readiness loop has a standard evidence format
- docs freshness loop can identify stale docs
- E2E loop creates actionable failure reports
