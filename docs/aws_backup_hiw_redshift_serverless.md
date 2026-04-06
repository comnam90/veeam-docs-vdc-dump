---
title: "How Backup Works"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_hiw_redshift_serverless.html"
last_updated: "3/30/2026"
product_version: ""
---

# How Backup Works


Veeam Data Cloud for AWS uses the [Amazon Redshift Serverless service](https://docs.aws.amazon.com/redshift/latest/mgmt/serverless-snapshots-recovery-points.html) to create a cloud-native backup of a Redshift Serverless namespace, and saves this backup in the same AWS Region in which the source namespace resides. The backup is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Data Cloud for AWS identify the related namespace backup.

Supported Redshift Serverless Properties

Veeam Data Cloud for AWS allows you to back up and restore the following Redshift Serverless properties:

Supported Redshift Serverless Properties

| Property | Description | Ability to Change Property During Restore to New Location |
| Namespace name | Name of a Redshift Serverless namespace. | Yes |
| Workgroup name | Name of a workgroup associated with the Redshift Serverless namespace. | Yes |
| Base capacity and maximum capacity | Basic and maximum amount of compute resources allocated to the workgroup. | Yes |
| Associated IAM roles | List of IAM roles associated with the Redshift Serverless namespace. | Yes |
| Default role ARN | ARN of the default IAM role associated with the Redshift Serverless namespace. | Yes |
| Admin password | Defines whether the admin password is managed by AWS Secrets Manager. | * Yes (if the admin password is entered manually or generated automatically by Amazon Redshift) * No (if the admin password is managed by AWS Secrets Manager) |
| Secret Manager KMS key ID | ID of the custom KMS key used to encrypt the secret. | Yes |
| VPC | VPC where the Redshift Serverless namespace is deployed. | Yes |
| Subnets | Subnet associated with the Redshift Serverless namespace. | Yes |
| Security group | Security groups associated with the Redshift Serverless namespace. | Yes |
| Public access | Defines whether the Redshift Serverless namespace is accessible outside the VPC in which the namespace is deployed. | Yes |
| Enhanced VPC routing | Defines whether network traffic is routed between the Redshift Serverless namespace and the data repositories through a Redshift-managed VPC endpoint. | No |
| Database name | Name of the initial database in the Redshift Serverless environment. | No |
| Database port | Port used to access the Redshift Serverless namespace. | Yes |
| Encryption key | AWS KMS key that is used to encrypt the Redshift Serverless namespace data. | Yes |
| Tags | User-defined labels assigned to the Redshift Serverless namespace. | No |

|  |
| --- |
| Important |
| Veeam Data Cloud for AWS does not support the following:   * Audit logging for Amazon Redshift Serverless * Configured resource policies, automatically optimized price-performance targets, backup copy settings and Redshift-managed VPC endpoints  * Elastic IP assigned to the network interfaces of Redshift Serverless namespaces |

Related Topics

* [Backup Chain](aws_backup_chain_redshift_serverless.md)
* [Redshift Serverless Backup Retention](aws_retention_backup_redshift_serverless.md)

