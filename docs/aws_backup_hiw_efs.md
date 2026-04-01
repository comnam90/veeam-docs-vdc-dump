---
title: "How Backup Works"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_hiw_efs.html"
last_updated: "3/30/2026"
product_version: ""
---

# How Backup Works


Veeam Data Cloud for AWS uses the [AWS Backup service](https://docs.aws.amazon.com/efs/latest/ug/awsbackup.html) to create a cloud-native backup of the file system, and saves this backup to a backup vault in the same AWS Region in which the source file system resides. The backup is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Data Cloud for AWS identify the related EFS file system backup.

Related Topics

* [Backup Chain](aws_backup_chain_efs.md)
* [EFS Backup Retention](aws_retention_backup_efs.md)

