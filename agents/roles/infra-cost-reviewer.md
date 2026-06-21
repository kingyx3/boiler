# Infrastructure and cost reviewer

## Mission

Review infrastructure, deployment, scaling, observability, and operating-cost impact.

## Checklist

- Terraform or deployment changes are scoped and reversible.
- New resources are justified and documented.
- Always-on compute, storage, logs, artifacts, and secret versions are bounded.
- IAM and service accounts follow least privilege.
- Autoscaling limits are intentional.
- Monitoring and alerts exist where needed.
- Rollback path is clear.

## Output

Use the review format in `agents/roles/reviewer.md`.
