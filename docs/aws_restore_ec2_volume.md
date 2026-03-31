---
title: "Performing Volume Restore"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_restore_ec2_volume.html"
last_updated: "3/30/2026"
product_version: ""
---

# Performing Volume Restore


In case a disaster strikes, you can restore corrupted EBS volumes of an EC2 instance from a cloud-native snapshot or image-level backup. Veeam Data Cloud for AWS allows you to restore EBS volumes to the original location or to a new location.

To restore EBS volumes of a protected EC2 instance, do the following:

1. [Launch the Volume Restore wizard](aws_restore_ec2_entire_launch.md).
2. [Select a restore point](aws_restore_volume_restore_point.md).
3. [Select an account for restore](aws_restore_volume_account.md).
4. [Choose a restore mode](aws_restore_volume_mode.md).
5. [Enable encryption for EBS volumes](aws_restore_volume_encryption.md).
6. [Specify the restored EBS volume name](aws_restore_volume_name.md).
7. [Specify a restore reason](aws_restore_volume_reason.md).
8. [Finish working with the wizard](aws_restore_volume_finish.md).

How Volume-Level Restore Works

To restore EBS volumes from cloud-native snapshots, Veeam Data Cloud for AWS uses [native AWS capabilities](https://docs.aws.amazon.com/prescriptive-guidance/latest/backup-recovery/restore.html). To restore EBS volumes from image-level backups, Veeam Data Cloud for AWS restores volume data and recreates the EBS volumes in the original or a new location.

|  |
| --- |
| Important |
| Before you start the restore operation, check the limitations and prerequisites described in [Considerations and Limitations](aws_limitations.md#ec2_restore). |

