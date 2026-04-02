---
title: "Performing Entire File System Restore"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_restore_entire_efs.html"
last_updated: "3/30/2026"
product_version: ""
---

# Performing Entire File System Restore


In case of a disaster, you can restore an entire EFS file system from a cloud-native backup. Veeam Data Cloud for AWS allows you to restore one or more EFS file systems at a time, to the original location or to a new location.

To restore a protected EFS file system, do the following:

1. [Launch the EFS Restore wizard](aws_restore_entire_launch_efs.md).
2. [Select a restore point](aws_restore_entire_point_efs.md).
3. [Specify account for restore](aws_restore_entire_account_efs.md).
4. [Choose a restore mode](aws_restore_entire_mode_efs.md).
5. [Enable encryption for the restored file system](aws_restore_entire_encryption_efs.md).
6. [Specify file system settings](aws_restore_entire_type_efs.md).
7. [Configure network settings](aws_restore_entire_network_efs.md).
8. [Specify a restore reason](aws_restore_entire_reason_efs.md).
9. [Finish working with the wizard](aws_restore_entire_finish_efs.md).

How File System Restore Works

To restore an EFS file system from a backup, Veeam Data Cloud for AWS performs the following steps using [native AWS capabilities](https://docs.aws.amazon.com/aws-backup/latest/devguide/restoring-efs.html):

1. Creates a file system in the specified location.
2. Modifies the configuration setting values of the created EFS file system.
3. Restores backed-up files and folders to the restored file system.

|  |
| --- |
| Important |
| Veeam Data Cloud for AWS supports restoring EFS file systems only to the same AWS accounts to which the source file system belong. |

