# /gx-finish

Finish the current agent worktree task end-to-end: commit (if needed),
push, open PR, wait for merge, prune the worktree.

Default invocation for the current agent branch:

```
gx branch finish \
  --branch "$(git branch --show-current)" \
  --base main \
  --via-pr \
  --wait-for-merge \
  --cleanup
```

To sweep every finished agent lane in this repo at once:

```
gx finish --all
```

Pre-conditions:
- Working tree is clean OR commits are already in the worktree.
- `gh auth status` is healthy (or `GITHUB_TOKEN` is set).
- Tests for the touched area pass (run `npm test`/equivalent first).

If branch protection blocks the merge, the flow returns the PR URL and
sets auto-merge. Re-run `/gx-pr watch` to follow it.

Do NOT replace this with standalone `git push` + `gh pr create` — those
skip Guardex's cleanup, lock release, and worktree prune.
