---
title: "Performing EC2 Instance Restore"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_restore_ec2_entire.html"
last_updated: "3/30/2026"
product_version: ""
---

# Performing EC2 Instance Restore


In case of a disaster, you can restore an entire EC2 instance from a cloud-native snapshot or image-level backup. Veeam Data Cloud for AWS allows you to restore one or more EC2 instances at a time, to the original location or to a new location.

To restore a protected EC2 instance, do the following:

1. [Launch the Instance Restore wizard](aws_restore_ec2_entire_launch.md).
2. [Select a restore point](aws_restore_ec2_entire_restore_point.md).
3. [Select an account for restore](aws_restore_ec2_entire_mode.md).
4. [Choose a restore mode](aws_restore_entire_mode.md).
5. [Enable encryption for EBS volumes](aws_restore_entire_encryption.md).
6. [Configure instance settings](aws_restore_ec2_entire_type.md).
7. [Enable encryption for EBS volumes](aws_restore_entire_encryption.md).
8. [Configure network settings](aws_restore_ec2_entire_network.md).
9. [Specify a restore reason](aws_restore_ec2_entire_reason.md).
10. [Finish working with the wizard](aws_restore_ec2_entire_finish.md).

How Instance Restore Works

To restore EC2 instances from cloud-native snapshots, Veeam Data Cloud for AWS uses [native AWS capabilities](https://docs.aws.amazon.com/prescriptive-guidance/latest/backup-recovery/restore.html). To restore EC2 instances from image-level backups, Veeam Data Cloud for AWS restores instance data and recreates the EC2 instances in the original or a new location.

|  |
| --- |
| Important |
| Before you start the restore operation, check the limitations and prerequisites described in section [Before You Begin](aws_restore_ec2_entire_before_you_begin.md). |

