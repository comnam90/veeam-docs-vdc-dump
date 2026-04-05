---
title: "Backup Chain"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_chain_redshift_serverless.html"
last_updated: "3/30/2026"
product_version: ""
---

# Backup Chain


During every backup session, Veeam Data Cloud for AWS creates a new cloud-native backup for each Redshift Serverless namespace added to the backup policy. To create the backup, Veeam Data Cloud for AWS uses the [Amazon Redshift Serverless service](https://docs.aws.amazon.com/redshift/latest/mgmt/serverless-snapshots-recovery-points.html). A sequence of cloud-native backups created during a set of backup sessions makes up a backup chain.

Each Redshift Serverless backup in the backup chain contains encrypted metadata. Metadata stores information about the protected namespace and its associated workgroup, the backup policy that created the backup, and the date, time and applied retention settings. Veeam Data Cloud for AWS uses metadata to identify outdated backups, to load the configuration of source namespace during recovery operations, and so on.

Redshift Serverless backups act as independent restore points for backed-up namespaces. If you remove any backup, it will not break the Redshift Serverless backup chain — you will still be able to roll back namespace data to any existing restore point.

Related Topics

[Redshift Serverless Backup Retention](aws_retention_backup_redshift_serverless.md)

