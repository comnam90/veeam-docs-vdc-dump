---
title: "How Backup Works"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_hiw_ec2.html"
last_updated: "3/30/2026"
product_version: ""
---

# How Backup Works


Veeam Data Cloud for AWS performs EC2 backup in the following way:

1. Veeam Data Cloud for AWS assumes an IAM role that is created during [deployment of the CloudFormation template](aws_tenant_connection.md) in the customer AWS account.
2. Veeam Data Cloud for AWS uses [EBS direct APIs](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-accessing-snapshot.html) to create EBS snapshots of the volumes attached to the processed EC2 instance.

The snapshots are assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Data Cloud for AWS to identify and manage the related EBS snapshots, use them to perform restore operations, and treat them as a single unit — a cloud-native snapshot stored in the customer AWS account.

1. To create image-level backups, Veeam Data Cloud for AWS reads data directly from the EBS snapshots and transfers the data to a Veeam Data Cloud backup repository, where the data is stored in the native Veeam format.

|  |
| --- |
| Note |
| Due to per-account quotas defined by the Amazon EBS direct APIs, backup throughput can be restricted. When Veeam Data Cloud for AWS reads snapshot data, it sends up to 500 GetSnapshotBlock requests per second for each backup operation. As a result, Veeam Data Cloud for AWS can process only a limited number of EC2 instances concurrently.  For more information on the maximum number of GetSnapshotBlock requests allowed per account, see [AWS documentation](https://docs.aws.amazon.com/general/latest/gr/ebs-service.html#limits_ebs). To learn how to request a quota increase, see [AWS documentation](https://docs.aws.amazon.com/servicequotas/latest/userguide/request-quota-increase.html). |

Related Topics

* [Snapshot Chain](aws_snapshot_chain_ec2.md)

* [Backup Chain](aws_backup_chain_ec2.md)

