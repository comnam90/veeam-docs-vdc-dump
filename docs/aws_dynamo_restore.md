---
title: "DynamoDB Restore"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_dynamo_restore.html"
last_updated: "3/30/2026"
product_version: ""
---

# DynamoDB Restore


In case of a disaster, you can restore a DynamoDB table from a cloud-native backup. Veeam Data Cloud for AWS allows you to restore one or more DynamoDB tables at a time, to the original location or to a new location.

To restore a protected DynamoDB table, do the following:

1. [Launch the DynamoDB Restore wizard](restore_launch_dynamo.md).
2. [Select a restore point](restore_point_dynamo.md).
3. [Specify account for restore](restore_account_dynamo.md).
4. [Choose a restore mode](restore_mode_dynamo.md).
5. [Enable encryption for the restored table](restore_encryption_dynamo.md).
6. [Configure table settings](restore_type_dynamo.md).
7. [Choose capacity mode for the restored table](restore_capacity_mode_dynamo.md).
8. [Specify a restore reason](restore_reason_dynamo.md).
9. [Finish working with the wizard](restore_finish_dynamo.md).

How DynamoDB Restore Works

To restore a DynamoDB table from a backup, Veeam Data Cloud for AWS performs the following steps using [native AWS capabilities](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Restore.TutorialAWS.html):

1. Creates a table in the specified location.
2. Restores backed-up data (items and attributes) to the restored table.
3. Modifies the configuration setting values of the created DynamoDB table.

|  |
| --- |
| Important |
| * Veeam Data Cloud for AWS supports restoring DynamoDB tables only to the same AWS account to which the source tables belongs.  * Veeam Data Cloud for AWS supports restoring only those DynamoDB table properties that are described in section [DynamoDB Backup](aws_backup_hiw_dynamo.md#table_parameters). |

