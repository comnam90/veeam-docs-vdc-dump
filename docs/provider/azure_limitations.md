---
title: "Considerations and Limitations"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/azure_limitations.html"
last_updated: "2/6/2026"
product_version: ""
---

# Considerations and Limitations


|  |
| --- |
| Important |
| Veeam Data Cloud for Microsoft Azure does not support Microsoft Azure features that are currently in the preview state. For more information, see [Microsoft Docs](https://learn.microsoft.com/en-us/azure/devops/project/navigation/preview-features?view=azure-devops). |

Before you start using Veeam Data Cloud for Microsoft Azure, keep in mind the following limitations and considerations.

Backup

Consider the following about backing up Azure resources:

* Veeam Data Cloud for Microsoft Azure only supports storage accounts that use the locally redundant storage (LRS) redundancy option.

* Consider the following about backup of Azure resources deployed in virtual networks with restricted access:

* Veeam Data Cloud for Microsoft Azure supports backup of Azure SQL databases deployed with private endpoints.

|  |
| --- |
| Important |
| If your SQL server [does not allow public access](https://learn.microsoft.com/en-us/azure/azure-sql/database/private-endpoint-overview?view=azuresql#disable-public-access-to-your-logical-server), the backup policy will send a private endpoint connection request to the server during the first run, which will initially fail. To make future policy runs succeed, you must approve the connection request in your Azure portal. Until this is done, the policy will continue to fail.  To learn more, see [Microsoft Docs](https://learn.microsoft.com/en-us/azure/azure-sql/managed-instance/private-endpoint-overview?view=azuresql&tabs=separate-vnets#review-and-approve-a-request-to-create-a-private-endpoint). |

* Veeam Data Cloud for Microsoft Azure currently does not support backup of VMs deployed in virtual networks with restricted (private) network access. Support for this scenario is planned for a future release.
* Veeam Data Cloud for Microsoft Azure does not support backup of Azure Files file shares when the associated storage account is configured with network restrictions.

* Veeam Data Cloud for Microsoft Azure does not support backup of Azure VMs whose source disks have the data access authentication mode enabled. For more information on the data access authentication mode, see [Microsoft Docs](https://learn.microsoft.com/en-us/azure/virtual-machines/windows/download-vhd?tabs=azure-portal#enable-data-access-authentication-mode).
* Due to Microsoft Azure limitations, Veeam Data Cloud for Microsoft Azure does not support backup of [Ephemeral OS disks](https://learn.microsoft.com/en-us/azure/virtual-machines/ephemeral-os-disks#unsupported-features).
* You can create SQL backup policies to protect only Azure SQL databases running on SQL Servers and databases located on SQL Managed Instances. If you want to protect a database hosted by a SQL Server on Azure VM, create an [Azure VM backup policy](azure_backup_create_vm.md). Note that in this case, you will not be able to restore a single database without restoring the entire VM.
* Due to export process limitations, it is recommended that you back up Azure SQL databases up to 16 TB in size for optimal reliability. Backup of larger databases has not been tested and may not be supported.
* Veeam Data Cloud for Microsoft Azure does not support backup of databases hosted by Azure Arc-enabled SQL Managed Instances and SQL Servers on Azure Arc-enabled servers.
* Veeam Data Cloud for Microsoft Azure uses BACPAC files to back up SQL databases. BACPAC export of databases with external references is not supported. If a SQL database was migrated to an Azure SQL Database Server or Azure SQL Managed Instance, make sure to clear legacy references, orphaned database users and credentials set up with authentication types not supported by Azure SQL, to avoid BACPAC export errors. To learn more about BACPAC files, see [Microsoft Docs](https://learn.microsoft.com/en-us/sql/tools/sql-database-projects/concepts/data-tier-applications/overview?view=sql-server-ver17#bacpac).
* To store backups, Veeam Data Cloud for Microsoft Azure automatically creates a repository in every Azure region whose resources are protected by the backup policy.
* Veeam Data Cloud for Microsoft Azure does not support adding of Azure SQL Server accounts using Microsoft Entra ID authentication. To add an Azure SQL Server account, you must specify credentials of a SQL Server Admin account.
* If you delete a file share from Microsoft Azure, all the snapshots of this file share will be deleted as well. To protect your snapshots from accidental deletion, you can use the file share soft delete option. For more information on the soft delete option for Azure Files, see [Microsoft Docs](https://docs.microsoft.com/en-us/azure/storage/files/storage-files-enable-soft-delete?tabs=azure-portal).
* Before you create an Azure files backup policy, make sure that the Allow storage account key access option for Shared Key authorization is enabled for the storage accounts where the file shares that you plan to protect reside — otherwise, backup operations will fail. For more information on Shared Key authorization, see [Microsoft Docs](https://learn.microsoft.com/en-us/rest/api/storageservices/authorize-with-shared-key?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&bc=%2Fazure%2Fstorage%2Fblobs%2Fbreadcrumb%2Ftoc.json).
* Due to Microsoft Azure limitations, Veeam Data Cloud for Microsoft Azure does not support backup of [NFS Azure file shares](https://learn.microsoft.com/en-us/azure/storage/files/files-nfs-protocol).
* Due to Microsoft Azure limitations, Veeam Data Cloud for Microsoft Azure does not support retention of locked snapshots. This means that Veeam Data Cloud for Microsoft Azure will not be able to remove an outdated snapshot during a retention session if the snapshot is protected from deletions and modifications using the lock feature. For more information on the lock feature, see [Microsoft Docs](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources?tabs=json).

Restore

Consider the following about restoring Azure resources:

* Veeam Data Cloud for Microsoft Azure does not support restore of Azure confidential VMs. For more information on Azure confidential VMs, see [Microsoft Docs](https://learn.microsoft.com/en-us/azure/confidential-computing/confidential-vm-overview).

* When performing restore operations, Veeam Data Cloud for Microsoft Azure assigns Azure tags to the processed resources. If you have any Azure policies that do not allow tag assignment, the restore operations will fail. To learn more about Azure policies, see [Microsoft Docs](https://learn.microsoft.com/en-us/azure/governance/policy/overview).

* Veeam Data Cloud for Microsoft Azure does not support restore of locked Azure VMs and Azure virtual disks. For more information on the lock feature, see [Microsoft Docs](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources?tabs=json).

Azure Disk Encryption

Backup and restore operations are supported within one Azure region only. If you choose to back up or restore your data to another region, you must first migrate to the target region all Azure key vaults, cryptographic keys and secrets used to encrypt the source Azure resources, as described in [Microsoft Docs](https://docs.microsoft.com/en-us/azure/key-vault/general/move-region).

For more information on Azure Disk Encryption, see [Microsoft Docs](https://docs.microsoft.com/en-us/azure/security/fundamentals/encryption-overview).

