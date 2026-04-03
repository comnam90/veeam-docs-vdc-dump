---
title: "Step 2. Select Restore Point"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_restore_entire_point_efs.html"
last_updated: "3/23/2026"
product_version: ""
---

# Step 2. Select Restore Point


At the File System step of the wizard, you can add EFS file systems to the restore session and select restore points to be used to perform the restore operation for each added file system. By default, Veeam Data Cloud for AWS uses the most recent valid restore point. However, you can restore a file system to an earlier state.

To select a restore point, do the following:

1. Select the EFS system and click Restore Point.
2. In the Choose restore point window, select the necessary restore point and click Apply.

To help you choose a restore point, Veeam Data Cloud for AWS provides the following information on each available restore point:

* Date — the date when the restore point was created.

* Size — the size of the restore point.
* Type — the type of the restore point.

* Restore Point Region — the AWS Region where the restore point is stored.

[![Select Restore Point](images/aws_restore_entire_point_efs.webp)](images/aws_restore_entire_point_efs.webp "Select Restore Point")

