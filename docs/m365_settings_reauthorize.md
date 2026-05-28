---
title: "Reauthorizing Veeam Data Cloud for Microsoft 365"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_settings_reauthorize.html"
last_updated: "5/26/2026"
product_version: ""
---

# Reauthorizing Veeam Data Cloud for Microsoft 365


You may need to reauthorize Veeam Data Cloud access to your Microsoft 365 tenant. This may be required in the following cases:

* If you have accidentally removed authorization for Veeam Data Cloud to access your Microsoft 365 data.
* If you see the following error message in the backup session logs: The identity of the calling application could not be established.
* If Veeam Data Cloud displays the You cannot enable Teams Posts due to missing required permissions. Please reauthorize your app registration and try again. notification when you enable team posts backups.
* If Veeam Data Cloud displays the following notification in the dashboard: Veeam Data Cloud for Microsoft 365 now uses Microsoft Graph APIs for Outlook data protection. EWS (Exchange Web Services), previously used for this purpose, is being deprecated by Microsoft. To continue protecting your Outlook data, before July 1, 2026 reauthorize your Veeam Data Cloud app registration: go to Settings → Microsoft 365 and select Reauthorize Veeam Data Cloud.

To reauthorize Veeam Data Cloud, do the following:

1. On the Microsoft 365 page, click the name of the tenant you want to manage.
2. Select Settings.
3. Go to the Microsoft 365 tab.
4. In the Reauthorize Veeam Data Cloud section, do one of the following:

* Click Reauthorize existing app registration to reauthorize and continue using your existing application registration.
* Click Create new app registration, to create a new application registration.

|  |
| --- |
| NOTE |
| If you select to create a new app registration, you must enable team posts backup again. For more information, see [Enabling Microsoft Team Posts Backup](m365_enable_team_chats_backup.md). |

[![Reauthorizing Veeam Data Cloud for Microsoft 365](images/m365_settings_reauthorize_vdc.webp)](images/m365_settings_reauthorize_vdc.webp "Reauthorizing Veeam Data Cloud for Microsoft 365")

1. Select the Microsoft account under which you want to authenticate against Microsoft 365. The account must have the Microsoft 365 Global Admin permissions.
2. Accept the required permissions.

