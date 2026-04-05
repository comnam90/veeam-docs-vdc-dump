---
title: "How Backup Works"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_hiw_dynamo.html"
last_updated: "3/30/2026"
product_version: ""
---

# How Backup Works


Veeam Data Cloud for AWS uses the [AWS Backup service](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/CreateBackupAWS.html) to create a cloud-native backup of a DynamoDB table and saves this backup to a backup vault in the same AWS Region in which the source table resides. The backup is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Data Cloud for AWS identify the related table backup.

Supported DynamoDB Table Properties

Veeam Data Cloud for AWS allows you to back up and restore the following table properties:

Supported DynamoDB Table Properties

| Property | Description | Ability to Change Property During Restore to New Location |
| Table name | Name of a DynamoDB table. | Yes |
| Partition key | First attribute of the primary key. | No |
| Sort key | Second attribute of the primary key. | No |
| Global secondary index (GSI) and local secondary index (LSI) | Additional indexes that provide efficient access to the table data. | No |
| Table class | Defines how often the table data is accessed. | Yes |
| Capacity mode | Defines how read/write operations are charged and managed. | Yes |
| Provisioned read/write capacity units | Read/write throughput for the table and its indexes. | Yes |
| Maximum throughput capacity | Maximum read/write throughput for the on-demand table. | No |
| Tags | Table identifiers. | No |
| Deletion protection | Defines whether the table is protected against accidental deletion. | Yes |
| Server-side encryption | Defines the key used for data-at-rest encryption. | Yes |
| Point-in-time recovery (PITR) | Defines whether the table data can be restored to any point in time during the last 35 days. | Yes |
| DynamoDB Time to Live (TTL) | Attribute name with a timestamp that determines when the table items are no longer needed. | No |

|  |
| --- |
| Important |
| Veeam Data Cloud for AWS does not support the following:   * CloudWatch alarms * Resource-based policies * DynamoDB global table feature * Adjusted provisioned throughput capacity provided by Amazon DynamoDB auto scaling * Item-level modifications captured by Amazon Kinesis Data Streams * Time-ordered sequences of item-level modifications captured by Amazon DynamoDB Streams * Restore of the configured CloudWatch Contributor Insights diagnostic tool |

Related Topics

* [Backup Chain](aws_backup_chain_dynamo.md)
* [DynamoDB Backup Retention](aws_retention_backup_dynamo.md)

