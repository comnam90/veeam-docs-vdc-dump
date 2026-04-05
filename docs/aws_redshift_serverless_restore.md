---
title: "Redshift Serverless Restore"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_redshift_serverless_restore.html"
last_updated: "3/30/2026"
product_version: ""
---

# Redshift Serverless Restore


In case of a disaster, you can restore a Redshift Serverless namespace from a cloud-native backup. Veeam Data Cloud for AWS allows you to restore only one Redshift Serverless namespace at a time to the original, any existing or a new namespace.

To restore a protected Redshift Serverless namespace, do the following:

1. [Launch the Redshift Serverless Restore wizard](aws_restore_launch_redshift_serverless.md).
2. [Select a restore point](restore_point_redshift_serverless.md).
3. [Specify account for restore](aws_restore_account_redshift_serverless.md).
4. [Choose a restore mode](aws_restore_mode_redshift_serverless.md).
5. [Configure workgroup settings](aws_restore_redshift_serverless_workgroup.md).
6. [Configure namespace settings](aws_restore_redshift_serverless_namespace.md).
7. [Specify a restore reason](aws_restore_reason_redshift_serverless.md).
8. [Finish working with the wizard](aws_restore_finish_redshift_serverless.md).

How Redshift Serverless Restore Works

To restore a Redshift Serverless namespace from a cloud-native backup, Veeam Data Cloud for AWS performs the following steps using [native AWS capabilities](https://docs.aws.amazon.com/redshift/latest/mgmt/serverless-snapshot-restore.html):

1. [Applies only if you perform restore to a new namespace] Creates a workgroup with the settings of a source workgoup or with custom settings in the region where the source namespace resides.
2. [Applies only if you perform restore to a new namespace] Creates a namespace with the settings of a source namespace or with custom settings in the region where the source namespace resides.
3. Restores backed-up database objects and users to the restored Redshift Serverless namespace.

|  |
| --- |
| Important |
| * Veeam Data Cloud for AWS supports restoring Redshift Serverless namespaces only to the same AWS accounts to which the source namespaces belong and to the same AWS Regions where the source namespaces reside.  * Veeam Data Cloud for AWS supports restoring only those Redshift Serverless namespace properties listed in section [Redshift Serverless Backup](aws_backup_hiw_redshift_serverless.md#properties).  * Veeam Data Cloud for AWS does not support restoring Amazon Redshift Serverless namespaces to provisioned clusters. * Veeam Data Cloud for AWS does not support restoring tables of Amazon Redshift Serverless namespaces. |

