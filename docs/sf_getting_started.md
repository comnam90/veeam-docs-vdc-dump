---
title: "Getting Started with Veeam Data Cloud for Salesforce"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_getting_started.html"
last_updated: "11/28/2025"
product_version: ""
---

# Getting Started with Veeam Data Cloud for Salesforce


To quickly get started with Veeam Data Cloud for Salesforce, follow these steps:

1. Obtain access to Veeam Data Cloud and perform your first login. For details, see [Accessing Veeam Data Cloud](accessing_vdc.md).
2. Invite other users to your Veeam Data Cloud organization and assign them roles so that your team can use the portal. For details, see [Users and Roles](users_manage.md).
3. Learn about Veeam Data Cloud for Salesforce limitations and find out in which regions you can store your backups. For details, see [Considerations and Limitations](sf_limitations.md) and [Backup Storage Regions](sf_regions.md).
4. Add your Salesforce tenants to Veeam Data Cloud. For details, see [Adding Salesforce Tenants](sf_tenants_add.md).

After you add a Salesforce tenant, Veeam Data Cloud will automatically create a backup policy to protect your tenant data.

|  |
| --- |
| note |
| It is normal for the initial full backup to take a long time to complete. |

1. Edit the backup policy to adjust schedules, configure encryption and specify retention for backups. For details, see [Editing Backup Policies](sf_backup_policies_edit.md).
2. Once Veeam Data Cloud creates the first Salesforce backup, you can restore your tenant data. For details, see [Salesforce Restore](sf_restore.md).
3. Configure archival policies to delete excessive or obsolete data from Salesforce production tenants to consume less storage space in Salesforce and improve its performance. For details, see [Salesforce Archiving](sf_archiving.md).

You can also deploy Veeam Data Cloud Salesforce Extension that allows you to access and restore Salesforce archived data directly from the Salesforce console. The extension improves user experience and reduces administrative workload required to process data requests. For details, see [Configuring Salesforce Package Connection](sf_settings_connections_package.md).

1. View backup and restore logs and monitor the protection status of your Salesforce tenant. For details see [Activity](sf_activity.md) and [Viewing Dashboard](sf_dashboard.md).

If you have other workloads in Veeam Data Cloud, you can leverage the [Organization Dashboard](dashboard.md) and [Organization Activity](activity.md) views, which provide aggregated information across your entire Veeam Data Cloud organization.

