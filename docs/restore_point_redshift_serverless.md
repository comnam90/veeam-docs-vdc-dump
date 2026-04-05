---
title: "Step 2. Select Restore Point"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/restore_point_redshift_serverless.html"
last_updated: "3/23/2026"
product_version: ""
---

# Step 2. Select Restore Point


At the Restore Point step of the wizard, select a restore point that will be used to restore the selected Redshift Serverless namespace. By default, Veeam Data Cloud for AWS uses the most recent valid restore point. However, you can restore the namespace data to an earlier state.

To select a restore point, do the following:

1. Click Restore Point.
2. In the Choose restore point window, select the necessary restore point and click Apply.

To help you choose a restore point, Veeam Data Cloud for AWS provides the following information on each available restore point:

* Date — the date when the restore point was created.
* Type — the type of the restore point.

* Restore Point Region — the AWS Region where the restore point is stored.

[![Select Restore Point](images/restore_point_redshift_serverless.webp)](images/restore_point_redshift_serverless.webp "Select Restore Point")

