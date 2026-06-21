# Infrastructure implementation guide

This guide defines what future infrastructure code should provide.

## Required environment layout

Infrastructure should follow:

```txt
infra/terraform/modules
infra/terraform/envs/dev
infra/terraform/envs/staging
infra/terraform/envs/prod
```

## Required capabilities

Each environment should document:

- purpose
- resource list
- expected cost drivers
- configuration inputs
- outputs consumed by CI or apps
- access boundaries
- deploy command
- rollback approach

## Module expectations

Reusable modules should document:

- inputs
- outputs
- default behavior
- cost notes
- security assumptions
- examples

## Agent review expectations

Infrastructure changes should include an infra and cost review when they add resources, change permissions, alter network behavior, affect deployment, or change observability.
