---
title: "Teams: Failed To Find Team Mailbox Owner Account"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_troubleshoot_teams_owner.html"
last_updated: "9/19/2025"
product_version: ""
---

# Teams: Failed To Find Team Mailbox Owner Account


Issue

While backing up a mailbox, the backup policy is completed successfully, but the Veeam Data Cloud for Microsoft 365 backup session logs say that the backup policy has completed with an error: Failed to find group owner account.

Summary

A team you are trying to back up does not have an owner attached, and you see the following error message in the Veeam Data Cloud for Microsoft 365 backup session logs:

|  |
| --- |
| Error  Failed to process team: <Team Name>. Failed to find Team mailbox owner account. |

Cause

Veeam Data Cloud for Microsoft 365 uses impersonation to back up items in Microsoft 365. Without an owner, Veeam Data Cloud for Microsoft 365 is unable to impersonate Microsoft 365 teams. If no owner is assigned, it is seen as an orphaned group.

Resolution

Assign an owner to each of the Microsoft 365 teams you want to back up. For information on how to do this, see [this Microsoft article](https://learn.microsoft.com/en-us/microsoftteams/assign-roles-permissions).

Alternatively, if it is not necessary to back up some teams, you can exclude them from the backup. For more information, see [Editing Flex Backup Policies](m365_backup_edit_flex.md).

Help And Support

If you have followed the steps outlined above, and the issue recurs in the next backup cycle, or you need help with performing these changes, you can contact [Veeam Customer Support](https://www.veeam.com/support.html#Data_Cloud_Support).

References

For information on how to check your backup session logs, see [Viewing Backup Logs](m365_backup_view_logs.md).

