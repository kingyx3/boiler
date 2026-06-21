# Cost and infrastructure standards

Infrastructure and operating cost should be reviewed continuously, not only after spend increases.

## Cost principles

1. Prefer simple managed services until scale requires complexity.
2. Keep environments intentionally sized: development, staging, production.
3. Avoid unbounded queues, logs, artifacts, secret versions, and storage growth.
4. Review autoscaling limits before production release.
5. Add monitoring before scaling decisions become guesswork.
6. Infrastructure changes should include a human-readable cost and scaling note.

## Infrastructure review checklist

- Does this change create new cloud resources?
- Does it add always-on compute?
- Are storage, artifact, or log retention settings bounded?
- Are secret versions or container images cleaned up?
- Are autoscaling min/max settings intentional?
- Are alerts or dashboards needed?
- Is rollback possible through Terraform or deployment rollback?

## Terraform expectations

Terraform or OpenTofu-managed infrastructure should include:

- formatted code
- validation
- plan review before apply
- environment separation
- no hardcoded secrets
- outputs documented when consumed by CI/CD
