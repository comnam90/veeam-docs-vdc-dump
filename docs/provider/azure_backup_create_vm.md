---
title: "Creating VM Backup Policies"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/azure_backup_create_vm.html"
last_updated: "4/14/2026"
product_version: ""
---

# Creating VM Backup Policies


Use the New Azure Virtual Machine Policy wizard to create a backup policy to protect Azure virtual machines.

|  |
| --- |
| Important |
| Consider the following:   * If VM disks have restricted network access, Veeam Data Cloud will temporarily modify the networking configuration to allow public SAS link access during the backup, which will enable the creation of snapshots with preserved network settings. Once the backup transfer is complete, the network settings are reverted to their original state. * If network access is completely denied, Veeam Data Cloud will not be able to modify this setting, which will result in backup failure. |

1. [Launch the New Azure Virtual Machines Policy wizard](azure_backup_create_vm_launch.md).
2. [Specify the policy name and description](azure_backup_create_vm_name.md).
3. [Specify the policy source](azure_backup_create_vm_source.md).
4. [Specify the policy protection settings](azure_backup_create_vm_sla.md).
5. [Review the default policy settings](azure_backup_create_vm_review.md).
6. [Specify the guest processing settings](azure_backup_create_vm_guest.md).
7. [Specify the snapshot settings](azure_backup_create_vm_snapshot.md).
8. [Specify the notifications settings](azure_backup_create_vm_name.md).
9. [Complete the backup policy configuration](azure_backup_create_vm_complete.md).

