# Agent operating instructions

These instructions are the canonical rules for AI coding agents working in this repository.

## Prime directive

Do not optimize for producing code. Optimize for shipping working, tested, secure, maintainable product changes.

## Required behavior

1. Read the relevant files before changing them.
2. Prefer small, reviewable changes with clear intent.
3. Update tests and documentation in the same change when behavior changes.
4. Never claim verification unless the relevant command or check has actually run.
5. Surface risks, assumptions, and missing context in the pull request.
6. Do not bypass CI, branch protection, tests, security checks, or human release review.
7. Do not store secrets, production credentials, API keys, tokens, or private customer data in the repo.

## Source-of-truth hierarchy

1. Code, tests, infrastructure, and release docs in this repository.
2. Approved architecture decision records in `docs/architecture/adr/`.
3. Product acceptance criteria in `docs/product/acceptance-criteria.md`.
4. External docs such as Notion or Confluence, accessed through MCP, are input sources unless mirrored into this repository.

## Change checklist

Before opening or updating a PR, the agent should check:

- What user journey does this affect?
- What tests prove the journey still works?
- What failure modes were considered?
- Is there any data, security, cost, or infra impact?
- Are docs and acceptance criteria still accurate?
- What is the rollback path?

## Agent role separation

Builder agents should not be the only reviewers of their own work. Use the role prompts in `agents/roles/` for specialist review loops.
