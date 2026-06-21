# Terraform infrastructure

This directory is reserved for infrastructure-as-code.

Recommended layout:

```txt
infra/terraform/
  modules/
  envs/
    dev/
    staging/
    prod/
```

## Required practices

- Keep environment configuration explicit.
- Do not hardcode secrets.
- Run formatting and validation on every Terraform change.
- Review plan output before apply.
- Keep outputs documented when consumed by CI/CD.
- Include cost, scaling, and rollback notes for new resources.

## Agent review expectations

An infra/cost reviewer should check:

- always-on compute
- autoscaling bounds
- log and artifact retention
- secret/version cleanup
- service account and IAM scope
- rollback path
