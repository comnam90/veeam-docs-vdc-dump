---
title: "Backup Chain"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_chain_efs.html"
last_updated: "3/30/2026"
product_version: ""
---

# Backup Chain


During every backup session, Veeam Data Cloud for AWS creates a cloud-native backup for each EFS file system added to the backup policy. To create the backup, Veeam Data Cloud for AWS uses the [AWS Backup service](https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html).

A sequence of cloud-native backups created during a set of backup sessions makes up a backup chain. Veeam Data Cloud for AWS creates the backup chain in the following way:

1. During the first backup session, Veeam Data Cloud for AWS creates a backup that contains all EFS file system data and saves it in the selected backup vault of the AWS Region where the processed file system resides. This backup becomes a starting point in the backup chain.

The creation of the first backup may take significant time to complete since Veeam Data Cloud for AWS copies the whole image of the EFS file system.

1. During subsequent backup sessions, Veeam Data Cloud for AWS creates backups that contain only those data blocks (files and directories) that have changed since the previous backup session.

The creation of subsequent backups typically takes less time to complete, compared to the first backup in the chain. Note, however, that the completion time still depends on the amount of processed data.

Each EFS backup in the backup chain contains encrypted metadata. Metadata stores information about the protected file system, the backup policy that created the backup, and the date, time and applied retention settings. Veeam Data Cloud for AWS uses metadata to identify outdated backups, to load the configuration of source file systems during recovery operations, and so on.

EFS backups act as independent restore points for backed-up file systems. If you remove any backup, it will not break the EFS backup chain — you will still be able to roll back file system data to any existing restore point.

Related Topics

[EFS Backup Retention](aws_retention_backup_efs.md)

