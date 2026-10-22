# RUNS.md

Log of substantive working sessions: which model ran, what was asked, and how the result
was actually checked. Newest first. One entry per session — keep each short enough to skim.

The model line should come from `/status` in the Claude Code session that did the work.

---

## 2026-10-22 — toolchain install, repo creation, working rules

**Model (from `/status`):** *not recorded — the session could not read its own `/status`
output. Owner: paste it here.*

**Asked:**
1. Install `gh` and `uv` into the user folder without admin rights, and check both work.
2. Create a public repo `mlr-agent-lab` from this folder with gh, showing what would be
   uploaded before pushing.
3. Write `AGENTS.md` with our working rules, make `CLAUDE.md` load it, and add `README.md`,
   `PLAN.md`, `RUNS.md`.

**Done:** both tools installed to `~/.local/bin` from official GitHub release zips (no
admin, no PATH change needed — the directory was already on PATH). Repo created public and
empty by choice; local folder initialised on `main` with `origin` and noreply author.
Five docs written.

**How it was checked:**

| Item | Check | Result |
| --- | --- | --- |
| gh, uv on PATH in a fresh shell | versions resolved with PATH rebuilt from registry only | `gh 2.103.0`, `uv 0.13.5`, `uvx 0.13.5` |
| uv really works | `uv venv`, `uv pip install idna`, `import idna`, `uv run` | passed; pulled managed CPython 3.15.1, installed idna 3.20 |
| repo is public | anonymous `curl` to the GitHub API, no token | `private: false`, `size: 0` |
| repo is empty | `gh repo view --json isEmpty`, `git ls-remote --heads origin` | `isEmpty: true`, no branches |
| gh authenticated | `gh auth status` | logged in as `Majky55`, scopes `repo, workflow, gist, read:org` |

**Not verified / caveats:**

- gh's outbound HTTPS path was never exercised — gh refuses all API calls until
  authenticated, and it wasn't at test time. It authenticated later and worked fine for
  repo creation, which covers this retrospectively.
- The requested "show what will be uploaded" review was moot: the folder was empty.
- The `/status` model string is missing, as noted above.

**Files:** `AGENTS.md`, `CLAUDE.md`, `README.md`, `PLAN.md`, `RUNS.md` (all uncommitted).
