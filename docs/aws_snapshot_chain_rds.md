---
title: "Snapshot Chain"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_snapshot_chain_rds.html"
last_updated: "3/30/2026"
product_version: ""
---

# Snapshot Chain


During every backup session, Veeam Data Cloud for AWS creates a cloud-native snapshot for each instance added to the backup policy. The cloud-native snapshot is taken using native AWS capabilities.

A sequence of cloud-native snapshots created during a set of backup sessions makes up a snapshot chain. Veeam Data Cloud for AWS creates the snapshot chain in the following way:

1. During the first backup session, Veeam Data Cloud for AWS creates a snapshot that contains all instance data and saves it in the AWS Region where the processed instance resides. This snapshot becomes a starting point in the snapshot chain.

The creation of the first snapshot may take significant time to complete since Veeam Data Cloud for AWS copies the whole image of the instance.

1. During subsequent backup sessions, Veeam Data Cloud for AWS creates snapshots that contain only those data blocks that have changed since the previous backup session.

The creation of subsequent snapshots typically takes less time to complete, compared to the first snapshot in the chain. Note, however, that the completion time still depends on the amount of data being processed.

For more information on how incremental snapshots work, see [AWS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ManagingManualBackups.html).

Each cloud-native snapshot in the snapshot chain contains encrypted metadata. Metadata stores information about the protected instance and the backup policy that created the snapshot. Veeam Data Cloud for AWS uses metadata to identify snapshots created by the Veeam backup service, to detect outdated snapshots, to load the configuration of source instances during recovery operations, and so on.

Cloud-native snapshots act as independent restore points for backed-up instances. If you remove any snapshot, it will not break the snapshot chain — you will still be able to roll back instance data to any existing restore point.

Related Topics

[RDS Snapshot Retention](aws_retention_snapshots_rds.md)

