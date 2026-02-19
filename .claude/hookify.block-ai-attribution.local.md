---
name: block-ai-attribution
enabled: true
event: bash
pattern: git\s+commit.*(-m|--message).*(?i)(claude|generated\s+with|co-authored-by.*claude|co-authored-by.*anthropic|noreply@anthropic|AI\s+generated)
action: block
---

🚫 **AI Attribution Detected in Commit!**

Your commit message contains AI attribution which is **strictly forbidden**.

**Blocked patterns:**
- "Claude" anywhere in the message
- "Generated with [Claude Code]"
- "Co-Authored-By: Claude"
- "noreply@anthropic.com"
- Any AI attribution whatsoever

**Rule:** Commits must be clean and human-authored. No Claude or AI attribution anywhere.

**Fix:** Remove all AI references from your commit message and try again.
