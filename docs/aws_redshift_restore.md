---
title: "Redshift Clusters Restore"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_redshift_restore.html"
last_updated: "3/30/2026"
product_version: ""
---

# Redshift Clusters Restore


In case of a disaster, you can restore a Redshift cluster from a cloud-native backup. Veeam Data Cloud for AWS allows you to restore one or more Redshift clusters at a time to the original location, with the source or different settings.

To restore a protected Redshift cluster, do the following:

1. [Launch the Redshift Restore wizard](aws_restore_launch_redshift.md).
2. [Select a restore point](aws_restore_point_redshift.md).
3. [Specify account settings for restore](aws_restore_account_redshift.md).
4. [Choose a restore mode](aws_restore_mode_redshift.md).
5. [Enable encryption for the restored cluster](aws_restore_encryption_redshift.md).
6. [Configure Redshift cluster settings](aws_restore_redshift_settings.md).
7. [Configure network settings](aws_restore_redshift_networks.md).
8. [Specify a restore reason](aws_restore_reason_redshift.md).
9. [Finish working with the wizard](aws_restore_finish_redshift.md).

How Redshift Clusters Restore Works

To restore a Redshift cluster from a backup, Veeam Data Cloud for AWS performs the following steps using [native AWS capabilities](https://docs.aws.amazon.com/aws-backup/latest/devguide/redshift-restores.html):

1. Creates a cluster in the specified location.
2. Modifies the configuration setting values of the created Redshift cluster.
3. Restores backed-up databases to the restored Redshift clusters.

|  |
| --- |
| Important |
| * Veeam Data Cloud for AWS supports restoring Redshift clusters only to the same AWS accounts to which the source clusters belong and to the same AWS Regions where the source clusters resides.  * Veeam Data Cloud for AWS supports restoring only those Redshift cluster properties that are described in section [Redshift Clusters Backup](aws_backup_hiw_redshift.md#properties).  * Veeam Data Cloud for AWS does not support restoring Amazon Redshift clusters with the Multi-AZ deployment. These clusters will be restored as clusters with the Single-AZ deployment. |

