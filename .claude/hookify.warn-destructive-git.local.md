---
name: warn-destructive-git
enabled: true
event: bash
pattern: git\s+(reset\s+--hard|clean\s+-[fd]|checkout\s+--force|push\s+.*--force|push\s+-f|rebase\s+-i)
action: warn
---

⚠️ **Destructive Git Operation Detected!**

You're about to run a potentially destructive git command.

**Detected command types:**
- `git reset --hard` — Discards uncommitted changes permanently
- `git clean -fd` — Deletes untracked files permanently
- `git checkout --force` — Overwrites local changes
- `git push --force` — Rewrites remote history (dangerous for shared branches)
- `git rebase -i` — Interactive rebase can rewrite history

**Before proceeding:**
- Verify you have backups or stashes of important changes
- Confirm this won't affect collaborators (especially force push)
- Consider using safer alternatives (git stash, soft reset)

**Ask the user for confirmation before executing.**
