---
title: "Viewing Licensed Users"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_settings_view_licensed_users.html"
last_updated: "9/19/2025"
product_version: ""
---

# Viewing Licensed Users


You can check which accounts are currently using the Veeam Data Cloud for Microsoft 365 license. To do this, follow these steps:

1. On the Microsoft 365 page, click the name of the tenant you want to manage.
2. Select Settings.
3. Select the Licensed Users tab.

[![Viewing Licensed Users](images/m365_settings_view_licensed_users.png)](images/m365_settings_view_licensed_users.png "Viewing Licensed Users")

In the table with your current Veeam Data Cloud for Microsoft 365 licensed users, the following information is displayed:

* Name — the email account that is licensed.
* License State — the current state of the user if they are licensed or not.
* Last Backup Date — the last date that anything associated with the account was backed up.
* Is Backed Up — shows whether the current data for the account is being backed up.
* Mailbox — shows whether the mailbox of the user is protected or not.
* Archive Mailbox — shows whether the archive mailbox of the user is protected or not.
* OneDrive — shows whether the OneDrive of the user is protected or not.
* Personal Site — shows whether the personal SharePoint site of the user is protected or not.
* Last updated — the last date that the information in the table was updated. The information in the table is automatically updated every day. You can click Refresh to manually update the data to get the current status of your licensed users.

|  |
| --- |
| TIP |
| You can click Export to generate a User Protection Report. For more information, see [Generating Reports](m365_reports_generate.md). |

