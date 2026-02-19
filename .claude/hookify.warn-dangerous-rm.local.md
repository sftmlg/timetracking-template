---
name: warn-dangerous-rm
enabled: true
event: bash
pattern: rm\s+(-[^-]*r[^-]*f|--recursive.*--force|--force.*--recursive|-rf|-fr)
action: warn
---

⚠️ **Dangerous rm command detected!**

You're about to run a recursive force delete (`rm -rf`).

**Before proceeding:**
- Verify the target path is correct
- Confirm this won't delete important files
- Consider using `ls` first to preview what will be deleted

**Ask the user for confirmation before executing this command.**
