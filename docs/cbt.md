---
title: "Changed Block Tracking"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/cbt.html"
last_updated: "4/27/2026"
product_version: ""
---

# Changed Block Tracking


The changed block tracking (CBT) mechanism allows Veeam Data Cloud for AWS to reduce the amount of data read from processed EBS volumes, and to increase the speed and efficiency of incremental backups:

* During a full backup session, Veeam Data Cloud for AWS reads only written data blocks, while unallocated data blocks are filtered out.
* During an incremental backup session, Veeam Data Cloud for AWS reads only those data blocks that have changed since the previous backup session.

To detect unallocated and changed data blocks, CBT relies on [EBS Direct APIs](https://docs.aws.amazon.com/ebs/latest/APIReference/Welcome.html).

1. During the first (full) backup session, AWS [creates a cloud-native snapshot](aws_backup_hiw_ec2.md#step1) of an EC2 instance. To do that, AWS sends API requests to access the content of the snapshot and to detect unallocated data blocks.
2. During subsequent sessions, new cloud-native snapshots are created. AWS sends API requests to access and to compare the content of the snapshot created during the previous backup session and the snapshot created during the current backup session. This allows AWS to detect data blocks that have changed since the previous backup session.

Limitations for Changed Block Tracking

Veeam Data Cloud for AWS cannot use CBT for EC2 instances that reside in AWS Regions where EBS Direct APIs are not available.

If CBT cannot be used, Veeam Data Cloud for AWS reads the whole content of processed EBS volumes and compares it with backed-up data that already exists in the backup repository. In this case, it may take Veeam Data Cloud for AWS more time to create incremental backups.

