---
title: "Step 3. Specify Account"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_restore_rds_account.html"
last_updated: "3/25/2026"
product_version: ""
---

# Step 3. Specify Account


At the Account step of the wizard, select the AWS account to which the restored RDS resources belong. For an AWS account to be displayed in the list of available accounts, it must be included into the tenant as described in section [Adding Tenants](aws_tenant_scope.md).

|  |
| --- |
| Note |
| To perform the restore operation, Veeam Data Cloud for AWS uses the permissions of the IAM role that was created in the AWS account during [CloudFormation template deployment](aws_tenant_connection.md). |

[![Specify Account](images/aws_restore_rds_account.webp)](images/aws_restore_rds_account.webp "Specify Account")

