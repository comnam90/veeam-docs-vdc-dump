---
title: "Creating Backup Policies"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_policies.html"
last_updated: "3/30/2026"
product_version: ""
---

# Creating Backup Policies


Veeam Data Cloud for AWS runs backup policies for every data protection operation. A backup policy is a collection of settings that define the way backup operations are performed: what data to back up, where backups must be stored, when the backup process must start, and so on.

You can create multiple backup policies for AWS resources. One backup policy can be used to process multiple resources residing in different AWS Regions within one AWS account, but you can back up each resource with one backup policy at a time. If an EC2 instance is added to more than one backup policy, it will be processed only by a backup policy that has the highest priority. Other backup policies will skip this EC2 instance from processing. For information on how to set a priority for a backup policy, see [Setting Policy Priority](aws_policy_priority.md).

In This Section

* [Creating EC2 Backup Policies](aws_backup_create_ec2.md)
* [Creating RDS Backup Policies](aws_backup_create_rds.md)
* [Creating DynamoDB Backup Policies](aws_backup_create_dynamo.md)
* [Creating Redshift Clusters Backup Policies](aws_backup_create_redshift_clusters.md)
* [Creating Redshift Serverless Backup Policies](aws_backup_create_redshift_serverless.md)
* [Creating EFS Backup Policies](aws_backup_create_efs.md)
* [Creating FSx Backup Policies](aws_backup_create_fsx.md)

