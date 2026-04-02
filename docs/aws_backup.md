---
title: "Performing Backup"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup.html"
last_updated: "3/30/2026"
product_version: ""
---

# Performing Backup


With Veeam Data Cloud for AWS, you can protect data in the following ways:

* Create cloud-native snapshots of EC2 instances and RDS resources

A cloud-native snapshot of a EC2 instance includes point-in-time snapshots of EBS volumes attached to the processed instance. Snapshots of EBS volumes (also referred to as EBS snapshots) are taken using native [AWS capabilities](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html).

A cloud-native snapshot of a DB instance includes a storage volume snapshot of the instance. Snapshots of DB instances (also referred to as DB snapshots) are taken using native [AWS capabilities](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateSnapshot.html).

A cloud-native snapshot of an Aurora DB cluster includes a storage volume snapshot of the cluster that backs up the entire cluster and not just individual databases. Snapshots of Aurora DB clusters (also referred to as DB cluster snapshots) are taken using native [AWS capabilities](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/USER_CreateSnapshotCluster.html).

* Create image-level backups of EC2 instances and RDS resources

In addition to cloud-native snapshots, you can protect your EC2 and DB instances with image-level backups.

An image-level backup of an EC2 instance captures the whole image of the processed instance (including instance configuration, OS data, application data and so on) at a specific point in time. The backup is saved to a backup repository in the native Veeam format.

An image-level backup of a DB instance captures the Microsoft SQL Server or PostgreSQL databases of the processed instance. The backup is saved to a backup repository in the native Veeam format.

* Create cloud-native backups of your DynamoDB tables

An Amazon DynamoDB backup captures the whole image of the DynamoDB table at a specific point of time. DynamoDB backups are taken using native [AWS capabilities](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/CreateBackupAWS.html).

DynamoDB backups are stored in backup vaults in AWS Regions where the processed tables reside.

* Create cloud-native backups of your Redshift clusters

An Amazon Redshift backup captures the whole image of the Redshift cluster at a specific point of time. Redshift backups are taken using native [AWS capabilities](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/CreateBackupAWS.html).

Redshift clusters backups are stored in backup vaults in AWS Regions where the processed clusters reside.

* Create cloud-native backups of your Redshift Serverless namespaces

An Amazon Redshift Serverless backup captures the data of the processed Redshift Serverless namespace at a specific point of time. Redshift Serverless backups are taken using native [AWS capabilities](https://docs.aws.amazon.com/redshift/latest/mgmt/serverless-snapshots-recovery-points.html).

Redshift Serverless backups are stored in the AWS Regions where the processed namespaces reside.

* Create cloud-native backups of your EFS and FSx file systems

An Amazon EFS and FSx file system backup captures the whole image of the EFS and FSx file system (including file system configuration, files, directories and so on) at a specific point of time. EFS and FSx backups are taken using native [AWS capabilities](https://docs.aws.amazon.com/efs/latest/ug/awsbackup.html).

EFS and FSx backups are stored in backup vaults in AWS Regions where the processed file systems reside.

In This Section

* [Creating Backup Policies](aws_backup_policies.md)
* [Managing Backup Policies](aws_policy_manage.md)
* [Viewing EC2 Policy Details](aws_policy_view.md)

