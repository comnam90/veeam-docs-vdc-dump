---
title: "SharePoint: Personal Site Was Not Found"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_troubleshoot_sharepoint_personal.html"
last_updated: "9/19/2025"
product_version: ""
---

# SharePoint: Personal Site Was Not Found


Issue

While backing up SharePoint Online sites, the backup policy is completed successfully, but the Veeam Data Cloud for Microsoft 365 backup session logs say that the backup policy has completed with a warning: Personal site was not found.

Summary

When checking the Veeam Data Cloud for Microsoft 365 backup session logs, you may see the following warning:

|  |
| --- |
| Warning  Processing site <Name> () finished with warning: Personal site was not found (ID: <ID>, name: <Name>) |

Cause

Veeam attempts to process Exchange Online, OneDrive for Business, SharePoint Online and Teams for each user. This particular warning lets you know that the end-user Microsoft license does not include a SharePoint site.

Resolution

You can edit backup policies to exclude certain items from backup. For information on how to do this, see [Editing Flex Backup Policies](m365_backup_edit_flex.md). This is optional: the warning will have no effect on the backups, you can safely ignore it.

Help And Support

If you have followed the steps outlined above, and the issue recurs in the next backup cycle, or you need help with performing these changes, you can contact [Veeam Customer Support](https://www.veeam.com/support.html#Data_Cloud_Support).

References

For information on how to check your backup session logs, see [Viewing Backup Logs](m365_backup_view_logs.md).

