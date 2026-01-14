---
title: "Considerations and Limitations"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_considerations_limitations.html"
last_updated: "1/8/2026"
product_version: ""
---

# Considerations and Limitations

In this article

This section lists considerations and known limitations in Veeam Data Cloud for Microsoft 365.

General

* Adding Microsoft 365 organizations using modern authentication method with legacy protocols allowed is not supported.
* Backup of a Microsoft 365 tenant organization is not supported if the initial domain of the organization was changed.
* Backup of dynamic distribution groups is not supported. Members of dynamic distribution groups cannot be resolved. Dynamic Entra ID groups can be used instead. For more information, see [Dynamic Entra ID Groups](#entragroups).
* Microsoft Entra Privileged Identity Management is not supported.
* Backup is not supported for Microsoft organizations in US Government GCC High regions.
* Express backup is not supported for Microsoft organizations in GCC regions.
* You cannot delete mailboxes, OneDrives and SharePoint sites protected (or were protected in the past 365 days) under an Express backup policy. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/troubleshoot/sharepoint/sites/cannot-delete-sites-protected-by-microsoft365-backup).

If you want to request the deletion of a specific mailbox, OneDrive or SharePoint site, contact Veeam Customer Support.

Supported Microsoft Organizations

Veeam Data Cloud for Microsoft 365 supports the following Microsoft Exchange Online and Microsoft SharePoint Online organization versions:

* Microsoft 365 Exchange Online

