---
title: "Outlook: Failed To Find Group Owner Account"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/m365_troubleshoot_outlook_group.html"
last_updated: "9/19/2025"
product_version: ""
---

# Outlook: Failed To Find Group Owner Account


Issue

While backing up a mailbox, the backup policy is completed successfully, but the Veeam Data Cloud for Microsoft 365 backup session logs say that the backup policy has completed with a warning: Failed to find group owner account.

Summary

When you review the completed Veeam Data Cloud for Microsoft 365 backup that includes Microsoft Exchange items, you may see the following warning message in the backup session logs:

|  |
| --- |
| Warning  Processing mailbox <Name> completed with warning: Failed to find group owner account |

Cause

Veeam Data Cloud for Microsoft 365 is unable to impersonate Microsoft 365 groups (mail-enabled and security groups) that do not have an owner assigned. This is a known Veeam and Microsoft issue.

Resolution

Assign an owner to each of the Microsoft 365 groups that you want to back up. For information on how to do this, see [this Microsoft article](https://support.office.com/en-us/article/assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

Help And Support

If you have followed the steps outlined above, and the issue recurs in the next backup cycle, or you need help with performing these changes, you can contact [Veeam Customer Support](https://www.veeam.com/support.html#Data_Cloud_Support).

References

For information on how to check your backup session logs, see [Viewing Backup Logs](m365_backup_view_logs.md).

