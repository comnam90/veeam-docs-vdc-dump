---
title: "Backup Chain"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_chain_rds.html"
last_updated: "3/30/2026"
product_version: ""
---

# Backup Chain


The forever forward incremental backup method is not implemented for DB instances — during every backup session Veeam Data Cloud for AWS creates a full backup in the regular backup chain.

Each RDS backup in the backup chain contains encrypted metadata that stores information about the protected DB instance, the backup policy that created the backup, as well as the date, time and configured retention settings. Veeam Data Cloud for AWS uses metadata to identify outdated backups, to retrieve information on the source instance configuration during recovery operations, and so on.

RDS backups act as independent restore points for backed-up DB instances. If you remove any backup, it will not break the backup chain — you will still be able to roll back data to any existing restore point.

Related Topics

[RDS Backup Retention](aws_retention_backup_rds.md)

