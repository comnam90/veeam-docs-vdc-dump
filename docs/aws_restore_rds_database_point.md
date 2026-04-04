---
title: "Step 2. Select Databases"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_restore_rds_database_point.html"
last_updated: "3/24/2026"
product_version: ""
---

# Step 2. Select Databases


At the Databases step of the wizard, you can add databases to the restore session and select a restore point that will be used to perform the restore operation for each database. By default, Veeam Data Cloud for AWS uses the most recent valid restore point. However, you can restore the database data to an earlier state.

To help you choose a restore point, Veeam Data Cloud for AWS provides the following information on each available restore point:

* Date — the date when the restore point was created.
* Type — the type of the restore point.
* State — the state of the restore point stored in the standard backup repository:

* Healthy — the restore point has been verified by the health check session and reported to be healthy.
* Incomplete — the restore point has been verified by the health check session and reported to be corrupted or incomplete.

* Storage Class — the storage class of the backup repository where the restore point is stored.
* Restore Point Region — the AWS Region where the restore point is stored.

|  |
| --- |
| Important |
| For Microsoft SQL Server DB instances, Veeam Data Cloud for AWS does not support restoring databases that contain the FILESTREAM file group. |

[![Select Databases](images/aws_restore_rds_database_point.webp)](images/aws_restore_rds_database_point.webp "Select Databases")