[Microsoft 365 and Office 365 service families](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options#service-families-and-plans), standalone services and plans for Business, Education, and Government\* hosted by Microsoft are supported. For more information about system requirements and limitations for Microsoft 365, see [this Microsoft article](https://www.microsoft.com/en-us/microsoft-365/microsoft-365-and-office-resources#Office365forBEG).

* Microsoft 365 SharePoint Online

[Microsoft 365 and Office 365 service families](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options#service-families-and-plans), standalone services and plans for Business, Education, and Government\* hosted by Microsoft are supported. For more information about system requirements and limitations for Microsoft 365, see [this Microsoft article](https://www.microsoft.com/en-us/microsoft-365/microsoft-365-and-office-resources#Office365forBEG).

\*Government support is experimental. For more information, see [this Veeam KB article](https://www.veeam.com/kb2976).

Backup

Before you back up your data, consider the listed recommendations and best practices for Veeam Data Cloud for Microsoft 365. Then, depending on your license plan, create new backup policies. For more information, see [Creating Flex Backup Policies](m365_backup_create_flex.md) and [Creating Express Backup Policies](m365_backup_create_express.md).

Number of Backup Policies

You can configure backup policies based on Users, Groups, Sites, Teams and Organizations (entire or partial).

If you configure a single backup policy for all your data, there are challenges due to risks like a single point of failure, management complexity, backup duration, and restore issues.

As a best practice, in most cases, it is recommended to create 2 backup policies.

For example, you can create a backup policy for Exchange Online and another backup policy for the rest of your data:

* Backup Policy 1: Mailboxes and Archive mailboxes
* Backup Policy 2: OneDrive for Business, SharePoint Online and Teams

In the case where you have more complex backup rules and do not back up your entire organization, it is recommended to split your backups into 3 backup policies:

* Backup Policy 1: Mailboxes and Archive mailboxes
* Backup Policy 2: OneDrive for Business
* Backup Policy 3: SharePoint Online and Teams

Recommended Maximums

While one SharePoint site counts as an object for sizing the Veeam Data Cloud for Microsoft 365 infrastructure, this does not always accurately represent the impact on the backup infrastructure. For example, a SharePoint site with 250,000 documents within a document library takes more compute resources to process than a simple 50 MB intranet site. It is advised to adhere to the limits specified by Microsoft for SharePoint, and to pay special attention to the guideline that suggests “For optimum performance, we recommend storing no more than 300,000 files in a single OneDrive". For more information, see [this Microsoft article](https://support.microsoft.com/en-us/office/restrictions-and-limitations-in-onedrive-and-sharepoint-64883a5d-228e-48f5-b3d2-eb39e07630fa#numberitemscanbesynced).

User-Based Services

For easier maintenance, backup policies for all user-based services in Exchange, as well as Exchange Archive, OneDrive, and Personal SharePoint Sites, should be based on user or group objects.

* If you want to back up all the users in the tenant, select the Partial Organization option and create one backup policy for each service.

* If you want to back up a subset of the users, create backup policies using groups. When you do not have groups, create new groups or manually select users and sites. In case you want the list of users of a backup policy to be automatically updated between backup policy runs, do not use simple groups, because you must manually update the groups every time a new user is added or removed from the groups. Use Dynamic Entra ID groups instead, because they are dynamically updated.

Dynamic Entra ID Groups

It is a best practice to use dynamic Entra ID groups for user-based backup policies, because these groups are dynamically updated within Entra ID, always representing the current state of your user base.

Create dynamic Entra ID groups and leverage the dynamic rules based on the objectID property. This property is a unique GUID for each user and thus a randomized number with statistically equal distribution of starting numbers/letters (HEX) over your user base.

For example, you can create regular expression match rules on the objectID property to create groups in any granularity. The following example shows how to use 2 groups with the following rules, to split your user base in 50%:

|  |
| --- |
| Group 1 (50%): (user.objectId -match "^[0-7].\*")  Group 2 (50%): (user.objectId -match "^[8-9a-f].\*") |

To increase the granularity, you can add a “lower level” of number/letter to your regular expression, The following example shows how the fist 4 groups look like when you want to group into 32 groups.

|  |
| --- |
| Group1: (user.objectId -match "^0[0-7].\*")  Group2: (user.objectId -match "^0[8-9a-f].\*")  Group3: (user.objectId -match "^1[0-7].\*")  Group4: (user.objectId -match "^1[8-9a-f].\*")  ... |

For more information on dynamic Entra ID groups, see [this Microsoft article](https://learn.microsoft.com/en-us/entra/identity/users/groups-create-rule).

For more information on dynamic Entra ID groups rules syntax, see [this Microsoft article](https://learn.microsoft.com/en-us/entra/identity/users/groups-dynamic-membership).

Microsoft SharePoint Online

It is recommended to keep the number of SharePoint pages processed within a single backup policy lower than the recommended maximum.

SharePoint also offers Personal Sites for users. These sites may be considered as not intended for keeping important company data, which is why it is advised to check if they need to be protected or not. Depending on the number of Personal Sites within the organization, exclusion of Personal Sites from backup policies can drastically reduce the time and performance impact during backups.

Also consider the following:

* To back up SharePoint Online objects, make sure that a user account has a valid Microsoft 365 license with an enabled SharePoint plan.
* A SharePoint Site Collection hierarchy is not supported if the root site was not configured. Make sure to configure the root site in advance using a SharePoint site template of your choice.
* If a SharePoint item has several versions with identical owshiddenversion values, only the latest version of this item is backed up. All the other versions are skipped from processing.
* When you perform backup of SharePoint data, Veeam Data Cloud for Microsoft 365 does not back up the following objects:

* External SharePoint lists

For more information, see [this Microsoft article](https://support.microsoft.com/en-us/office/differences-between-native-and-external-lists-6601eda9-b722-4bf8-a2bf-ce25cf3d2fd0).

* SharePoint folder attachments
* SharePoint site collection recycle bin
* SharePoint sites created by Microsoft Loop
* Archived SharePoint sites
* SharePoint sites with blocked access

* For Express backup policies, Veeam Data Cloud for Microsoft 365 only backs up root SharePoint sites.

Microsoft Throttling

During your initial full backup, Microsoft may be throttling your traffic due to the high load of Microsoft Exchange data. To mitigate this, you can temporarily disable Microsoft Exchange throttling in the Microsoft 365 admin center. For detailed instructions on how to disable Microsoft throttling, see [this Veeam KB article](https://www.veeam.com/kb4198).

Even after Microsoft throttling is disabled, Microsoft still throttles traffic and limits to processing 150 MB for each mailbox every 5 minutes.

Executing Backup Policies

You should not be executing more than one or 2 backup policies at the same time. For example, you can have mailboxes and Teams backup policies running at the same time, because they process data of different applications. You must never have OneDrive and SharePoint backup policies running at the same time, because OneDrive is built on top of SharePoint.

Backup Policies Start Time

Backup policies start times are dynamically managed to optimize system performance and ensure reliable service. Backups will always meet the agreed RPOs.

Editing Backup Policies

For information on how to edit existing backup policies, see [Editing Flex Backup Policies](m365_backup_edit_flex.md) and [Editing Express Backup Policies](m365_backup_edit_express.md).

|  |
| --- |
| NOTE |
| When you add a new user to a backup policy, Veeam Data Cloud for Microsoft 365 automatically attempts to add all child objects of the user data (Mailbox, Archive Mailbox, OneDrive, Personal Site) to the backup policy. If your backup policies are split into Exchange and Other items backups, you will need to edit the user and deselect the child objects you want to remove. |

Restore

Before you restore your data, consider the listed recommendations and best practices for Veeam Data Cloud for Microsoft 365.

General Considerations

* [Data restore methods](m365_restore.md) apply to Microsoft Outlook mailboxes, entire Microsoft OneDrives and Microsoft SharePoint sites. For other types of Outlook, OneDrive and SharePoint objects, you do not need to select the restore method.
* Backup and restore of Microsoft Teams data is available to users of the Flex and Premium plans only. Users can restore Teams data flexibly and do not need to select the restore method.
* Smaller restores may be quicker with Flex; benefits of Express are best realized with large restores.
* Veeam Data Cloud for Microsoft 365 supports a maximum of 2 restore operations in parallel. To raise this limit in urgent cases, contact Veeam Customer Support.
* Restore of OneNote notebooks from backups of Microsoft SharePoint Online, Microsoft OneDrive for Business and Microsoft Teams data is not supported.

As a workaround, you can download the required OneNote file to your computer and then upload this OneNote file to your OneDrive or SharePoint site.

* Preservation Hold items are not available for restore under the Flex plan.
* The maximum size for download in background of OneDrive for Business and SharePoint Online data is 200 GB.

Flex Restore Considerations

Exchange Online

* Mailboxes can be restored only to mailboxes of the same type. For example, a user mailbox to a user mailbox, an archive mailbox to an archive mailbox.

* Veeam Data Cloud for Microsoft 365 only restores public folders located under the IPM\_SUBTREE folder.

OneDrive for Business

Restore of OneNote notebooks from backups of Microsoft OneDrive for Business data is not supported.

SharePoint Online

Status Restore Limitations

* If a document or an item was in the Check Out state when the backup was created, the last version of the item will not be restored to the target SharePoint and will be available for viewing only. Previous versions (if any) will be restored.
* If automatic declaration of items as records was originally applied to the list item, the relevant status will not be preserved. Instead, the restored item status will be set in accordance with the target list or target library content approval workflow.
* If the On Hold status was originally applied to the list item, this item will not be restored.

Documents, Libraries and Lists Restore

* Versioning settings of SharePoint lists are not preserved during restore.
* Restoring Generic List and Pages Library may fail with the No content type 'XXX' found in web YYY error.
* The Created By field of restored documents is updated with the account performing restore.
* Some values of the Rating Settings of Discussion lists are not restored.

List Items Restore

Consider that when restoring a list item, Veeam Data Cloud for Microsoft 365 works in the following way:

1. Deletes an existing item.
2. Creates the latest version of the item anew, using data from the backup.
3. Checks whether it is declared as a record.
4. If the check is a success, the process finishes.
5. If not, the created version is deleted and item versions are restored sequentially.

This logic leads to the following peculiarities of list item restore:

* If a list or list items column is used as a lookup column in the dependent list, consider that restoring an item from the source list causes the relevant items deletion in the dependent list.
* If a lookup column in the dependent list has the enforced relationship behavior set to Cascade Delete, then restoring an item from the source list may cause item deletion in the dependent list due to Microsoft implementation. For more information, see [this Microsoft article](https://support.office.com/en-au/article/Create-list-relationships-by-using-unique-and-lookup-columns-80a3e0a6-8016-41fb-ad09-8bf16d490632).

To prevent this issue, you should turn off enforced relationship behavior.

Also consider the following limitations:

* If a lookup column in the dependent list has the enforced relationship behavior set to Restrict Delete, then the item restore will fail.
* If an .ASPX page references an item using ItemID, this reference may fail to restore (as the item will be created anew with a different ItemID).
* If a list item cannot be deleted (for example, the Welcome page of the site), consider that Veeam Data Cloud will restore all versions of the item sequentially without deletions, adding them to Version History.
* The restored Issue list items are assigned a new IssueID.
* Restore of the Time Card list is not supported.

List Items with Links Restore

* If the retention policy for the target list or target document library was configured to declare items as records automatically, only the last version of the item will be restored to the target list or target document library. The target retention policy settings will be applied to the restored item. However, links (attachments) will not be restored.
* If automatic declaration of items as records was originally applied to the list item, this item will not be restored.

Surveys Restore

* Survey items can be restored to a new survey, created automatically by Veeam Data Cloud for Microsoft 365 in the specified destination instead of the previously deleted survey. However, if a new survey is created by a user from scratch (not replacing a deleted one), items cannot be restored to such a survey.
* A survey can be restored to an existing target survey only if that target survey includes at least one item (question), same as survey questions stored in the content database.
* If a survey question was not answered completely in the source survey, after restore, the response status in the target survey will be set to Completed anyway.
* When restoring a single response to a survey, the target response item with the same number will be deleted and the restored item will be placed in the target survey after the last numbered response.

For example, if the target survey has responses numbered from 1 to 15 and you try to restore a response that used to be number 6 on the source, the target response number 6 will be deleted and the restored response will be assigned number 16.

Sites Restore

* When restoring site collections, make sure that such collections exist in the target location; Veeam Data Cloud for Microsoft 365 does not create site collections.
* Before restoring team sites, make sure that the user account used for authorization has access to the root SharePoint site of the tenant organization.
* When restoring team sites, Veeam Data Cloud for Microsoft 365 does not restore team site owners or Microsoft 365 group members.
* If you plan to restore SharePoint site pages, consider that Veeam Data Cloud for Microsoft 365 does not support the restore of items that are not stored in the SharePoint content database (in particular, pages, page references and items based on default templates). Such items cannot be restored, except for data from Wiki Content (text and images), which is stored in the database. Thus, site pages that contain only text and images can be restored and displayed properly.

Teams

* You can restore Microsoft Teams data to the original organization only.
* Veeam Data Cloud for Microsoft 365 does not change roles for team owners during restore. For example, you create a backup of your organization, and then change the role for a team member from Member to Owner. In this case, if you restore this team member from the backup, Veeam Data Cloud for Microsoft 365 will not set their role to Member.
* Restore of OneNote notebooks from backups of Microsoft Teams data is not supported.
* When restoring a channel tab, Veeam Data Cloud for Microsoft 365 does not preserve the relation between the link to a file published on the tab and the file itself. You will need to link the tab to the file manually after restore. This limitation does not apply to the scenario where you restore an entire team.
* Veeam Data Cloud for Microsoft 365 does not restore posts to their original location in the team channel. Instead, Veeam Data Cloud for Microsoft 365 exports posts to a file of the HTML format, creates a separate tab in the original channel and attaches the HTML file to this tab.
* If a user never opened the Files tab of a team channel in Microsoft Teams before data backup, files from this tab are not displayed in Veeam Data Cloud for Microsoft 365.
* When restoring a channel, Veeam Data Cloud for Microsoft 365 cannot rename this channel.
* Before restoring teams data, make sure that the user account used for authorization has access to the root SharePoint site of the tenant organization.

* During backup and restore of an archived team, Veeam Data Cloud for Microsoft 365 does not preserve the Make the SharePoint site read-only for team members property of the team on the Microsoft 365 side.
* When you restore a deleted team, a renamed General channel and its contents are not restored. A new empty General channel is created during team restoration. To recover the renamed General channel, restore it separately after the team is restored. The data will not be merged into the existing General channel.

Express Restore Considerations

General

* Veeam Data Cloud for Microsoft 365 replaces data in the original location with the data from the backup. For example, if a user is making edits on a SharePoint site and you restore it to a previous state, the user will lose their edits.
* When you create a backup policy for an Exchange Online mailbox, OneDrive for Business account or SharePoint Online site, Veeam Data Cloud for Microsoft 365 starts generating restore points.

* For Exchange Online, the restore points are created every 10 minutes. The retention period for these restore points is 52 weeks.
* For OneDrive for Business and SharePoint Online, the restore points are created every 10 minutes. The retention period for these restore points is 2 weeks. In addition, weekly restore points are created once a week. The retention period for these restore points is 50 weeks.

For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/microsoft-365/backup/backup-restore-data?view=o365-worldwide&tabs=exchange#considerations-when-using-restore).

|  |
| --- |
| NOTE |
| The 52 and 50 weeks of retention are not applicable once a tenant is no longer under Express backup protection. When a tenant is offboarded, the protected data will be preserved for 90 days after the date of offboarding, and then the data will be deleted. |

* To restore an Exchange Online mailbox or OneDrive for Business account for a user who is deleted from Microsoft Entra ID, do the following:

* If the user has been deleted within the past 30 days, restore the user based on the instructions in [this Microsoft article](https://learn.microsoft.com/en-us/microsoft-365/admin/add-users/restore-user).
* For Exchange Online, if the user account is permanently deleted, Microsoft retains the inactive mailbox for a set time. To restore the inactive mailbox, you must convert it to a new, active mailbox that is linked to a new user. For details, see [this Microsoft article](https://learn.microsoft.com/en-us/purview/recover-an-inactive-mailbox). Once you convert the inactive mailbox to an active one, remove the deleted user from the backup policy. Then, add the new user with the linked active mailbox to the backup policy.
* For OneDrive for Business, you can restore the OneDrive to the original location. Once restored, the OneDrive is in an "orphaned" state. For details on how to connect the OneDrive to a user, see [this Microsoft article](https://learn.microsoft.com/en-us/sharepoint/troubleshoot/sharing-and-permissions/fix-site-user-id-mismatch).

Exchange Online

* For Exchange Online restore, only mailbox items that were changed, deleted to the Recoverable Items folder or purged can be restored. New mailbox items are kept. This can lead to unwanted data being restored.
* You cannot back up mailbox draft items and thus cannot restore them.
* For calendar item restore, restoring the organizer copy does not automatically update the attendee copies. It only allows the organizer to send updates for this calendar item in the future. This means that if an attendee has already accepted or declined the meeting, their copy of the calendar item will not be updated to match the restored organizer's copy, unless the organizer explicitly updates the meeting request.
* Items moved to the Deleted Items folder will not be restored. Mailbox users can recover these items themselves by moving them back to the Inbox from the Deleted Items folder.
* If the parent folder of an item has been deleted, the item will be restored to a newly created folder named Recovered Items YYYY-MM-DD, HH:MM.
* The Outlook mailbox folder structure is not backed up. This means that while you perform a mailbox restore with multiple hierarchical folders, the folder structure is not reconstructed when restored. The restored mailbox items are located in a different folder, created by Microsoft.
* Discovery search mailboxes, public folder mailboxes, remote mailboxes and resource mailboxes are not supported.

OneDrive for Business and SharePoint Online

* Restore is only available for cloud root SharePoint sites, as Veeam Data Cloud for Microsoft 365 only backs up cloud root SharePoint sites.

* Subsites are restored at the root SharePoint site level and are not available in the SharePoint restore tab. To restore a subsite, you must restore the root SharePoint site.
* Personal sites are included in the OneDrive for Business restore and are not available in the SharePoint restore tab.

* If there is old "My Site" data before the transition to OneDrive for Business, the data will also be protected by the OneDrive for Business backup policy.

* The following SharePoint site templates are not supported:

* SiteConstants.TemplateId\_ReviewCenter
* SiteConstants.TemplateId\_FunSite
* SiteConstants.TemplateId\_PolicyCenter
* SiteConstants.TemplateId\_TestSite
* SiteConstants.TemplateId\_CentralAdminSite
* SiteConstants.TemplateId\_MySiteHost
* SiteConstants.TemplateId\_TenantAdmin
* SiteConstants.TemplateId\_CSPContainer

For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/microsoft-365/backup/backup-faq?view=o365-worldwide#can-i-backup-every-type-of-sharepoint-site).

* Site search is case-sensitive and is a prefix-type search.
* Restore will fail for OneDrive for Business accounts or SharePoint Online sites under the strict SEC 17a-4(f) hold policy. You must remove the hold before you perform restore.
* If you rename a tenant, move a tenant or change a SharePoint site URL, you cannot revert those changes when performing restore.
* For OneDrive for Business restore, discovery search mailboxes, shared mailboxes, public folder mailboxes, remote mailboxes and resource mailboxes are not supported.

Page updated 1/8/2026
