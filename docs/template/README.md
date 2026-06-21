# Production app template

This directory defines the Phase 2 contract for turning the agent-loop operating scaffold into a reusable production app template.

The current repository intentionally starts with governance and operating structure. A template is not production-ready until the executable app, infrastructure, CI/CD, security, observability, and agent automation contracts in this directory are implemented.

## Files

```txt
docs/template/
  production-ready-app-contract.md   # Required capabilities before the template can be called production-ready
  implementation-roadmap.md          # Recommended order for adding executable implementation
  template-readiness-checklist.md    # Final go/no-go checklist for using the template on real products
```

## Template principle

A production-ready template must be runnable, testable, deployable, observable, secure by default, and understandable by both humans and agents.

Docs alone are not enough. The code and workflows added in future phases must prove the template works.
