# ADR 0001: Repo-first agent-loop operating model

Status: Proposed  
Date: 2026-06-21

## Context

The project aims to support software delivery using agent teams and repeatable loops. Agents may read product requirements from external tools such as Notion, Confluence, Jira, or GitHub issues through MCP or APIs.

However, release-critical information needs to be versioned, reviewable, auditable, and enforceable by CI/CD.

## Decision

Use the Git repository as the canonical source of truth for release-critical engineering context:

- agent instructions
- product acceptance criteria
- user journeys
- architecture decisions
- testing strategy
- security standards
- cost and infrastructure standards
- release and rollback process

External documentation systems may be used for collaboration and intake, but approved delivery criteria should be mirrored into this repository before implementation or release gating.

## Consequences

### Positive

- Code, tests, docs, and infra can be changed atomically.
- Pull requests can review documentation and implementation together.
- CI/CD can enforce structure and release readiness.
- Agents have stable, repo-local context.
- Rollbacks and audits have a clear commit history.

### Trade-offs

- Business users may prefer Notion or Confluence for drafting.
- Some documentation may need to be synced or summarized back to external tools.
- The repository requires discipline to avoid stale docs.

## Operating rule

If stale or incorrect documentation could cause a bad production release, that documentation belongs in Git.
