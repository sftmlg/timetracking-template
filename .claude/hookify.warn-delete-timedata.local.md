---
name: warn-delete-timedata
enabled: true
event: bash
pattern: rm\s+.*(KW[0-9]+\.md|SUMMARY\.md|20[2-9][0-9]-[0-9]{2}[/\\])
action: warn
---

⚠️ **Time Tracking Data Deletion Detected!**

You're about to delete a time tracking file or folder.

**These files are the source of truth for invoicing.** Deleting them means:
- Hours logged are permanently lost
- Monthly invoices can no longer be verified
- Client disputes cannot be resolved with evidence

**Before proceeding:**
- Is this entry already invoiced? Deleting it creates a gap in billing history.
- Are you correcting an error? Edit the file instead of deleting it.
- Is this a whole month folder? Verify all KW files inside are no longer needed.

**Ask the user for explicit confirmation before deleting any time entries.**
