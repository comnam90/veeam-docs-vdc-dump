---
title: "SharePoint: Failed To Request File Versions For Item"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_troubleshoot_sharepoint_file_versions.html"
last_updated: "9/19/2025"
product_version: ""
---

# SharePoint: Failed To Request File Versions For Item


Issue

While backing up SharePoint Online sites, the Veeam Data Cloud for Microsoft 365 backup session logs say that the backup policy session has completed with a warning: Failed to request file versions for item.

Summary

When checking the Veeam Data Cloud for Microsoft 365 backup session logs, you may see the following warning:

|  |
| --- |
| Warning  Processing site <Name> () finished with warning: Failed to request file versions for item/ sites/ file name.aspx from list Pages (listID: <list ID>, itemID: <item ID>), exception: User cannot be found.) |

Cause

The SharePoint site has been checked out for modification by a user.

If you also get the User cannot be found exception, the user no longer exists in the directory.

Resolution

The user should either discard or save their modifications on the SharePoint site.

If you also get the User cannot be found exception, check the user profile in the SharePoint admin center. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/sharepoint/manage-user-profiles).

Help And Support

If you have followed the steps outlined above, and the issue recurs in the next backup cycle, or you need help with performing these changes, you can contact [Veeam Customer Support](https://www.veeam.com/support.html#Data_Cloud_Support).

References

For information on how to check your backup session logs, see [Viewing Backup Logs](m365_backup_view_logs.md).

