---
title: "Managing Backup Repositories"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_settings_backup_repos.html"
last_updated: "5/19/2026"
product_version: ""
---

# Managing Backup Repositories


Veeam Data Cloud for Microsoft 365 uses backup repositories as a storage system for backups. Users can edit their backup repositories, add new backup repositories within their storage region, and supply their own encryption password for a backup repository.

Only users with the OrganizationAdmin or M365:Administrator roles or a custom role with the Manage Tenants permission can manage the backup repositories of their tenant. For more information about roles, see [Roles](users_roles.md).

Creating Backup Repositories

To create a new backup repository, do the following:

1. On the Microsoft 365 page, click the name of the tenant you want to manage.
2. Select Settings.
3. Go to the Backup Repositories tab.
4. Click Add.

[![Managing Backup Repositories](images/m365_settings_backup_repos_add.webp)](images/m365_settings_backup_repos_add.webp "Managing Backup Repositories")

1. In the Create new backup repository window, do the following:

1. Select the Custom name check box if you want to specify a name for the backup repository. Otherwise, Veeam Data Cloud generates the name automatically based on the name of your organization.
2. In the Retention period type drop-down list, select the type of the retention period:

* Yearly. If selected, you must also select a value in the Retention period drop-down list, to specify the duration of the retention period.
* Daily. If selected, you must also specify a value in the Number of days field, to specify the duration of the retention period.

1. In the Region drop-down list, select the region where you want to store your data.
2. Click Save.

[![Managing Backup Repositories](images/m365_settings_backup_repos_add_options.webp)](images/m365_settings_backup_repos_add_options.webp "Managing Backup Repositories")

|  |
| --- |
| note |
| When you create a new backup repository and want to include an object from the old backup repository, Veeam Data Cloud performs a full backup of that object which takes time.  For example, you have the old backup repository where you are backing up a mailbox, with retention set to 1 year. Then you add a new backup repository with retention set to 3 years. In the new repository, you create a backup policy that includes the mailbox and you remove this mailbox from the backup policy in the old repository. In this case, Veeam Data Cloud performs a full backup for the mailbox in the new backup repository, which takes time. The mailbox will remain in the old backup repository until the 1 year retention ends. |

Editing Backup Repositories

To edit a backup repository, do the following:

1. On the Microsoft 365 page, click the name of the tenant you want to manage.
2. Select Settings.
3. Go to the Backup Repositories tab.
4. In the Actions column, click the menu next to the backup repository you want to edit.
5. Click Edit display name to modify the display name of the backup repository. This name will be visible when selecting the storage region during the creation of a new backup policy. In the Edit Repository Display Name window, specify a new display name for the backup repository and click Save.

[![Managing Backup Repositories](images/m365_settings_backup_repos_name.webp)](images/m365_settings_backup_repos_name.webp "Managing Backup Repositories")

1. Click Edit retention to modify the retention settings of the backup repository. In the Edit repository retention window, in the Retention period type drop-down list, select Yearly or Daily. Depending on the selection, you must then specify the duration of the retention period in years or number of days.

[![Managing Backup Repositories](images/m365_settings_backup_repos_retention.webp)](images/m365_settings_backup_repos_retention.webp "Managing Backup Repositories")

1. Click Set your own password to add encryption to the backup repository. In the Add Password window, provide a password, verify that password and click Save.

If you want to update your password, click Change encryption password. In the Update Password window, provide the existing password, add a new password and verify it and click Save.

[![Managing Backup Repositories](images/m365_settings_backup_repos_password.webp)](images/m365_settings_backup_repos_password.webp "Managing Backup Repositories")

|  |
| --- |
| note |
| If you forgot your encryption password, contact Veeam Customer Support. |

