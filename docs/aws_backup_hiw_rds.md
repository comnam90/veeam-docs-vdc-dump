---
title: "How Backup Works"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_hiw_rds.html"
last_updated: "3/30/2026"
product_version: ""
---

# How Backup Works


Veeam Data Cloud for AWS performs RDS backup in the following way:

1. Veeam Data Cloud for AWS uses the Amazon RDS service to [create a storage volume snapshot](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateSnapshot.html) of the processed DB instance (that is, a DB snapshot) or of the processed Aurora DB cluster (that is, a DB cluster snapshot).

The snapshot is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Data Cloud for AWS identify the related snapshot. For the Aurora DB cluster metadata saved in AWS tags also contains information on every DB instance launched in the cluster.

1. [Applies only to PostgreSQL DB instances] Veeam Data Cloud for AWS leverages the Veeam technology to create image-level backups based on the created snapshots and transfers the backed-up data to a Veeam Data Cloud backup repository, where the data is stored it in the native Veeam format.
2. [Applies only to Microsoft SQL Server DB instances] Veeam Data Cloud for AWS uses the Amazon RDS service to [create a native backup of the SQL Server DB instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/SQLServer.Procedural.Importing.html), and saves this backup to a temporary Amazon S3 bucket in the same AWS Region in which the source DB instance resides. Then, reads data from the native SQL Server backup, transfers the data to a Veeam Data Cloud backup repository and stores it in the native Veeam format.

Related Topics

* [Snapshot Chain](aws_snapshot_chain_rds.md)
* [Backup Chain](aws_backup_chain_rds.md)

