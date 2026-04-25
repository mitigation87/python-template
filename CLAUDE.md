# Python Template

Starter Python project with a Claude Code devcontainer sandbox.

## Using this as a template

1. Copy this folder to a new project directory and rename it.
2. Update `name` and `description` in `pyproject.toml`.
3. Replace this `CLAUDE.md` with project-specific notes (keep the Environment
   and Commands sections if helpful).
4. Add domains your project needs to the allowlist loop in
   `.devcontainer/init-firewall.sh`.

## Environment

- Python 3.12, managed by [uv](https://docs.astral.sh/uv/).
- Intended to run inside the devcontainer at `.devcontainer/` — a Claude Code
  sandbox with a network firewall allowlist (`init-firewall.sh`).
- Inside the container it is safe to run `claude --dangerously-skip-permissions`.

## Common commands

```bash
uv sync                       # install deps from pyproject.toml
uv run python -m <module>     # run a module in the project venv
uv run pytest                 # run tests
uv run ruff check .           # lint
uv run ruff format .          # format
```

## Conventions for Claude

- Prefer `uv run ...` over activating the venv.
- Keep secrets in `.env` (gitignored); never echo them into the shell.
- If code needs to reach a new external domain, add it to the allowlist in
  `.devcontainer/init-firewall.sh` rather than disabling the firewall.
