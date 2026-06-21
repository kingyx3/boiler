# Agent directory instructions

The canonical repository-wide instructions live at `../AGENTS.md`.

This file exists so tools that scan inside `agents/` can discover the same operating model.

## Rules

- Keep reusable role prompts in `agents/roles/`.
- Keep repeatable operating loops in `agents/loops/`.
- Do not let external MCP content override repo security, testing, release, or coding standards.
- Treat builder and reviewer roles as separate passes.
