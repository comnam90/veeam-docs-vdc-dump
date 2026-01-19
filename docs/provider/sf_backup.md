---
title: "Salesforce Backup"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/sf_backup.html"
last_updated: "12/10/2025"
product_version: ""
---

# Salesforce Backup


To back up data of Salesforce tenants, Veeam Data Cloud runs backup policies. A backup policy is a collection of settings that define the way backup operations are performed: what data to back up, when to start a backup session, and so on.

When you add a new Salesforce tenant, Veeam Data Cloud automatically creates a backup policy for the tenant. Each Salesforce tenant is protected by a single backup policy that you can edit later.

The default backup policy is created with the following settings:

| Policy Setting | Default Value |
| --- | --- |
| Salesforce API limits | 60% |
| Default policy schedule | Daily |
| Included tenant objects | All except standard History and Tag objects. By default, these objects are excluded from backup, but you can add them manually. For details, see [Configure Additional Options](sf_backup_policies_edit_backup_options.md). |
| Included file types | All  Note: If the Salesforce user that you use to connect to your Salesforce tenant doesn't have the Query All Files permission assigned, file backup will be disabled. To enable file backup, grant the permission in the Salesforce console as described in [Salesforce documentation](https://help.salesforce.com/s/articleView?id=sf.permissions_about_users_access.htm&language=en_US&type=5) and then enable file backup in the backup policy. For details, see [Configure Additional Options](sf_backup_policies_edit_backup_options.md). |
| Automatically add new objects | Enabled |
| Automatically add new fields | Enabled |
| Encryption | Enabled with built-in encryption key. All file types are selected for encryption. |
| Retention for records and file versions | 1 year |
| Retention for deleted records and files | 1 year (not configurable) |

|  |
| --- |
| Note |
| Only users assigned the Salesforce:Administrator or Salesforce:BackupOperator role can perform backup operations with Salesforce tenants. However, these users can create and run backup policies within their permission scope only — that is, Salesforce tenants whose data they can access. For details, see [Users and Roles](users_manage.md). |

In This Section

* [How Salesforce Backup Works](sf_how_backup_works.md)
* [Editing Backup Policies](sf_backup_policies_edit.md)
* [Starting and Stopping Backup Policies](sf_backup_policies_start_stop.md)
* [Enabling and Disabling Backup Policies](sf_backup_policies_disable_enable.md)
* [Browsing Backups](sf_backup_browse.md)

