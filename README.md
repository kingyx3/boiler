# Agent-loop software delivery operating system

This repository is structured as a monorepo-ready operating system for building software with agent teams and repeatable verification loops.

The core idea is simple:

> Git is the source of truth. Agents can propose and operate. CI/CD decides objective correctness. Humans retain ownership of consequential release decisions.

## Repository map

```txt
apps/                     # Future frontend, backend, workers, and product apps
packages/                 # Shared packages, contracts, UI, and test utilities
infra/terraform/          # Infrastructure-as-code entry point
tests/e2e/                # Browser-level human-journey tests
docs/                     # Product, architecture, engineering, and runbook documentation
agents/                   # Agent roles, loop definitions, and operating prompts
.github/                  # Pull request templates and repository governance workflows
AGENTS.md                 # Canonical repo instructions for AI coding agents
```

## Operating principles

1. Release-critical rules live in Git, not only in chat, Notion, or Confluence.
2. Every meaningful feature should update product docs, acceptance criteria, tests, or explicitly justify why not.
3. Agent loops are reviewers/operators around deterministic checks; they are not a substitute for CI/CD.
4. Human-facing docs may live in Notion or Confluence, but approved engineering truth should be mirrored into this repo.
5. No feature is ready until code, tests, docs, security, infra impact, and rollback path have been considered.

## Recommended workflow

```txt
business requirement
  -> product/acceptance criteria in docs/
  -> implementation plan
  -> code + tests + docs
  -> agent specialist reviews
  -> deterministic CI gates
  -> preview or staging validation
  -> production release with monitoring and rollback path
```

See `docs/operating-model.md` for the full operating model.
