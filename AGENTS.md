# AGENTS.md — working rules

Rules for any AI agent working in this repository (Claude Code, Codex, or other).
These are requirements, not preferences. If a task conflicts with one, say so before acting.

## 1. Orient first

Before touching anything, read:

1. [`README.md`](README.md) — what this project is for, and how to run it.
2. [`PLAN.md`](PLAN.md) — where the work actually stands, and the next step.

If those files contradict the task you were given, raise the contradiction *before*
proceeding. Don't silently pick one and hope.

## 2. Python goes through uv

`uv` is the only sanctioned way to run or install Python here.

| Do | Don't |
| --- | --- |
| `uv add <pkg>` / `uv add --dev <pkg>` | `pip install` into a global or system interpreter |
| `uv run python script.py`, `uv run pytest` | bare `python script.py`, bare `pytest` |
| `uv sync` to reproduce the environment | hand-editing `uv.lock` |

Why it matters: a global install isn't recorded in `pyproject.toml` / `uv.lock`, so the
next person — or the next agent run — gets a different environment and a result that
doesn't reproduce.

Commit `pyproject.toml` and `uv.lock` together, in the same commit.

`uv` is installed per-user at `~/.local/bin/uv` (this machine has no admin rights).

## 3. Check before you say "done"

Before claiming something works, is fixed, or is finished:

- Run the narrowest check that actually exercises the change.
- Quote the command and its real output in the report.
- Report a failing check as a failure, with the output, not smoothed over.
- If no check exists, say plainly **not verified**, and name what would verify it.

Describing a result you didn't observe, or implying a check ran when it didn't, is a
false report. Unverified-and-admitted is fine; unverified-and-claimed is not.

## 4. Repo conventions

- **This repo is public.** No secrets, tokens, API keys, credentials, or raw data you
  don't have the rights to publish. Ever.
- Commit author: `Majky55 <99173549+Majky55@users.noreply.github.com>` (repo-local git
  config is already set to this; the machine's global config still has a real email).
- Log substantive runs in [`RUNS.md`](RUNS.md): model, what was asked, how it was checked.
