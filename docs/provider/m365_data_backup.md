---
title: "Data Backup"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/m365_data_backup.html"
last_updated: "12/30/2025"
product_version: ""
---

# Data Backup


This section describes backup concepts of Veeam Data Cloud for Microsoft 365.

Backup Applications

To back up Microsoft 365 data, Veeam Data Cloud for Microsoft 365 uses Microsoft Entra ID applications.

The first Microsoft Entra application registration is created when you [add a Microsoft 365 tenant](m365_tenant_add.md) to Veeam Data Cloud for Microsoft 365. You can either select to create the application registration automatically or manually:

* If you choose to automatically connect Veeam Data Cloud for Microsoft 365 to your Microsoft 365 tenancy, Veeam Data Cloud for Microsoft 365 creates a new application registration and grants the required permissions.
* If you choose to manually connect Veeam Data Cloud for Microsoft 365 to your Microsoft 365 tenancy, you must manually grant the required permissions for the new or existing application registration. For more information on the required permissions, see [Microsoft Entra Application Permissions](m365_permissions.md).

Backup Retention

Veeam Data Cloud for Microsoft 365 uses the snapshot-based retention mechanism to store the backed-up data. With each backup policy run, Veeam Data Cloud for Microsoft 365 captures a snapshot or state of a backed-up item, and saves it to the backup location. The item state comprises a cumulative set of item versions created for the item in Microsoft 365. The item state belongs to a specific restore point.

Snapshot-based retention works in the following way:

1. During the initial backup of an item, Veeam Data Cloud for Microsoft 365 creates the first restore point with the initial item state. The item state contains all versions of the item that exist in Microsoft 365 at the moment when the backup is created.
2. When a user modifies the item in Microsoft 365 once again, Microsoft 365 creates a new version for the item.
3. During a subsequent backup session, Veeam Data Cloud for Microsoft 365 creates a new restore point with a new item state. The new item state cumulatively includes all versions of the item created by Microsoft 365, including those that are already contained in the first restore point.
4. After the retention period for the first restore point expires, Veeam Data Cloud for Microsoft 365 removes the restore point from the backup location — that is, removes the item state. The item itself remains in the backup location.

Veeam Data Cloud for Microsoft 365 will repeat this operation for all subsequent restore points that contain newer states of the item until the retention period expires for the last restore point, and the last restore point is removed as well.

Retention is set to 1 year by default, and can be customized to offer an unlimited time period. To do this, contact [Veeam Customer Support](https://www.veeam.com/support.html#Data_Cloud_Support).

Once the data is backed up, you cannot delete it.

Backup and Restore of Public Folders

Veeam Data Cloud for Microsoft 365 supports backup and restore of public folders.

To back up and restore public folders, you must grant the following roles and permissions during onboarding:

* The Microsoft 365 Global Admin account that you use for onboarding must have the Owner role at the root level of the public folder hierarchy. For more information, see [Granting Owner Role in PowerShell](m365_grant_owner_role.md).
* The Microsoft 365 Global Admin account that you use for onboarding must have a valid Exchange Online license and an active mailbox within the Microsoft 365 organization.
* To back up public folders and discovery search mailboxes in Microsoft 365 organizations, Veeam Data Cloud for Microsoft 365 needs access to Exchange Online PowerShell. To access Exchange Online PowerShell, the Microsoft Entra application must have the Exchange.ManageAsApp permission and the Global Reader role. For information on how to grant the Global Reader role, see [Granting Global Reader Role to Microsoft Entra Application](m365_permissions.md#globalreader).

Consider the following limitations:

* Backup and restore of public folders requires the Variable License Model.
* Veeam Data Cloud for Microsoft 365 only backs up and restores public folders located under the IPM\_SUBTREE folder.
* When backing up public mailboxes, only select the root public mailbox. Any child folders of the selected public mailbox will be backed up as well.
* Veeam Data Cloud for Microsoft 365 does not back up permissions for sharing mailbox folders and calendar.

To back up public folders, select the public folders that are listed as Microsoft 365 users when you create a backup policy. For more information, see [Microsoft 365 Backup](m365_backup.md).

To restore public folders, explore your Outlook backups, select the public folder mailbox and restore it. For more information, see [Restoring Outlook Mailboxes](m365_restore_outlook_mailbox.md).

Data Validation

Veeam Data Cloud for Microsoft 365 uses various data validation methods to ensure that backed-up data is correct.

