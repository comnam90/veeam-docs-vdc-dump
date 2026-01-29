---
title: "Step 3. Specify Restore Options"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/entra_id_restore_group_options.html"
last_updated: "1/29/2026"
product_version: ""
---

# Step 3. Specify Restore Options


At the Options step of the wizard, configure the restore options, such as how to restore groups, their relationships and other:

1. In the Restore mode section, specify whether to overwrite groups or skip restore of the already existing groups.

* When you select the Skip option, Veeam Data Cloud will not overwrite or update objects that already exists.
* When you select the Overwrite option, Veeam Data Cloud updates fields present in the backup. If a field in the backup is empty, it will be restored as empty. However, Veeam Data Cloud does not update read-only fields (the ID, creation date and so on) and fields that are not present in the backup. For details, see [Supported Entra ID Item Properties](entra_id_properties.md).

1. In the Advanced options section, configure the following:

* In the Reason for Restore field, enter a reason for restoring groups. This information will be saved to the session history, and you will be able to reference it later.

* To restore relationships of groups within the current tenant, click Keep Relationships. Veeam Data Cloud will restore the following relationships: assigned roles, the membership in a parent group, memberships in admin units, child groups, user members of the group and group owners. Note that Veeam Data Cloud restores only relationships — if a role, user, group or admin unit does not exist, it will not be restored.

If you have selected the Overwrite option, Veeam Data Cloud will restore the relationships from the backup and will remove the relationships not present in the backup.

* To restore groups from the Entra ID recycle bin instead of the backup, click Restore from Entra ID Recycle Bin. In this case, if the groups exist in both the recycle bin and the backup, they will be restored from the recycle bin and will preserve their object IDs. The groups that do not exist in the recycle bin will not be restored.

To restore groups that cannot be restored from the recycle bin, launch the restore wizard again, select the necessary groups and clear the Restore from Entra ID Recycle Bin check box. The groups will be restored from the backup and get new object IDs.

[![Specifying Restore Options](images/entra_id_restore_group_options.webp)](images/entra_id_restore_group_options.webp "Specifying Restore Options")

