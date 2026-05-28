---
title: "Editing Flex Backup Policies"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/m365_backup_edit_flex.html"
last_updated: "5/28/2026"
product_version: ""
---

# Editing Flex Backup Policies


Variable License Model

Users of the Variable License Model can add and remove users and objects to and from backup policies created in Veeam Data Cloud for Microsoft 365.

Keep in mind that backup policy editing with the Fixed License Model is different. To learn more, see [Fixed License Model](#FixedLicense).

To edit a Flex backup policy, do the following:

1. On the Microsoft 365 page, click the name of the tenant you want to manage.
2. Select Backup Policies.
3. On the Backup Policies page, in the Actions column of the policy you want to edit, click Edit.

[![Editing Backup Policy](images/m365_backup_flex_edit.webp)](images/m365_backup_flex_edit.webp "Editing Backup Policy")

1. In the Policy name field, you can modify the name of the backup policy.
2. In the Description field, you can modify or provide a description for future reference.
3. [For specific items backup policies] In the Included in backup section, click View/Remove to view or modify the objects currently included in the backup policy. You can do the following actions:

* If you want to remove any of the objects, select the check boxes next to them and click Delete.

[![Editing Backup Policy](images/m365_backup_flex_edit_included.webp)](images/m365_backup_flex_edit_included.webp "Editing Backup Policy")

* If you want to modify the processing options for an object, click the pencil icon in the Actions column. In the Specify processing options window, select the check boxes for the objects you want to include in the backup policy and click Ok.

[![Editing Backup Policy](images/m365_backup_flex_edit_objects.webp)](images/m365_backup_flex_edit_objects.webp "Editing Backup Policy")

1. [For specific items backup policies] In the Add additional items section, to add more items to the backup policy do the following:

* Click Select next to Users and choose users to to add to the backup policy. For each selected user, you can select check boxes to include their Mailbox, Archive Mailbox, OneDrive and Personal Site in the backup.

You can also click Upload a CSV file to upload a .CSV or text file with one email address per line.

* Click Select next to Groups and choose groups to add to the backup policy. For each group member, you can select check boxes to include their Mailbox, Archive Mailbox, OneDrive and Personal Site in the backup. For each group mailbox, you can select check boxes to include the group Mailbox and Site in the backup.

Use dynamic Entra ID groups if you want the groups to be automatically updated between backup policy runs. Otherwise, you must manually add and delete users from the groups.

* Click Select next to SharePoint Sites and choose sites to back up. If you select the root SharePoint site, the list of sites to back up will be automatically updated when the backup policy runs. For example, if some subsites were added or deleted between backup policy runs, the backup policy will reflect those changes.

You can also click Upload a CSV file to upload a .CSV file with one SharePoint site URL per line.

* Click Select next to Teams and choose teams to back up. You can select whether to back up team posts if you [enabled team posts backup](m365_enable_team_chats_backup.md).

[![Editing Backup Policy](images/m365_backup_flex_edit_add.webp)](images/m365_backup_flex_edit_add.webp "Editing Backup Policy")

1. In the Exclude more items section, click Select next to Users, Groups, SharePoint Sites or Teams and choose specific objects to exclude.

For Users, you can also click Upload a CSV file to upload a .CSV or text file with one email address per line.

For SharePoint Sites, you can also click Upload a CSV file to upload a .CSV file with one SharePoint site URL per line.

[![Editing Backup Policy](images/m365_backup_flex_edit_excluded.webp)](images/m365_backup_flex_edit_excluded.webp "Editing Backup Policy")

1. Click Update Policy to complete the operation.

Fixed License Model

|  |
| --- |
| IMPORTANT |
| The Fixed License Model has been deprecated. Any existing users will be moved to the Variable License Model, which provides additional functionality. No features will be lost in this transition. |

Users of the Fixed License Model can add and remove users and objects to and from backup policies created in Veeam Data Cloud for Microsoft 365.

Keep in mind that backup policy editing with the Variable License Model is different. To learn more, see [Variable License Model](#VarLicense).

To edit a Flex backup policy, do the following:

1. On the Microsoft 365 page, click the name of the tenant you want to manage.
2. Select Backup Policies.
3. On the Backup Policies page, in the Actions column of the policy you want to edit, click Edit.

1. Follow instructions to add or remove objects within your backup policies:

* [Adding Objects to Backup Policy](#add_object)
* [Removing Groups and Users from Backup Policy](#remove_object)

Adding Objects to Backup Policy

To add objects to a backup policy, take the following steps:

1. To add Microsoft 365 users, do the following:

1. In the Microsoft 365 Users and Groups tab of the Manage Backup Items page, click Add User.
2. In the User selection window, select check boxes next to user names to specify users to be backed up.
3. For each user that you selected, in the Mailbox, Archive Mailbox, OneDrive, and Personal Site columns, select what objects you want to back up.
4. Click OK to confirm your selection.

1. To add Microsoft 365 groups, do the following:

1. In the Microsoft 365 Users and Groups tab of the Manage Backup Items page, click Add Group.
2. In the Select Groups window, select the group you want to add.

Veeam Data Cloud searches within the cache to optimize performance. Use Search Microsoft 365 directly (slower but includes newly created Groups) to search for objects recently added through the Microsoft 365 admin center.

1. In the User selection window, select check boxes next to user names to specify users to be backed up.

1. For each user that you selected, in the Mailbox, Archive Mailbox, OneDrive, and Personal Site columns, select what objects you want to back up.

1. Click OK to confirm your selection.

1. Click Next.

1. To add SharePoint sites, do the following:

1. In the Sharepoint Sites and Teams tab, click Sharepoint Sites.

1. In the Site selection window, use the search bar or the list of SharePoint sites to find specific sites. Select check boxes next to names of the sites that you want to back up. If you select a root SharePoint site, the list of sites to back up will be automatically updated when the backup policy runs. For example, if some subsites were added or deleted between backup policy runs, the backup policy will reflect those changes.

1. Click OK to confirm your selection.

1. To add teams, do the following:

1. In the Sharepoint Sites and Teams tab, click Teams.

1. In the Team selection window, use the search bar or the list of teams to find specific Microsoft 365 teams. Select check boxes next to names of teams that you want to back up.

Veeam Data Cloud searches within the cache to optimize performance. Use Search Microsoft 365 directly (slower but includes newly created Groups) to search for objects recently added through the Microsoft 365 admin center.

1. Click OK to confirm your selection.

1. Click Start backup to finish the operation.

Removing Groups and Users from Backup Policy

To remove Microsoft 365 users from a backup policy, do the following:

1. Navigate to the Microsoft 365 Users and Groups tab.
2. In the Microsoft 365 Users window, select check boxes next to user names of users that you want to remove from the backup policy.
3. Click Delete to complete the operation.

To remove Microsoft 365 groups from a backup policy, do the following:

1. Navigate to the Microsoft 365 Users and Groups tab.
2. In the Microsoft 365 Groups window, click the bin icon on the right to remove a group from the backup.
3. Click Delete to complete the operation.

