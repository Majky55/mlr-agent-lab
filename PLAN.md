# PLAN.md

Keep this honest and short: where things actually stand, then the single next step.
Update it as part of the work, not afterwards.

## Progress

Done:

- **2026-10-22 — toolchain.** `gh` 2.103.0 and `uv` 0.13.5 installed to `~/.local/bin`
  without admin rights; both verified working. uv end-to-end test passed (venv, managed
  CPython 3.15.1 download, PyPI install, import).
- **2026-10-22 — repo.** Public `Majky55/mlr-agent-lab` created; local folder initialised
  on branch `main` with `origin` attached and the noreply commit identity set locally.
- **2026-10-22 — working rules.** `AGENTS.md` (+ `CLAUDE.md` import), `README.md`,
  `PLAN.md`, `RUNS.md` written.

Not done:

- Nothing is committed yet — all five files exist only on disk, and the remote has zero
  commits and zero branches.
- No `pyproject.toml`, no `.venv`, no code, no checks.
- The project goal in `README.md` is still a placeholder.

## Next step

Commit and push the docs so the repo has a first commit on `main`, then `uv init` and turn
the goal in `README.md` into a first runnable experiment with a check attached to it.

Smaller tasks, in order:

1. `git add -A && git commit -m "Add project docs and agent working rules" && git push -u origin main`
2. Fill in the real goal and success metric in `README.md`.
3. `uv init` — pin a Python version, add the first dependencies.
4. Define the first experiment and, with it, the check that will be run before it is
   called done.

## Open questions

- What exactly is being measured, and against what baseline?
- Notebooks for exploration, or plain scripts for reproducibility?
