---
title: "Getting Started with Veeam Data Cloud for Microsoft Entra ID"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/entra_id_getting_started.html"
last_updated: "11/28/2025"
product_version: ""
---

# Getting Started with Veeam Data Cloud for Microsoft Entra ID

In this article

To quickly get started with Veeam Data Cloud for Microsoft Entra ID, follow these steps:

1. Obtain access to Veeam Data Cloud and perform your first login. For details, see [Accessing Veeam Data Cloud](accessing_vdc.md).
2. Invite other users to your Veeam Data Cloud organization and assign them roles so that your team can use the portal. For details, see [Users and Roles](users_manage.md).
3. Learn about Veeam Data Cloud for Microsoft Entra ID limitations and find out in which regions you can store your backups. For details, see [Considerations and Limitations](entra_id_limitations.md) and [Backup Storage Regions](entra_id_regions.md).
4. Add your Microsoft Entra ID tenants to Veeam Data Cloud. For details, see [Adding Microsoft Entra ID Tenants](entra_id_tenant_add.md).

After you add a Microsoft Entra ID tenant, Veeam Data Cloud will automatically create a backup policy to protect your tenant data.

|  |
| --- |
| note |
| It is normal for the initial full backup to take a long time to complete. |

1. Once Veeam Data Cloud creates the first Entra ID backup, you can restore your tenant data. For details, see [Entra ID Restore](entra_id_data_restore.md).
2. View backup and restore logs and monitor the protection status of your Microsoft Entra ID tenant. For details see [Viewing Backup and Restore Sessions](entra_id_activity.md) and [Viewing Dashboard](entra_id_dashboard.md).

If you have other workloads in Veeam Data Cloud, you can leverage the [Organization Dashboard](dashboard.md) and [Organization Activity](activity.md) views, which provide aggregated information across your entire Veeam Data Cloud organization.

Page updated 11/28/2025
