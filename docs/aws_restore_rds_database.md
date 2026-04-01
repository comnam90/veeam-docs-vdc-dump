---
title: "Performing RDS Database Restore"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_restore_rds_database.html"
last_updated: "3/30/2026"
product_version: ""
---

# Performing RDS Database Restore


In case of a disaster, you can restore corrupted databases of Microsoft SQL Server and PostgreSQL DB instances from an image-level backup. Veeam Data Cloud for AWS allows you to restore one or more databases of a single DB instance at a time, to the original location only.

To restore databases of a protected DB instance, do the following:

1. [Launch the Database Restore wizard](aws_restore_rds_database_launch.md).
2. [Select databases](aws_restore_rds_database_point.md).
3. [Specify account settings for restore](aws_restore_rds_database_account.md).
4. [Configure target instance settings](aws_restore_rds_database_settings.md).
5. [Specify a restore reason](aws_restore_rds_database_reason.md).
6. [Finish working with the wizard](aws_restore_rds_database_finish.md).

How Database Restore Works

To restore databases of Microsoft SQL Server and PostgreSQL DB instances from an image-level backup, Veeam Data Cloud for AWS performs the following steps:

1. [Applies only to Microsoft SQL Server DB instances] Reads data from the backup file stored in the target backup repository, transfers the data to a temporary Amazon S3 bucket in the same AWS Region in which the source DB instance resides and stores it in the native SQL Server backup format. Then, uses native AWS capabilities to restore the SQL Server databases to the specified DB instance.
2. [Applies only to PostgreSQL DB instances] Retrieves dumps, triggers and stored procedures from the backup file stored in the target backup repository. Then, uses PostgreSQL capabilities to restore the PostgreSQL databases to the specified DB instance.
3. [Applies only to Microsoft SQL Server DB instances] Removes the temporary Amazon S3 bucket from AWS if it is not currently used by any data recovery operation.

|  |
| --- |
| Important |
| Before you start the restore operation, check the limitations and prerequisites described in [Considerations and Limitations](aws_limitations.md#rds_restore). |

