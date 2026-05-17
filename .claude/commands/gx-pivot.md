# /gx-pivot

Pivot the current session onto a fresh agent worktree so edits stop being
blocked by skill_guard on a protected/non-agent branch.

Usage:

```
gx pivot "<task description>" "<agent-name>"
```

Example:

```
gx pivot "Add /pr open" "claude-pr-flow"
```

Output prints `WORKTREE_PATH=...` and `BRANCH=agent/claude-pr-flow/<slug>`.
`cd` into the worktree path, then continue editing.

When to use:
- `skill_guard` blocked an edit/Bash on `main`, `dev`, or any non-agent branch.
- Starting a brand-new task in a fresh session.

When NOT to use:
- You're already inside an agent worktree and just want to continue. Stay put.
- The task is a typo / 1-line tweak the user explicitly marked `quick:` /
  `tiny:` / `just:` — those skip orchestration.
