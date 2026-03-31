---
title: "FSx Restore"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_fsx_restore.html"
last_updated: "3/30/2026"
product_version: ""
---

# FSx Restore


In case of a disaster, you can restore a FSx file system from a cloud-native backup. Veeam Data Cloud for AWS allows you to restore one or more file systems at a time, to the original location or to a new location.

To restore a protected FSx file system, do the following:

1. [Launch the FSx Restore wizard](aws_restore_launch_fsx.md).
2. [Select a restore point](aws_restore_point_fsx.md).
3. [Specify account for restore](aws_restore_account_fsx.md).
4. [Choose a restore mode](aws_restore_mode_fsx.md).
5. [Enable encryption for the restored table](aws_restore_encryption_fsx.md).
6. [Configure file system settings](aws_restore_general_fsx.md).
7. [Configure network settings](aws_restore_capacity_network_efs.md).
8. [Specify a restore reason](aws_restore_reason_fsx.md).
9. [Finish working with the wizard](aws_restore_finish_fsx.md).

How File System Restore Works

To restore an FSx file system from a backup, Veeam Data Cloud for AWS performs the following steps using [native AWS capabilities](https://docs.aws.amazon.com/aws-backup/latest/devguide/restoring-fsx.html):

1. Creates a file system in the specified location.
2. Modifies the configuration setting values of the created EFS file system.
3. Restores backed-up files and folders to the restored file system.

|  |
| --- |
| Important |
| * Veeam Data Cloud for AWS supports restoring FSx file systems only to the same AWS accounts to which the source file systems belong.  * Veeam Data Cloud for AWS supports restoring only those FSx file system properties that are described in section [FSx Backup](aws_backup_hiw_fsx.md#parameters).  * Veeam Data Cloud for AWS supports restoring Amazon FSx for Windows File Server file systems. However, before you start a restore operation, it is recommended that you use the Amazon FSx Active Directory Validation tool to check the connection between the file systems that you plan to restore and the Microsoft Active Directories to which these file systems will be joined. To learn how to use the validation tool, see [AWS Documentation](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/aws-ad-integration-fsxW.html). * Veeam Data Cloud for AWS does not support restoring Amazon FSx for Windows File Server file systems that use AWS Secrets Manager to store service account credentials when joined to a self-managed Microsoft Active Directory (AD). |

