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

## Environment configuration rules

| Environment | Config source | Data policy |
| --- | --- | --- |
| `dev` | local example file or development secret store | synthetic or disposable data |
| `stg` | staging secret/config store | production-like synthetic or sanitized data |
| `prd` | production secret/config store | production data controls |

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
