---
title: "Settings"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/entra_id_settings.html"
last_updated: "2026"
product_version: ""
---

# Settings


The Veeam Data Cloud portal enables you to view general settings of the tenant, include additional Microsoft Entra ID objects in your Entra ID backup, and reauthorize Veeam Data Cloud access to the tenant.

Viewing General Settings

To view the general settings of the tenant:

1. On the Entra ID page, click the name of the tenant you want to manage.
2. Select Settings.
3. Make sure that the General tab is selected.

[![Viewing General Settings](images/entra_id_settings_general.png)](images/entra_id_settings_general.png "Viewing General Settings")

Enabling Backup of Additional Objects

You can enable backup of additional Entra ID objects to include them in your backup scope. Once enabled, Veeam Data Cloud automatically assigns the Veeam Data Cloud for Microsoft Entra ID service principal the additional permissions required to back up and restore the selected objects. For details on required permissions, see [Permissions](entra_id_permissions.md).

|  |
| --- |
| Note |
| The restore and compare of additional objects becomes available only if you enable the backup of those objects, and Veeam Data Cloud completes an Entra ID backup with this option enabled. For details, see [Entra ID Conditional Access Policies Restore](entra_id_cap_restore.md), [Microsoft Intune Policies Restore](entra_id_intune_restore.md), [Comparing Entra ID Organization Contact Properties](entra_id_contacts_compare.md) and [Comparing Entra ID Device Properties](entra_id_devices_compare.md). |

To enable backup of additional objects, do the following:

1. On the Entra ID page, click the name of the tenant you want to manage.
2. Select Settings.
3. Select the Permissions tab.
4. Next to the object type you want to back up, set the toggle to On.
5. Click Save to apply the changes.

[![Enabling Backup of Additional Objects](images/entra_id_settings_permissions.png)](images/entra_id_settings_permissions.png "Enabling Backup of Additional Objects")

Disabling Backup of Additional Objects

To disable backup of additional objects, contact [Veeam Customer Support](https://my.veeam.com/my-cases).

Reauthorizing Veeam Data Cloud

If the Veeam Data Cloud for Microsoft Entra ID service principal is deleted and authorization is revoked, you can reauthorize Veeam Data Cloud access to the Microsoft Entra ID tenant. Veeam Data Cloud verifies the service principal status every time you open the Connection tab on the Settings page and displays the current connection status before you proceed.

If the service principal is present and the connection is intact, Veeam Data Cloud displays a confirmation message, and the Reauthorize button is inactive. Reauthorization is required only when the connection status indicates a problem.

|  |
| --- |
| Note |
| If the service principal exists and is deactivated in your Microsoft Entra ID environment, Veeam Data Cloud will prompt you to activate it manually in the Microsoft Entra ID admin center. |

To reauthorize Veeam Data Cloud for the Entra ID tenant:

1. On the Entra ID page, click the name of the tenant you want to manage.
2. Select Settings.
3. Select the Connection tab.
4. Click Reauthorize.
5. On the Sign in to your account page, log in with a Microsoft 365 account that has Global Administrator privileges.
6. Review the requested permissions and click Accept to grant Veeam Data Cloud access to your Entra ID tenant. For details on required permissions, see [Permissions](entra_id_permissions.md).

After authorization, Veeam Data Cloud updates the Microsoft Entra ID service principal in the tenant.

[![Reauthorizing Entra ID Connection](images/entra_id_settings_connection.webp)](images/entra_id_settings_connection.webp "Reauthorizing Entra ID Connection")

Page updated 2026-07-09
