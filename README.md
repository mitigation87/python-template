# python-template

Template Python project with a Claude Code devcontainer sandbox.

## What's inside

- `.devcontainer/` — Dockerfile, devcontainer.json, and `init-firewall.sh` that
  restricts outbound network traffic to an allowlist. Safe environment for
  running `claude --dangerously-skip-permissions`.
- `.claude/settings.local.json` — starter allow/deny rules for Claude Code.
- `pyproject.toml` — Python 3.12 project managed by [uv](https://docs.astral.sh/uv/),
  with `ruff` and `pytest` pre-configured.
- `CLAUDE.md` — project conventions for Claude.

## Getting started

```bash
# copy into a new project
cp -R python-template my-new-project
cd my-new-project
# edit pyproject.toml: set name + description
# edit CLAUDE.md: replace with project-specific notes
```

Open the folder in VS Code with the **Dev Containers** extension installed and
choose *Reopen in Container*. Then inside the container:

```bash
uv sync
claude --dangerously-skip-permissions
```
