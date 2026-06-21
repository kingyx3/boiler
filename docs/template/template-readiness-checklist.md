# Template readiness checklist

Use this checklist before using the repository as the starting point for a real production application.

## Local development

- [ ] Clean clone can install dependencies.
- [ ] Web app can run locally.
- [ ] API can run locally.
- [ ] Worker can run locally or execute a sample job.
- [ ] Local setup is documented in `docs/engineering/local-development.md`.

## Test coverage

- [ ] Unit tests exist for shared logic.
- [ ] Integration tests exist for API behavior.
- [ ] Contract tests exist for app/package boundaries.
- [ ] E2E tests cover at least one critical user journey.
- [ ] Smoke tests exist for deployed environments.

## CI/CD

- [ ] CI runs real lint, type, test, and build commands.
- [ ] E2E workflow runs real browser tests.
- [ ] Terraform workflow runs real validation and planning when infra exists.
- [ ] Environment deployment workflows implement the documented conditions.
- [ ] Required checks are documented for branch protection.

## Environments

- [ ] `dev` uses disposable or synthetic data.
- [ ] `stg` is production-like enough for release validation.
- [ ] `prd` requires release readiness evidence.
- [ ] Environment-specific config is documented.
- [ ] Rollback path exists for each deploy target.

## Security and operations

- [ ] Sensitive config is not stored in the repo.
- [ ] Dependency checks are configured.
- [ ] Application security checks are configured.
- [ ] Health checks are available.
- [ ] Logs and metrics support incident triage.
- [ ] Alerting guidance exists.

## Agent loops

- [ ] Planner loop maps request to affected journeys and acceptance criteria.
- [ ] Builder loop updates code, tests, and docs together.
- [ ] Reviewer loops cover backend, frontend, security, infra/cost, E2E, and docs.
- [ ] Release-readiness loop produces go/no-go evidence.
- [ ] Incident loop produces triage and prevention follow-up.

## Final decision

Do not call the template production-ready until every section above is either complete or explicitly marked not applicable with a human-reviewed reason.
