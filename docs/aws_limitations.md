---
title: "Considerations and Limitations"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_limitations.html"
last_updated: "3/9/2026"
product_version: ""
---

# Considerations and Limitations


Before you start using Veeam Data Cloud for AWS and protecting your AWS resources, keep in mind the following limitations and considerations.

Deployment

Veeam Data Cloud for AWS is available only in AWS Global and AWS GovCloud (US) regions.

Software

To access Veeam Data Cloud for AWS, use Microsoft Edge (Chromium only), Mozilla Firefox (latest version) or Google Chrome (latest version). Internet Explorer is not supported.

EC2 Backup

When protecting EC2 instances, consider the following:

* Veeam Data Cloud for AWS supports creating cloud-native snapshots and image-level backups for EC2 instances only to the same AWS accounts to which the source instances belong.

* Veeam Data Cloud for AWS protects only EC2 instances that run in VPCs. EC2-Classic instances are not supported. For more information, see [this Veeam KB article](https://www.veeam.com/kb3147).

When Veeam Data Cloud for AWS backs up EC2 instances with IPv6 addresses assigned, it does not save the addresses. That is why when you restore these instances, IP addresses are assigned according to the settings specified in AWS for the subnet to which the restored instances will be connected.

* Veeam Data Cloud for AWS may fail to create image-level backups of EC2 instances with [product codes](https://docs.aws.amazon.com/marketplace/latest/userguide/ami-getting-started.html#ami-product-codes) if the AMIs that were used to deploy the instances do not support the type of worker instances deployed for the backup operation.

* [Applies only to image-level backups and file-level recovery from cloud-native snapshots] Veeam Data Cloud for AWS does not support creating image-level backups and restoring EC2 instances with [product codes](https://docs.aws.amazon.com/marketplace/latest/userguide/ami-getting-started.html#ami-product-codes) that have vendor restrictions preventing root EBS volumes from being attached to worker instances as secondary volumes. To learn how Veeam Data Cloud for AWS performs EC2 backup, see [Protecting EC2 Instances](aws_backup_hiw_ec2.md).

* Veeam Data Cloud for AWS does not support creating cloud-native snapshots and image-level backups for arm64-based EC2 instances if these instances were deployed from AMIs containing [product codes](https://docs.aws.amazon.com/marketplace/latest/userguide/ami-getting-started.html#ami-product-codes).

* Veeam Data Cloud for AWS runs retention sessions for backup policies at 4:00 AM by default, according to the time zone set on the backup appliance.

RDS Backup

When protecting RDS resources, consider the following:

* Veeam Data Cloud for AWS supports creating cloud-native snapshots and image-level backups for RDS resources only to the same AWS accounts to which the source resources belong.

* Veeam Data Cloud for AWS supports creating image-level backups for Microsoft SQL Server and PostgreSQL DB instances only. However, the size of each database hosted on a protected Microsoft SQL Server DB instance must not exceed 5 TiB.
* Veeam Data Cloud for AWS supports image-level backup of PostgreSQL versions 17, 16, 15, 14, 13, and 12.
* Veeam Data Cloud for AWS does not support creating cloud-native snapshots for PostgreSQL DB clusters with Multi-AZ DB cluster deployment and IBM Db2 DB instances.
* Veeam Data Cloud for AWS does not support creating cloud-native snapshots for Aurora PostgreSQL Limitless Database clusters.
* Veeam Data Cloud for AWS does not support creating image-level backups for Microsoft SQL Server DB instances that host system databases only.
* Veeam Data Cloud for AWS does not support creating image-level backups for Aurora PostgreSQL clusters.

* [Applies only if you plan to back up Microsoft SQL Server DB instances] The SQLSERVER\_BACKUP\_RESTORE option must be added to the option group that is applied to each processed DB instance.

The IAM role that is associated with the SQLSERVER\_BACKUP\_RESTORE option must have the permissions required to access temporary Amazon S3 buckets. The IAM role must also have a trust relationship and a permissions policy attached to allow the Amazon RDS service to assume the role. For more information on the backup and restore option, see [AWS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Appendix.SQLServer.Options.BackupRestore.html#Appendix.SQLServer.Options.BackupRestore.Add).

* Veeam Data Cloud for AWS runs retention sessions at 4:00 AM by default, according to the time zone set on the backup appliance.

DynamoDB Backup

When protecting DynamoDB tables, consider the following:

* Veeam Data Cloud for AWS supports backup of only those DynamoDB table properties that are described in section [DynamoDB Backup](aws_backup_hiw_dynamo.md#table_parameters).

* Veeam Data Cloud for AWS supports creating cloud-native backups for DynamoDB tables only to the same AWS accounts to which the source tables belong.

For Veeam Data Cloud for AWS to be able to create cloud-native backups for DynamoDB tables, you must configure the AWS Backup settings to enable both the Opt-in service and the advanced features for Amazon DynamoDB backups. Otherwise, Veeam Data Cloud for AWS will automatically enable these settings for each AWS Region specified in the backup policy settings in your AWS account while performing backup operations. For more information on advanced DynamoDB backup, see [AWS Documentation](https://docs.aws.amazon.com/aws-backup/latest/devguide/advanced-ddb-backup.html).

* Veeam Data Cloud for AWS does not support storing cloud-native backups in [logically air-gapped vaults](https://docs.aws.amazon.com/aws-backup/latest/devguide/logicallyairgappedvault.html) and in backup vaults with the [AWS Backup Vault Lock](https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html) feature enabled.

* Veeam Data Cloud for AWS uses the [AWS Backup](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/backuprestore_HowItWorksAWS.html) service to create DynamoDB backups. The [DynamoDB backup](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/backuprestore_HowItWorks.html) service is not supported.

* Veeam Data Cloud for AWS runs retention sessions at 4:00 AM by default, according to the time zone set on the backup appliance.

Redshift Clusters Backup

When protecting Redshift clusters, consider the following:

* Veeam Data Cloud for AWS supports backup of only those Redshift cluster properties that are described in section [Redshift Clusters Backup](aws_backup_hiw_redshift.md#properties).
* Veeam Data Cloud for AWS supports creating cloud-native backups for Redshift clusters only to the same AWS accounts to which the source clusters belong and the same AWS Region where the source clusters reside.

For Veeam Data Cloud for AWS to be able to create cloud-native backups of Redshift clusters, you must enable the Opt-in service for the Redshift resource type in the AWS Backup settings. Otherwise, Veeam Data Cloud for AWS will automatically enable the service for each AWS Region specified in the backup policy settings in your AWS account while performing backup operations. For more information on considerations for using AWS Backup with Amazon Redshift, see [AWS Documentation](https://docs.aws.amazon.com/redshift/latest/mgmt/managing-aws-backup.html#managing-aws-backup-considerations).

* Veeam Data Cloud for AWS does not support storing cloud-native backups in [logically air-gapped vaults](https://docs.aws.amazon.com/aws-backup/latest/devguide/logicallyairgappedvault.html) and in backup vaults with the [AWS Backup Vault Lock](https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html) feature enabled.

* Veeam Data Cloud for AWS runs retention sessions at 4:00 AM by default, according to the time zone set on the backup appliance.

Redshift Serverless Backup

When protecting Redshift Serverless namespaces, consider the following:

* Veeam Data Cloud for AWS supports backup of only those Redshift Serverless properties that are described in section [Redshift Serverless Backup](aws_backup_hiw_redshift_serverless.md#properties).

* Veeam Data Cloud for AWS supports creating cloud-native backups for Redshift Serverless namespaces only to the same AWS accounts to which the source namespaces belong and the same AWS Region where the source namespaces reside.

* Make sure that workgroups are associated with Redshift Serverless namespaces that you plan to protect. Otherwise, the backup operation may fail to complete successfully.

* Veeam Data Cloud for AWS runs retention sessions at 4:00 AM by default, according to the time zone set on the backup appliance.

EFS Backup

When protecting EFS file systems, consider the following:

* Veeam Data Cloud for AWS supports creating cloud-native backups for EFS file systems only to the same AWS accounts to which the source file systems belong.

* Veeam Data Cloud for AWS does not support storing cloud-native backups in [logically air-gapped vaults](https://docs.aws.amazon.com/aws-backup/latest/devguide/logicallyairgappedvault.html) and in backup vaults with the [AWS Backup Vault Lock](https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html) feature enabled.

* Veeam Data Cloud for AWS runs retention sessions at 4:00 AM by default, according to the time zone set on the backup appliance.

FSx Backup

When protecting FSx file systems, consider the following:

* Veeam Data Cloud for AWS supports backup of only those FSx file system properties that are described in section [FSx Backup](aws_backup_hiw_fsx.md#parameters).

* Veeam Data Cloud for AWS supports creating cloud-native backups for FSx file systems only to the same AWS accounts to which the source file systems belong.

For Veeam Data Cloud for AWS to be able to create cloud-native backups for FSx file systems, you must enable the Opt-in service for the FSx resource type in the AWS Backup settings. Otherwise, Veeam Data Cloud for AWS will automatically enable the service for each AWS Region specified in the backup policy settings in your AWS account while performing backup operations.

* Veeam Data Cloud for AWS does not support creating cloud-native backups for Amazon FSx for NetApp ONTAP file systems. However, you can back up Amazon FSx for NetApp ONTAP file systems using the Veeam Backup & Replication console. For more information, see the Veeam Backup & Replication User Guide, section [Unstructured Data Backup](https://helpcenter.veeam.com/docs/vbr/userguide/unstructured_data_backup.html?ver=13).
* Veeam Data Cloud for AWS does not support creating cloud-native backups for Amazon FSx for Windows File Server file systems that use AWS Secrets Manager to store service account credentials when joined to a self-managed Microsoft Active Directory (AD).

* Veeam Data Cloud for AWS does not support storing cloud-native backups in [logically air-gapped vaults](https://docs.aws.amazon.com/aws-backup/latest/devguide/logicallyairgappedvault.html) and in backup vaults with the [AWS Backup Vault Lock](https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html) feature enabled.

* Veeam Data Cloud for AWS does not support creating cloud-native backups for Amazon FSx for Lustre file systems with the [Scratch deployment type](https://docs.aws.amazon.com/fsx/latest/LustreGuide/using-fsx-lustre.html?icmpid=docs_fsx_console#scratch-file-system).

* Veeam Data Cloud for AWS does not support creating cloud-native backups for Amazon FSx for Lustre with the [data repository association](https://docs.aws.amazon.com/fsx/latest/LustreGuide/fsx-data-repositories.html).

* Veeam Data Cloud for AWS does not support creating cloud-native backups for Amazon FSx for OpenZFS with the [Intelligent-Tiering storage class](https://docs.aws.amazon.com/fsx/latest/OpenZFSGuide/performance-intelligent-tiering.html).

* Veeam Data Cloud for AWS uses the [AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html) service to create FSx backups and backup copies. The AWS Backup service does not support creating backup copies of FSx backups stored in [Opt-in Regions](https://docs.aws.amazon.com/controltower/latest/userguide/opt-in-region-considerations.html).

* Veeam Data Cloud for AWS runs retention sessions at 4:00 AM by default, according to the time zone set on the backup appliance.

EC2 Restore

When restoring EC2 instances, consider the following:

* Veeam Data Cloud for AWS supports restoring EC2 instances only to the same AWS accounts to which the source instances belong.

* Veeam Data Cloud for AWS supports restoring EC2 instances from different types of restore points only to the original location.
* Veeam Data Cloud for AWS supports restoring EC2 instances from image-level backups only to the original location.

* When restoring multiple EC2 instances that have the same EBS volume attached, Veeam Data Cloud for AWS restores one volume per each instance and enables the Multi-Attach option for every restored volume. For more information on Amazon EBS Multi-Attach, see [AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volumes-multi.html).

* If you restore multiple EC2 instances that have the same EBS volume attached, Veeam Data Cloud for AWS creates a separate volume for each instance and enables the Multi-Attach option for all volumes. After the restore operation completes, you can manually delete extra EBS volumes in the AWS Management Console and attach the necessary volume to the instances.

For more information on Amazon EBS Multi-Attach, see [AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volumes-multi.html).

* [Applies only if you plan to restore EBS volumes] Veeam Data Cloud for AWS does not attach restored EBS volumes to any EC2 instances — the volumes are placed to the specified location as standalone EBS volumes.

* [Applies only if you plan to restore EC2 instances to a new location or with different settings] Veeam Data Cloud for AWS restores EC2 instances with a single network interface and assigns a new primary private IP address to each instance.

* [Applies only if you plan to restore EC2 instances to the original location] Veeam Data Cloud for AWS restores the instance and all network interfaces that were attached to the source EC2 instance. However, there are limitations regarding Elastic IP and private IP addresses. For more information, see [Performing EC2 Instance Restore](aws_restore_ec2_entire_before_you_begin.md).

* [Applies only if you plan to restore EC2 instances to the original location] If [stop protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-stop-protection.html) or [termination protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination) is enabled on an EC2 instance, Veeam Data Cloud for AWS will not be able to restore the instance and will raise an error notifying that you must disable stop protection or termination protection on the source instance.
* [Applies only if you plan to restore EC2 instances to the original location] Veeam Data Cloud for AWS does not support restoring EC2 instances if the source instances with termination protection and stop protection enabled still exist in AWS.

* Veeam Data Cloud for AWS does not support restore of IPv6 addresses, tags of Elastic IP addresses or prefixes assigned to Amazon EC2 network interfaces attached to EC2 instances.

RDS Restore

When restoring RDS resources, consider the following

* Veeam Data Cloud for AWS supports restoring RDS resources only to the same AWS accounts to which the source resources belong.

* When restoring Aurora DB clusters that are part of an Amazon Aurora global database, Veeam Data Cloud for AWS restores only the primary clusters in the primary AWS Region. Secondary clusters must be created manually in the AWS Management Console after the restore operation completes.

For more information on Amazon Aurora Global Database feature, see [AWS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database.html).

* When restoring Aurora DB clusters to a new location, Veeam Data Cloud for AWS creates only primary DB instances in the restored clusters. Additional writer DB instances (for Aurora multi-master clusters) or Aurora Replicas (for Aurora DB clusters with single-master replication) must be added manually in the AWS Management Console after the restore operation completes.

To learn how to add DB instances to Amazon Aurora DB clusters, see [AWS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-replicas-adding.html).

* Veeam Data Cloud for AWS does not support restoring RDS resources to the original location if deletion protection is enabled for the source resource.

* [Applies only if you perform restore databases of Microsoft SQL Server and PostgreSQL DB instances from image-level backups] Keep in mind the following:

* Veeam Data Cloud for AWS supports restoring databases only to the same AWS Region where the source DB instances reside.
* The database account that you specify for the restore operation will become the owner of all restored databases.
* Veeam Data Cloud for AWS does not support restoring original database accounts, including their predefined roles and access privileges. Therefore, you will have to manually recreate these accounts on the restored databases and reassign their privileges after the restore process completes.

* [Applies only if you perform restore databases of Microsoft SQL Server DB instances from image-level backups] Keep in mind the following:

* The target DB instance must be set to the same time zone as the source DB instance. Otherwise, your applications may encounter data consistency issues.
* The target DB instance must run the same or a later engine version as the source DB instance. Otherwise, the restore operation will fail to complete successfully.
* Veeam Data Cloud for AWS does not support restoring databases that contain the FILESTREAM file group.
* Veeam Data Cloud for AWS does not support restoring databases of DB instances that have a zero backup retention period to DB instances that have a nonzero retention period due to the incompatibility in database recovery models. This is the expected behavior caused by [AWS technical limitations](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Appendix.SQLServer.CommonDBATasks.DatabaseRecovery.html).

DynamoDB Restore

When restoring DynamoDB tables, consider the following:

* Veeam Data Cloud for AWS supports restoring DynamoDB tables only to the same AWS account to which the source tables belong.

* Veeam Data Cloud for AWS supports restoring only those DynamoDB table properties that are described in section [DynamoDB Backup](aws_backup_hiw_dynamo.md#table_parameters).

* The [AWS Backup](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/backuprestore_HowItWorksAWS.html) service does not support copying DynamoDB cloud-native backups stored in a cold storage tier to another AWS Region. These means that you will only be able to use these backups to restore tables to the same AWS Region in which the backups reside after being transitioned from a warm storage tier.

* You can change the Time to Live (TTL) setting for DynamoDB tables only an hour after the restore operation completes.

Redshift Restore

When restoring Redshift clusters, consider the following:

* Veeam Data Cloud for AWS supports restoring Amazon Redshift clusters only to the same AWS accounts to which the source clusters belong and the same AWS Region where the source clusters reside.

* Veeam Data Cloud for AWS supports restoring only those Redshift cluster properties that are described in section [Redshift Clusters Backup](aws_backup_hiw_redshift.md#properties).
* Veeam Data Cloud for AWS does not support restoring Amazon Redshift clusters with the Multi-AZ deployment. These clusters will be restored as clusters with the Single-AZ deployment.

Redshift Serverless Restore

When restoring Redshift Serverless namespaces, consider the following:

* Veeam Data Cloud for AWS supports restoring Amazon Redshift Serverless namespaces only to the same AWS accounts to which the source namespaces belong and the same AWS Region where the source namespaces reside.
* Veeam Data Cloud for AWS supports restoring only those Redshift Serverless namespace properties listed in section [Redshift Serverless Backup](aws_backup_hiw_redshift_serverless.md#properties).
* Veeam Data Cloud for AWS does not support restoring Amazon Redshift Serverless namespaces to provisioned clusters.
* Veeam Data Cloud for AWS does not support restoring tables of Amazon Redshift Serverless namespaces.

EFS Restore

Veeam Data Cloud for AWS supports restoring EFS file systems only to the same AWS account to which the source file systems belong.

FSx Restore

When restoring FSx file systems, consider the following:

* Veeam Data Cloud for AWS supports restoring FSx file systems only to the same AWS accounts to which the source file systems belong.

* Veeam Data Cloud for AWS supports restoring only those FSx file system properties that are described in section [FSx Backup](aws_backup_hiw_fsx.md#parameters).

* Veeam Data Cloud for AWS does not support restoring Amazon FSx for Windows File Server file systems that use AWS Secrets Manager to store service account credentials when joined to a self-managed Microsoft Active Directory (AD).

