# Local development

This document defines the expected local development experience for the future executable template.

## Goal

A developer or coding agent should be able to start from a clean clone and run the system locally without guessing project-specific setup steps.

## Required future commands

The executable template should expose commands equivalent to:

```txt
install dependencies
run all apps locally
run web only
run API only
run worker only
run lint
run type checks
run unit tests
run integration tests
run E2E tests
run build
```

The exact package manager and framework can change, but the behavior should remain documented and scriptable.

## Required documentation

When implementation code is added, document:

- prerequisites
- package manager and version expectations
- local environment file setup
- how to start each app
- how to run tests
- how to reset local data
- how to troubleshoot common setup failures

## Agent expectations

Agents should use local development commands as the first verification layer before claiming a change works.

If an agent cannot run a command, it must state that clearly in the PR evidence and explain what still needs human or CI verification.
