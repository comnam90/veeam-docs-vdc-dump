---
title: "Backup Chain"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_chain_redshift.html"
last_updated: "3/30/2026"
product_version: ""
---

# Backup Chain


During every backup session, Veeam Data Cloud for AWS creates a new cloud-native backup for each Redshift cluster added to the backup policy. To create the backup, Veeam Data Cloud for AWS uses the [AWS Backup service](https://docs.aws.amazon.com/redshift/latest/mgmt/managing-aws-backup.html). A sequence of cloud-native backups created during a set of backup sessions makes up a backup chain.

Each Redshift backup in the backup chain contains encrypted metadata. Metadata stores information about the protected cluster, the backup policy that created the backup, and the date, time and applied retention settings. Veeam Data Cloud for AWS uses metadata to identify outdated backups, to load the configuration of source cluster during recovery operations, and so on.

|  |
| --- |
| Note |
| Due to [AWS Backup service limitations](https://docs.aws.amazon.com/aws-backup/latest/devguide/backup-feature-availability.html#features-by-resource), during every backup session, Veeam Data Cloud for AWS creates a full backup in the regular backup chain. |

Redshift backups act as independent restore points for backed-up clusters. If you remove any backup, it will not break the Redshift backup chain — you will still be able to roll back cluster data to any existing restore point.

Related Topics

[Redshift Clusters Backup Retention](aws_retention_backup_redshift.md)

