# /gx-status

Show the gitguardex status of the current repo: branch, guardex toggle,
worktree count, agent-branch list, pending findings, and protected-base
health.

```
gx status                # human-readable
gx status --json         # machine-readable
gx status --strict       # treat warnings as failures (exit 1 on any)
```

When status reports findings, run `/gx-doctor` to repair.
