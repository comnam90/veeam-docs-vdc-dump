---
title: "Creating SQL Backup Policies"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/azure_backup_create_sql.html"
last_updated: "4/14/2026"
product_version: ""
---

# Creating SQL Backup Policies


Use the New Azure SQL Policy wizard to create a backup policy to protect SQL databases.

|  |
| --- |
| Important |
| Consider the following:   * If public access is disabled on the SQL Server, the backup policy will attempt to create a private endpoint connection during the first run, which will initially fail. You must approve this connection request in the Azure portal for future policy runs to succeed; otherwise, the policy will continue to fail. * If public access is enabled, the backup policy will use the public endpoint, which requires port 3342 to be open for inbound connections, regardless of whether a private endpoint is also configured. |

1. [Launch the New Azure SQL Policy wizard](azure_backup_create_sql_launch.md).
2. [Specify the policy details](azure_backup_create_sql_name.md).
3. [Specify the policy source](azure_backup_create_sql_source.md).
4. [Specify the policy protection settings](azure_backup_create_sql_sla.md).
5. [Specify the database processing settings](azure_backup_create_sql_process.md).
6. [Review the default policy settings](azure_backup_create_sql_review.md).
7. [Specify the notification settings](azure_backup_create_sql_notifications.md).
8. [Complete the backup policy configuration](azure_backup_create_sql_complete.md).

