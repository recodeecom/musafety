# /gx-doctor

Run repo repair + verification.

Steps:
1. `gx doctor` — installs/refreshes Guardex scaffolding, prunes stale worktrees, auto-finishes ready PRs.
2. If issues remain, surface them with the relevant fix command (`gx setup`, `gx claude install`, `gx locks claim`, etc.).
3. Report final state as `Repo is fully safe` or list outstanding errors/warnings.

Useful flags to pass through:
- `--dry-run` — preview without writing.
- `--current` — limit to the top-level repo (no recursive scan).
- `--no-wait-for-merge` — skip the auto-finish PR-merge polling.
- `--json` — machine-readable output for scripts.
