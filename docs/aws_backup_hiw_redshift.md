---
title: "How Backup Works"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_hiw_redshift.html"
last_updated: "3/30/2026"
product_version: ""
---

# How Backup Works


Veeam Data Cloud for AWS uses the [AWS Backup service](https://docs.aws.amazon.com/redshift/latest/mgmt/managing-aws-backup.html) to create a cloud-native backup of a Redshift cluster, and saves this backup to a backup vault in the same AWS Region in which the source cluster resides. The backup is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Data Cloud for AWS identify the related cluster backup.

Supported Redshift Cluster Properties

Veeam Data Cloud for AWS allows you to back up and restore the following cluster properties:

Supported Redshift Cluster Properties

| Property | Description | Ability to Change Property During Restore to New Location |
| Cluster ID | Unique identifier of the Redshift cluster. | Yes |
| Node type | Type of the nodes for the Redshift cluster. | Yes |
| Number of nodes | Total number of compute nodes for the Redshift cluster. | Yes |
| Associated IAM roles | List of IAM roles associated with the Redshift cluster. | Yes |
| Default role ARN | ARN of the default IAM role associated with the Redshift cluster. | Yes |
| Admin password | Defines whether the admin password is managed by AWS Secrets Manager. | No |
| Secret Manager KMS key ID | ID of the custom KMS key used to encrypt the secret. | Yes |
| VPC | VPC to which the Redshift cluster is connected. | Yes |
| Subnet group | Subnet group in which the Redshift cluster is launched. | Yes |
| Availability Zone | Availability Zone where the Redshift cluster resides. | Yes |
| Public access | Defines whether the Redshift cluster is accessible outside the VPC to which the cluster is connected. | Yes |
| Enhanced VPC routing | Defines whether network traffic is routed between the Redshift cluster and the data repositories through a Redshift-managed VPC endpoint. | No |
| Port | Port used to access the Redshift cluster. | Yes |
| Parameter group | Parameter group associated with the Redshift cluster. | Yes |
| Cluster relocation | Defines whether the Redshift cluster can be moved to another Availability Zone. | No |
| Encryption key | AWS KMS key that is used to encrypt the Redshift cluster data. | Yes |
| Tags | User-defined labels assigned to the Redshift cluster. | No |
| Backup and maintenance | Defines whether daily automatic backup is scheduled and whether a weekly maintenance window is configured for the Redshift cluster. | No |

|  |
| --- |
| Important |
| Veeam Data Cloud for AWS does not support the following:   * Multi-AZ deployment mode of Redshift clusters * HSM encryption scheme of Redshift clusters  * Elastic IP assigned to the network interfaces of Redshift clusters |

Related Topics

* [Backup Chain](aws_backup_chain_redshift.md)
* [Redshift Clusters Backup Retention](aws_retention_backup_redshift.md)

