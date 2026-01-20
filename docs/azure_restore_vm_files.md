---
title: "Restoring VM Files"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_restore_vm_files.html"
last_updated: "1/20/2026"
product_version: ""
---

# Restoring VM Files


You can recover corrupted or missing files of an Azure VM from a cloud-native snapshot or image-level backup. Veeam Data Cloud for Microsoft Azure allows you to restore the files and folders of the source Azure VM to the original location using the File-Level Recovery Explorer.

|  |
| --- |
| Important |
| Consider the following:   * To perform file-level recovery, the Azure VM must be in the running state. * File-level recovery is supported from FAT, FAT32, NTFS, EXT2, ext3, ext4, XFS, BTRFS file systems only. For Microsoft Windows systems, file-level recovery is supported for basic volumes only. * File-level recovery of Azure VMs with the [Azure Disk Encryption option](https://docs.microsoft.com/en-us/azure/security/fundamentals/encryption-overview) enabled is not supported in the current Veeam Data Cloud for Microsoft Azure version. * File-level recovery from virtual disks with Windows-native [Data Deduplication](https://learn.microsoft.com/en-us/windows-server/storage/data-deduplication/overview) enabled is not supported. To work around the issue, you can restore entire virtual disks, and then attach these disks to an Azure VM with the deduplication feature enabled. To learn how to restore entire virtual disks, see [Restoring VM Disks](azure_restore_vm_disks.md). |

To recover files and folders of a protected Azure VM, do the following:

1. [Launch the File-Level Recovery wizard](azure_restore_vm_files_launch.md).
2. [Select a restore point](azure_restore_vm_files_point.md).
3. [Start the restore session](azure_restore_vm_files_session.md).
4. [Select files to restore](azure_restore_vm_files_explorer.md).
5. [Review and stop the restore session](azure_restore_vm_files_session_stop.md).

