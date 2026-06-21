# Agent prompts and loops

This directory contains reusable instructions for agent-assisted software delivery.

## Structure

```txt
agents/
  roles/       # Specialist role prompts
  loops/       # Repeatable operating loops
```

## Usage

Use `AGENTS.md` as the canonical repository-wide instruction file. Use the files in this directory to run specialist reviews or repeatable loops.

Recommended sequence for meaningful product changes:

```txt
planner
  -> builder
  -> backend/frontend/security/infra/e2e/docs reviewers
  -> CI gates
  -> release readiness loop
```

## Important rule

A builder agent should not be the only reviewer of its own work. Specialist review loops should be run as separate passes with fresh context.
