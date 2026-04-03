---
title: "Backup Chain"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_chain_ec2.html"
last_updated: "2/13/2026"
product_version: ""
---

# Backup Chain


When producing image-level backups for an EC2 backup policy, Veeam Data Cloud for AWS creates a new backup in a backup repository during every backup session according to the backup policy schedule. A sequence of backups created during a set of backup sessions makes up a backup chain.

The backup chain includes backups of the following types:

* Full — a full backup stores a copy of the full EC2 image.
* Incremental — incremental backups store incremental changes of EC2 images.

To create a backup chain for an EC2 instance protected by a backup policy, Veeam Data Cloud for AWS implements the forever forward incremental backup method:

1. During the first backup session, Veeam Data Cloud for AWS copies the full EC2 image and creates a full backup in the backup repository. The full backup becomes a starting point in the backup chain.
2. During subsequent backup sessions, Veeam Data Cloud for AWS copies only those data blocks that have changed since the previous backup session, and stores these data blocks to incremental backups in the backup repository. The content of each incremental backup depends on the content of the full backup and the preceding incremental backups in the backup chain.

Full and incremental backups act as restore points for backed-up EC2 instances that let you roll back instance data to the necessary state. To recover an EC2 instance to a specific point in time, the chain of backups created for the instance must contain a full backup and a set of incremental backups dependent on the full backup.

Related Topics

* [Changed Block Tracking](cbt.md)
* [EC2 Backup Retention](aws_retention_backup_ec2.md)

