# Apps

This directory is for deployable applications.

Recommended layout:

```txt
apps/
  web/       # frontend application
  api/       # backend API service
  worker/    # background workers and schedulers
```

## Rules

- App-specific code stays under the relevant app directory.
- Shared code should be extracted to `packages/`.
- User-facing behavior changes should update `docs/product/` and relevant E2E tests.
- Deployment-impacting changes should update `docs/engineering/release-process.md` or `infra/terraform/` docs where relevant.
