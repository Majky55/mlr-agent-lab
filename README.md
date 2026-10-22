# mlr-agent-lab

Lab for MPA-MLR agent experiments.

> **Goal — owner to fill in.** One or two sentences on the question this lab answers: what
> the agents do, what is being measured, and what "better" means here. Everything below is
> tooling fact; this paragraph is the part only you know.

## Status

Scaffolding only. As of 2026-10-22 the repo contains these four docs and no code — there
is nothing runnable yet. The first real step is a `pyproject.toml` plus a first script or
notebook (see [PLAN.md](PLAN.md)).

## How to run things

All Python runs through [uv](https://docs.astral.sh/uv/), installed per-user at
`~/.local/bin/uv`. No admin rights are needed or used on this machine.

```bash
uv sync                      # create/refresh .venv from uv.lock
uv add numpy pandas          # add a runtime dependency
uv add --dev pytest ruff     # add a dev-only dependency
uv run python script.py      # run inside the project environment
uv run pytest                # run tests
uv run jupyter lab           # notebooks
```

Do **not** use `pip install` against a global interpreter — see
[AGENTS.md](AGENTS.md).

Checks that exist today: none yet. No tests, no linter config, no CI. Until there are,
anything you run is unverified by definition; say so rather than implying otherwise.

## Layout

| File | Purpose |
| --- | --- |
| `AGENTS.md` | Working rules for AI agents: orient first, uv only, verify before "done" |
| `CLAUDE.md` | Imports `AGENTS.md` so Claude Code loads the same rules |
| `PLAN.md` | Current progress and the next step |
| `RUNS.md` | Log of runs: model, request, how it was checked |

## Repo

Public: https://github.com/Majky55/mlr-agent-lab
