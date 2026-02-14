---
title: "Backup Object Types"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/m365_backup_object_types.html"
last_updated: "2/13/2026"
product_version: ""
---

# Backup Object Types


Veeam Data Cloud for Microsoft 365 allows you to select what types of objects to include in the backup and exclude from the backup, depending on your plan. Objects of each type consist of a set of child objects. You can specify processing and exclusion options — that is, select what child objects of a specific object to include in the backup and what to exclude from the backup.

Flex Backup Object Types

Under the Foundation plan, the following object types and their child objects are available for Flex backups:

* Organization — consists of all objects within your Microsoft 365 organization. The objects you can exclude from the backup are:

+ Microsoft 365 Users and their child objects: Mailbox, Archive Mailbox, OneDrive, Personal Site
+ Groups and their child objects: members with Mailbox, Archive Mailbox, OneDrive and Sites, and Group Mailbox and Group Site for Microsoft 365 groups
+ SharePoint Sites
+ Teams
+ Teams chats (if backup of team chats is enabled)

* Microsoft 365 Users — consists of users, shared mailboxes, public mailboxes and discovery search mailboxes. The child objects you can process or exclude from the backup are: Mailbox, Archive Mailbox, OneDrive and Personal Site.
* Groups — consists of Microsoft 365 groups, dynamic Entra ID groups, security groups (nested security groups are also supported if they are discoverable) and distribution groups. The child objects you can process or exclude from the backup are: members with Mailbox, Archive Mailbox, OneDrive and Sites. For Microsoft 365 groups, Group Mailbox and Group Site are also available.
* SharePoint Sites — consists of Microsoft SharePoint sites and subsites. You can either select the root site, which automatically selects all its subsites, or any of its subsites.
* Teams — consists of Microsoft Teams teams. Channels, Posts in channels, Tabs, Files and Membership are always processed. If you have [enabled team chats backup](m365_enable_team_chats_backup.md), you also have the option to process or exclude Teams chats, meaning private and shared channels and public channel messages.
* Partial Organization — consists of all objects within your Microsoft 365 organization. You can select processing options by service: Mailbox, Archive Mailbox, OneDrive, Sites, Teams and Teams chats (if backup of Teams chats is enabled). You can then exclude the Microsoft 365 Users, Groups, SharePoint Sites and Teams objects and their child objects from the partial organization backup.

You can select which objects and their child objects to process and exclude from a backup when you [create new backup policies](m365_backup_create_flex.md) and when you [edit existing backup policies](m365_backup_edit_flex.md). For example, when you select to back up a Microsoft 365 user, you can select to process their Mailbox, Archive Mailbox and OneDrive, and not process their Personal Site in the backup.

Express Backup Object Types

Under the Premium plan, you can have both Flex and Express backup policies.

You can create Express backup policies by product. The following object types are available for each product:

* For an Express Outlook backup policy:

* Entire Organization — consists of all Microsoft 365 users and groups with Outlook accounts within your organization.
* Microsoft 365 Users — consists of Microsoft 365 users with Outlook accounts within your organization.
* Groups — consists of Microsoft 365 groups, dynamic Entra ID groups, security groups and distribution groups.

The objects that are backed up are Mail, Contacts, Calendar and Task items. Draft items are not backed up. Discovery search mailboxes, public folder mailboxes and resource mailboxes are not supported.

* For an Express OneDrive backup policy:

* Entire Organization — consists of all Microsoft 365 users and groups with OneDrive for Business accounts within your organization.
* Microsoft 365 Users — consists of Microsoft 365 users with OneDrive for Business accounts within your organization.
* Groups — consists of Microsoft 365 groups, dynamic Entra ID groups, security groups and distribution groups.

The objects that are backed up are Files, Folders and Metadata.

* For an Express SharePoint backup policy:

* Entire Organization — consists of all Microsoft 365 SharePoint accounts within your organization.
* SharePoint Sites — consists of Microsoft SharePoint sites and subsites. You can either select the root site, which automatically selects all its subsites, or any of its subsites.

For a selected items backup policy, you can choose which objects to process in the backup when you [create new backup policies](m365_backup_create_express.md) and when you [edit existing backup policies](m365_backup_edit_express.md). For example, when you create an Express Outlook backup policy, click Microsoft 365 Users and select the users you want to back up.

Considerations

Consider the following:

* To back up user mailboxes, make sure that a mailbox has a valid Microsoft 365 license.
* To back up SharePoint Online and OneDrive for Business objects, make sure that a user account has a valid Microsoft 365 license with a SharePoint Online plan enabled.
* To back up public folder mailboxes, first check the considerations listed in [Backup and Restore of Public Folders](m365_data_backup.md#public).
* Veeam Data Cloud for Microsoft 365 does not back up permissions for sharing mailbox folders and Calendar.
* Veeam Data Cloud for Microsoft 365 does not support backup of dynamic distribution groups. Members of dynamic distribution groups cannot be resolved.
* When you perform backup of SharePoint Online data, Veeam Data Cloud for Microsoft 365 does not back up the following objects:

+ External SharePoint lists. For more information, see [this Microsoft article](https://support.microsoft.com/en-us/office/differences-between-native-and-external-lists-6601eda9-b722-4bf8-a2bf-ce25cf3d2fd0).
+ SharePoint folder attachments
+ SharePoint site collection recycle bin
+ SharePoint sites created by Microsoft Loop

* To create Microsoft team chats backups, Veeam Data Cloud for Microsoft 365 needs access to [Microsoft Teams Export APIs](https://docs.microsoft.com/en-us/microsoftteams/export-teams-content). You must authorize Veeam Data Cloud for Microsoft 365 to use the required APIs. To learn how to do that, see [Enabling Microsoft Team Chats Backup](m365_enable_team_chats_backup.md).
* Veeam Data Cloud for Microsoft 365 does not back up the TeamsMessagesData folder.

