---
title: "Cannot See SharePoint, Teams or Other Users Data"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_troubleshoot_roles.html"
last_updated: "9/19/2025"
product_version: ""
---

# Cannot See SharePoint, Teams or Other Users Data


Issue

You are unable to explore and restore SharePoint, Teams, or other users backups.

Summary

When logged in to Veeam Data Cloud for Microsoft 365, you are unable to see SharePoint or Teams data in the restore page.

Cause

The role assigned to your account is missing the required permissions.

Resolution

Assign the M365:RestoreOperator user role to the account. For details, see [Editing Users](users_edit.md).

|  |
| --- |
| Note |
| You may need to log out and then log in back to your account for the changes to take effect. |

Help And Support

If you have followed the steps outlined above, and the issue recurs in the next backup cycle, or you need help with performing these changes, you can contact [Veeam Customer Support](https://www.veeam.com/support.html#Data_Cloud_Support).

