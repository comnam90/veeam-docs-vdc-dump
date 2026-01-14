---
title: "How Entra ID Restore Works"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/entra_id_data_restore_how.html"
last_updated: "12/12/2025"
product_version: ""
---

# How Entra ID Restore Works

In this article

When Veeam Data Cloud restores entire Entra ID objects, it attempts the following restore operations in sequence: restore from the Entra ID recycle bin and restore from a backup. You can specify how Veeam Data Cloud must proceed through these operations in the restore wizard, for example, in the Restore Users wizard. For more information on what Microsoft Entra ID objects Veeam Data Cloud can restore, see [Entra ID Restore](entra_id_data_restore.md).

After you complete a restore wizard, Veeam Data Cloud starts a restore session. The restore session includes the following steps:

1. Veeam Data Cloud attempts to restore objects from the Entra ID recycle bin. If the objects still exist in the recycle bin, Veeam Data Cloud restores them to production. The objects that do not exist in the recycle bin will not be restored.

To skip this step, clear the Restore from Entra ID Recycle Bin check box at the Options step of the restore wizard.

1. Veeam Data Cloud attempts to restore objects using the backed-up data. This process depends on the options you select:

* If you configure the restore to skip objects that already exist in your Entra ID tenant, Veeam Data Cloud restores only objects that were deleted. However, it does not overwrite existing objects in your Entra ID tenant, including those restored from the recycle bin. The final status of the restore for skipped objects is Warning.
* If you configure the restore to overwrite objects that already exist in your Entra ID tenant, Veeam Data Cloud restores deleted objects and replaces existing objects that you selected to restore with the version from the backup.

To specify whether Veeam Data Cloud must skip or overwrite objects, select Skip or Overwrite at the Options step of the restore wizard.

Page updated 12/12/2025
