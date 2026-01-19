---
title: "Restoring Synchronized Users (Hybrid Identity)"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/entra_id_restore_user_sync.html"
last_updated: "7/24/2025"
product_version: ""
---

# Restoring Synchronized Users (Hybrid Identity)


Veeam Data Cloud for Microsoft Entra ID allows you to restore users that are synchronized with Microsoft Active Directory (hybrid identities). Unlike the synchronization software (for example, [Microsoft Entra Connect](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/whatis-azure-ad-connect-v2)), restore with Veeam Data Cloud preserves relations stored in your Entra ID tenant: group memberships, assigned roles, used licenses and other relations.

Veeam Data Cloud for Microsoft Entra ID restores only the supported properties and relations. For details, see [Supported Entra ID Item Properties](entra_id_properties.md). To restore other properties, you still need synchronization software and, in some cases, local Active Directory restore. This section describes possible scenarios and steps for restore.

Restoring Users Removed from Entra ID Without Subsequent Synchronization

If a synchronized user is removed only from Entra ID, and no synchronization process occurs after the removal, take the following steps:

1. In Veeam Data Cloud for Microsoft Entra ID, use the Restore Users wizard to restore an entire user to Entra ID. At the Options step of the wizard, make sure to enable the Keep Relationships option. For details on user restore, see [Restoring Entire Users](entra_id_restore_user.md).

Veeam Data Cloud will restore the user with a new object ID.

1. Wait for or launch synchronization with Active Directory, for example, using Microsoft Entra Connect.

After the synchronization, the relations restored using Veeam Data Cloud will be preserved, the existing properties will be overwritten, and the lacking properties will be restored. The user will become a hybrid identity.

Restoring Users Removed from Entra ID with Subsequent Synchronization

If a synchronized user is removed only from Entra ID, but the synchronization restores this user, Veeam Data Cloud will not be able to map this user and restore the relationships. In this case, take the following steps:

1. Remove from Entra ID the user that was created after the synchronization.
2. In Veeam Data Cloud for Microsoft Entra ID, use the Restore Users wizard to restore the entire user to Entra ID. At the Options step of the wizard, make sure to enable the Keep Relationships option. For details on user restore, see [Restoring Entire Users](entra_id_restore_user.md).

Veeam Data Cloud will restore the user with a new object ID.

1. Wait for or launch synchronization with Active Directory, for example, using Microsoft Entra Connect.

After the synchronization, the relations restored using Veeam Data Cloud will be preserved, the existing properties will be overwritten, and the lacking properties will be restored. The user will become a hybrid identity.

Restoring Users Removed from Entra ID and Active Directory

If a synchronized user is removed from Entra ID and Active Directory, take the following steps:

1. In Veeam Data Cloud for Microsoft Entra ID, use the Restore Users wizard to restore an entire user to Entra ID. At the Options step of the wizard, make sure to enable the Keep Relationships option. For details on user restore, see [Restoring Entire Users](entra_id_restore_user.md).

Veeam Data Cloud will restore the user with a new object ID.

1. Use Veeam Backup & Replication application item restore or Veeam Explorer for Microsoft Active Directory to restore the user locally in Active Directory. For details, see the [Application Item Restore](https://helpcenter.veeam.com/docs/backup/vsphere/restore_veeam_explorers.html?ver=120) section of the Veeam Backup & Replication User Guide and the [Veeam Explorer for Microsoft Active Directory](https://helpcenter.veeam.com/docs/backup/explorers/vead_user_guide.html?ver=120) section of the Veeam Explorers User Guide.
2. Wait for or launch synchronization with Active Directory, for example, using Microsoft Entra Connect.

After the synchronization, the relations restored using Veeam Data Cloud will be preserved, the existing properties will be overwritten, and the lacking properties will be restored. The user will become a hybrid identity.

