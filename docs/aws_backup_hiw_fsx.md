---
title: "How Backup Works"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_hiw_fsx.html"
last_updated: "3/30/2026"
product_version: ""
---

# How Backup Works


Veeam Data Cloud for AWS uses the [AWS Backup service](https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html) to create a cloud-native backup of the file system, and saves this backup to a backup vault in the same AWS Region in which the source file system resides. The backup is assigned AWS tags upon creation. Keys and values of AWS tags contain encrypted metadata that helps Veeam Data Cloud for AWS identify the related FSx file system backup.

Supported FSx File System Properties

Veeam Data Cloud for AWS allows you to back up and restore the following file system properties:

Supported FSx File System Properties

| Property | Description | Ability to Change Property During Restore to New Location |
| File system name | Name of an FSx file system. | Yes |
| Deployment type | Deployment type of the FSx file system. | No |
| Storage type | Storage type of the FSx file system. | No |
| Storage capacity | Storage capacity of the FSx file system. | No |
| Throughput capacity | Sustained speed at which file servers hosting the FSx file system can process data. | No |
| Throughput per unit of storage | Read/write throughput for each 1 TiB of provisioned storage, in MB/s/TiB. | No |
| IOPS | Maximum number of input/output operations per second that the FSx file system can process. | No |
| Provisioned Metadata IOPS [Applies only to FSx for Lustre file systems] | Maximum rate of metadata operations supported by the FSx file system. | No |
| Volume properties [Applies only to FSx for OpenZFS file systems] | Properties of the FSx file system configured to manage its root volume storage. | No |
| Provisioned SSD IOPS [Applies only to FSx for Windows File Server file systems] | Additional IOPS provisioned to the FSx file system. | No |
| Data compression type [Applies only to FSx for Lustre file systems] | Defines whether the FSx file system data is compressed. | No |
| Windows authentication [Applies only to FSx for Windows File Server file systems] | Type of an Microsoft Active Directory to which the FSx file system is joined. | No |
| Active Directory domain name [Applies only to FSx for Windows File Server file systems] | Domain name of the Microsoft AD to which the FSx file system is joined. | Yes |
| DNS server IP addresses [Applies only to FSx for Windows File Server file systems] | IPv4 addresses of DNS servers configured for the domain. | Yes |
| Service account user name [Applies only to FSx for Windows File Server file systems] | Name of a service account that has access to the FSx file system. | Yes |
| Organizational unit [Applies only to FSx for Windows File Server file systems] | Path name of an organizational unit in which the FSx file system is connected. | Yes |
| System administrators group [Applies only to FSx for Windows File Server file systems] | Name of an Active Directory group that has privileges to manage the FSx file system. | Yes |
| DNS Aliases [Applies only to FSx for Windows File Server file systems] | Additional names that are used to access FSx file system data. | No |
| Root squash configuration [Applies only to FSx for Lustre file systems] | Additional layer of access control configured for the FSx file system. | No |
| Elastic Fabric Adapter (EFA) [Applies only to FSx for Lustre file systems] | EFA is a high-performance network interface to increase the performance of the FSx file system. | No |
| Tags | File systems identifiers. | No |
| VPC | VPC to which the FSx file system is connected. | Yes |
| Subnet | Subnet in which the elastic network interface of the FSx file system resides. | Yes |
| Preferred and standby subnet [Applies only to FSx for Windows File Server and FSx for OpenZFS file systems file systems] | Subnets in which the network interfaces of the primary and standby file servers reside. | Yes |
| Security groups | Security groups associated with the FSx file system. | Yes |
| Route tables [Applies only to FSx for OpenZFS file systems file systems] | Route tables associated with the subnet of the VPC to which the FSx file system is connected. | Yes |
| Encryption key | AWS KMS key that is used to encrypt the FSx file system data. | Yes |
| Backup and maintenance | Defines whether daily automatic backup is scheduled and whether a weekly maintenance window is configured for the FSx file system. | No |

|  |
| --- |
| Important |
| Veeam Data Cloud for AWS does not support restore of the following items:   * [For FSx for OpenZFS file systems] Copy tags to snapshots from the root volume and copy tags to backups settings * [For FSx for OpenZFS file systems with the Multi-AZ deployment type] Configured endpoint IP address ranges  * [For FSx for Windows File Server file systems] Copy tags to backups setting, file access auditing configurations and associated DNS aliases  * [For Amazon FSx for Lustre file systems] Copy tags to backups setting, CloudWatch logging configurations, and exceptions to root squash settings |

Required Ports

If you plan to protect FSx file systems, make sure that security groups associated with these file systems allow access to the following ports:

Required Ports

| File System Type | Protocol | Ports | Notes |
| Amazon FSx for Windows File Server | UPD | 53, 88, 123, 389, 464 | Requires inbound and outbound access. |
| TCP | 53, 88, 135, 389, 445, 464, 636, 3268, 3269, 5985, 9389, 49152-65535 |
| Amazon FSx for Lustre | TCP | 988, 1018-1023 | Requires inbound access. For more information on file system access control, see [AWS Documentation](https://docs.aws.amazon.com/fsx/latest/LustreGuide/limit-access-security-groups.html). |
| Amazon FSx for OpenZFS | TCP, UDP | 111, 2049, 20001-20003 | Requires inbound access. |

To learn how to authorize access to security groups, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/security-group-rules.html).

Related Topics

* [Backup Chain](aws_backup_chain_fsx.md)
* [FSx Backup Retention](aws_retention_backup_fsx.md)

