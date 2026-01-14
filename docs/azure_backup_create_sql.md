---
title: "Creating SQL Backup Policies"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_backup_create_sql.html"
last_updated: "11/11/2025"
product_version: ""
---

# Creating SQL Backup Policies

In this article

Use the New Azure SQL Policy wizard to create a backup policy to protect SQL databases.

|  |
| --- |
| Important |
| If your SQL server [does not allow public access](https://learn.microsoft.com/en-us/azure/azure-sql/database/private-endpoint-overview?view=azuresql#disable-public-access-to-your-logical-server), the backup policy will send a private endpoint connection request to the server during the first run, which will initially fail. To make future policy runs succeed, approve the connection request in your Azure portal. Until this is done, the policy will continue to fail.  To learn more, see [Microsoft Docs](https://learn.microsoft.com/en-us/azure/azure-sql/managed-instance/private-endpoint-overview?view=azuresql&tabs=separate-vnets#review-and-approve-a-request-to-create-a-private-endpoint). |

1. [Launch the New Azure SQL Policy wizard](azure_backup_create_sql_launch.md).
2. [Specify the policy details](azure_backup_create_sql_name.md).
3. [Specify the policy source](azure_backup_create_sql_source.md).
4. [Specify the policy protection settings](azure_backup_create_sql_sla.md).
5. [Specify database processing settings](azure_backup_create_sql_process.md).
6. [Complete the backup policy configuration](azure_backup_create_sql_complete.md).

Page updated 11/11/2025
