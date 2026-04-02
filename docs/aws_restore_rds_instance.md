---
title: "Performing RDS Instance Restore"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_restore_rds_instance.html"
last_updated: "3/30/2026"
product_version: ""
---

# Performing RDS Instance Restore


In case of a disaster, you can restore a DB instance or an Aurora DB cluster from a cloud-native snapshot. Veeam Data Cloud for AWS allows you to restore one or more RDS resources at a time, to the original location or to a new location.

How to Perform RDS Restore

To restore a protected RDS resource, do the following:

1. [Launch the RDS Restore wizard](aws_restore_rds_launch.md).
2. [Select a restore point](aws_restore_rds_point.md).
3. [Specify account settings for restore](aws_restore_rds_account.md).
4. [Choose a restore mode](aws_restore_rds_mode.md).
5. [Enable encryption](aws_restore_rds_encryption.md).
6. [Configure RDS resource settings](aws_restore_rds_settings.md).
7. [Configure network settings](aws_restore_rds_network.md).
8. [Specify a restore reason](aws_restore_rds_reason.md).
9. [Finish working with the wizard](aws_restore_rds_finish.md).

How RDS Restore Works

To restore a DB instance from a snapshot, Veeam Data Cloud for AWS uses [native AWS capabilities](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Tutorials.RestoringFromSnapshot.html) to restore database data and recreate the DB instance in the original or a new location.

To restore an Aurora DB cluster from a snapshot, Veeam Data Cloud for AWS uses [native AWS capabilities](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/tut-restore-cluster.console.html) to restore database data and recreate the Aurora DB cluster and its DB instances in the original or a new location.

|  |
| --- |
| Important |
| Before you start the restore operation, check the limitations and prerequisites described in [Considerations and Limitations](aws_limitations.md#rds_restore). |

