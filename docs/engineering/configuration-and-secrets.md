# Configuration and sensitive settings

This document defines how configuration should work once executable app code is added.

## Goals

- Keep environment configuration explicit.
- Keep local development simple.
- Avoid committing sensitive values.
- Make dev, staging, and production differences obvious.
- Let agents reason safely about configuration without seeing private credentials.

## Required future files

The executable template should include an example configuration file such as:

```txt
.env.example
```

The example file should contain names, descriptions, and safe placeholder values only.

`.env` files are excluded from version control via `.gitignore`. They are created at runtime by the CI/CD workflows.

## Environment configuration rules

| Environment | Config source | Data policy |
| --- | --- | --- |
| `dev` | GitHub Actions `dev` environment variables and secrets | synthetic or disposable data |
| `stg` | GitHub Actions `stg` environment variables and secrets | production-like synthetic or sanitized data |
| `prd` | GitHub Actions `prd` environment variables and secrets | production data controls |
| local | `.env` copied from `.env.example` and populated manually | developer-supplied test data |

## CI/CD environment file creation

Each deployment workflow (and CI for build and test steps) contains a **Create environment files** step that:

1. Reads non-sensitive values from GitHub Actions **Variables** (`vars.*`).
2. Reads sensitive values from GitHub Actions **Secrets** (`secrets.*`).
3. Writes `.env` files for each app (`apps/api/.env`, `apps/web/.env`, `apps/worker/.env`) on the runner.

These files are never committed. They exist only on the runner for the duration of the job.

### Required GitHub Variables (set per environment)

| Variable | Apps | Description |
| --- | --- | --- |
| `NODE_ENV` | api, web, worker | Runtime environment label (e.g. `development`, `staging`, `production`) |
| `API_PORT` | api | Port the API server listens on |
| `WEB_PORT` | web | Port the web server listens on |
| `API_URL` | web | Public base URL of the backend API |
| `APP_URL` | web | Public base URL of the web app |
| `CORS_ORIGIN` | api | Allowed CORS origin(s), comma-separated |
| `JWT_EXPIRES_IN` | api | JWT expiry duration (e.g. `1h`, `7d`) |
| `LOG_LEVEL` | api, worker | Logging verbosity (`debug` / `info` / `warn` / `error`) |
| `WORKER_CONCURRENCY` | worker | Number of concurrent jobs per worker instance |

### Required GitHub Secrets (set per environment)

| Secret | Apps | Rotate? | Description |
| --- | --- | --- | --- |
| `DATABASE_URL` | api, worker | Yes | Full database connection string including credentials |
| `JWT_SECRET` | api | Yes | Secret used to sign and verify JWTs |
| `REDIS_URL` | worker | Yes | Redis connection string for job queue |

## Required documentation per setting

For every required setting, document:

- name
- purpose
- which app uses it
- required environments
- safe local placeholder
- whether rotation or expiry matters

## Agent rules

Agents may add or rename configuration keys, but must update this documentation and the example config file in the same PR.

Agents must not place real credentials, tokens, private keys, customer exports, or private operational data into the repository.
