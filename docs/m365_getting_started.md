---
title: "Getting Started with Veeam Data Cloud for Microsoft 365"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_getting_started.html"
last_updated: "11/28/2025"
product_version: ""
---

# Getting Started with Veeam Data Cloud for Microsoft 365

In this article

To quickly get started with Veeam Data Cloud for Microsoft 365, follow these steps:

1. Obtain access to Veeam Data Cloud and perform your first login. For details, see [Accessing Veeam Data Cloud](accessing_vdc.md).
2. Invite other users to your Veeam Data Cloud organization and assign them roles so that they can use the portal. For details, see [Users and Roles](users_manage.md).
3. Learn about Veeam Data Cloud for Microsoft 365 limitations and find out in which regions you can store your backups. For details, see [Considerations and Limitations](m365_considerations_limitations.md) and [Backup Storage Regions](m365_region_availability.md).
4. Add your Microsoft 365 tenants to Veeam Data Cloud. For details, see [Adding Microsoft 365 Tenants](m365_tenant_add.md).

After you add a Microsoft 365 tenant, Veeam Data Cloud will automatically create a backup policy to protect your tenant data.

If you chose to manually create backup policies after onboarding, create backup policies. For details, depending on your plan, see [Creating Flex Backup Policies](m365_backup_create_flex.md) and [Creating Express Backup Policies](m365_backup_create_express.md).

|  |
| --- |
| note |
| * It is normal for the initial full backup to take a long time to complete.  * Microsoft may be throttling your traffic due to the high load of Microsoft Exchange data. For detailed instructions on how to disable Microsoft throttling, see [this Veeam KB article](https://www.veeam.com/kb4198). |

1. Once the initial backup session completes, you can restore your tenant data. For details, see [Microsoft 365 Restore](m365_restore.md).
2. Use basic or advanced search to search for objects in your backups. For details, see [Searching for Objects in Backup](m365_search.md).
3. View backup session logs and monitor the protection status of your Microsoft 365 tenant. For details see [Viewing Backup Logs](m365_backup_view_logs.md) and [Viewing Dashboard](m365_dashboard.md).
4. Generate, download and schedule Veeam Data Cloud for Microsoft 365 usage reports. For details, see [Reports](m365_reports.md).

Page updated 11/28/2025
