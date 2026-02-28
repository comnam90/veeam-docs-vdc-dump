---
title: "How Entra ID Restore Works"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/entra_id_data_restore_how.html"
last_updated: "2/20/2026"
product_version: ""
---

# How Entra ID Restore Works


When Veeam Data Cloud restores entire Entra ID objects, it attempts the following restore operations in sequence: restore from the Entra ID recycle bin and restore from backup. You can specify how Veeam Data Cloud must proceed through these operations in the restore wizard, for example, in the Restore Users wizard. For more information on which Microsoft Entra ID objects Veeam Data Cloud can restore, see [Entra ID Restore](entra_id_data_restore.md).

Each object in Microsoft Entra ID has a unique ID that Veeam Data Cloud can change or preserve depending on the selected restore method. Regardless of whether the object ID changes, the object retains a continuous set of recovery points.

After you complete a restore wizard, Veeam Data Cloud starts a restore session. The restore session includes the following steps:

1. Veeam Data Cloud attempts to restore objects from the Entra ID recycle bin. If the objects still exist in the recycle bin, Veeam Data Cloud restores them to production. The objects that do not exist in the recycle bin will not be restored.

When you restore an object from recycle bin, the object preserves its original object ID.

To skip this step, clear the Restore from Entra ID Recycle Bin check box at the Options step of the restore wizard.

1. Veeam Data Cloud attempts to restore objects from backup. This process depends on the options you select:

* If you configure the restore to skip objects that already exist in your Entra ID tenant, Veeam Data Cloud restores only objects that were deleted, but it does not overwrite existing objects, including those restored from the recycle bin. When the restore completes, Veeam Data Cloud sets the Warning status for skipped objects. For details on how to view restore session status, see [Viewing Backup and Restore Sessions](entra_id_activity.md).
* If you configure the restore to overwrite objects that already exist in your Entra ID tenant, Veeam Data Cloud restores deleted objects and replaces existing objects that you selected to restore with the version from the backup.

When you restore a deleted object from backup, it receives a new object ID. However, Veeam Data Cloud maintains a link between the original and the new object IDs. This ensures that the object retains a continuous set of restore points.

To specify whether Veeam Data Cloud must skip or overwrite objects, select Skip or Overwrite at the Options step of the restore wizard.

|  |
| --- |
| Note |
| If you restore a deleted object from backup and later use the Microsoft Entra ID portal to restore the same object from the Entra ID recycle bin, two separate instances of the object will exist. After Veeam Data Cloud completes the next backup, both instances will appear as distinct items when you browse Entra ID objects in Veeam Data Cloud, each with its own set of restore points. If you then permanently delete the object restored from the recycle bin, all future restores from either set of restore points will target the object that was originally restored from the backup. |

