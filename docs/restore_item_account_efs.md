---
title: "Step 3. Specify Account Settings"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/restore_item_account_efs.html"
last_updated: "3/23/2026"
product_version: ""
---

# Step 3. Specify Account Settings


At the Account step of the wizard, select the AWS account to which the restored EFS file systems belong. For an AWS account to be displayed in the list of available accounts, it must be included into the tenant as described in section [Adding Tenants](aws_tenant_scope.md).

|  |
| --- |
| Note |
| To perform the restore operation, Veeam Data Cloud for AWS uses the permissions of the IAM role that was created in the AWS account during [CloudFormation template deployment](aws_tenant_connection.md). |

[![Specify Account Settings](images/restore_item_account_efs.webp)](images/restore_item_account_efs.webp "Specify Account Settings")

