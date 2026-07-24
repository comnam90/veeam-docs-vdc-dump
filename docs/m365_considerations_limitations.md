---
title: "Considerations and Limitations"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_considerations_limitations.html"
last_updated: "2026"
product_version: ""
---

# Considerations and Limitations


This section lists considerations, known limitations and best practices in Veeam Data Cloud for Microsoft 365.

Supported Microsoft Organizations

Veeam Data Cloud for Microsoft 365 supports the following Microsoft Exchange Online and Microsoft SharePoint Online organization versions:

* Microsoft 365 Exchange Online

[Microsoft 365 and Office 365 service families](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options#service-families-and-plans), standalone services and plans for Business, Education, and Government\* hosted by Microsoft are supported. For more information about system requirements and limitations for Microsoft 365, see [this Microsoft article](https://www.microsoft.com/en-us/microsoft-365/microsoft-365-and-office-resources#Office365forBEG).

* Microsoft 365 SharePoint Online

[Microsoft 365 and Office 365 service families](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options#service-families-and-plans), standalone services and plans for Business, Education, and Government\* hosted by Microsoft are supported. For more information about system requirements and limitations for Microsoft 365, see [this Microsoft article](https://www.microsoft.com/en-us/microsoft-365/microsoft-365-and-office-resources#Office365forBEG).

\*Government support is experimental. For more information, see [this Veeam KB article](https://www.veeam.com/kb2976).

Backup Best Practices

Before you back up your data, consider the listed recommendations and best practices for Veeam Data Cloud for Microsoft 365. Then, depending on your license plan, create new backup policies. For more information, see [Creating Flex Backup Policies](m365_backup_create_flex.md) and [Creating Express Backup Policies](m365_backup_create_express.md).

Number of Backup Policies

You can configure backup policies based on Users, Groups, Sites, Teams and Organizations (entire or partial).

If you configure a single backup policy for all your data, there are challenges due to risks like a single point of failure, management complexity, backup duration, and restore issues.

As a best practice, in most cases, it is recommended to create 2 backup policies.

For example, you can create a backup policy for Exchange Online and another backup policy for the rest of your data:

* Backup Policy 1: Mailboxes and Archive mailboxes
* Backup Policy 2: OneDrive, SharePoint Online and Teams

In the case where you have more complex backup rules and do not back up your entire organization, it is recommended to split your backups into 3 backup policies:

* Backup Policy 1: Mailboxes and Archive mailboxes
* Backup Policy 2: OneDrive
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

Microsoft Throttling

During your initial full backup, Microsoft may be throttling your traffic due to the high load of Microsoft Exchange data. To mitigate this, you can temporarily disable Microsoft Exchange throttling in the Microsoft 365 admin center. For detailed instructions on how to disable Microsoft throttling, see [this Veeam KB article](https://www.veeam.com/kb4198).

Even after Microsoft throttling is disabled, Microsoft still throttles traffic and limits to processing 150 MB for each mailbox every 5 minutes.

Executing Backup Policies

Avoid running more than one or 2 backup policies at the same time.

OneDrive, SharePoint, and Teams are closely connected under the hood. When you run their backup policies at the same time, Microsoft 365 can slow down or break your backups. Schedule these at different times to avoid issues.

Exchange backup policies can run at the same time as other services backup policies without issue.

Backup Policies Start Time

Backup policies start times are dynamically managed to optimize system performance and ensure reliable service. Backups will always meet the agreed RPOs.

Editing Backup Policies

For information on how to edit existing backup policies, see [Editing Flex Backup Policies](m365_backup_edit_flex.md) and [Editing Express Backup Policies](m365_backup_edit_express.md).

|  |
| --- |
| NOTE |
| When you add a new user to a backup policy, Veeam Data Cloud for Microsoft 365 automatically attempts to add all child objects of the user data (Mailbox, Archive Mailbox, OneDrive, Personal Site) to the backup policy. If your backup policies are split into Exchange and Other items backups, you will need to edit the user and deselect the child objects you want to remove. |

Backup

Before you back up your data, consider the listed recommendations and best practices for Veeam Data Cloud for Microsoft 365.

General Backup Considerations

* Backup of a Microsoft 365 tenant organization is not supported if the initial domain of the organization was changed.
* Backup of dynamic distribution groups is not supported. Members of dynamic distribution groups cannot be resolved. Dynamic Entra ID groups can be used instead. For more information, see [Dynamic Entra ID Groups](#entragroups).
* Microsoft Entra Privileged Identity Management is not supported.
* Backup is not supported for Microsoft organizations in US Government GCC High regions.

Flex Backup Considerations

Exchange Online Backup

* To back up user mailboxes, make sure that a mailbox has a valid Microsoft 365 license.
* Backup and restore of public folders requires the Variable License Model.
* To back up public folder mailboxes, a valid Microsoft Exchange Online license and an active mailbox within the Microsoft 365 organization is required.
* Veeam Data Cloud for Microsoft 365 only backs up and restores public folders located under the IPM\_SUBTREE folder.
* When backing up public mailboxes, only select the root public mailbox. Any child folders of the selected public mailbox will be backed up as well.
* When backing up Microsoft Exchange Online mailboxes, Veeam Data Cloud does not create a new version of an item if the Read/Unread property of such item was changed. That said, the Read/Unread property of each of the backed-up items always remains exactly the same as it was during the initial backup.
* Veeam Data Cloud for Microsoft 365 does not back up permissions for sharing mailbox folders and calendar.
* Veeam Data Cloud for Microsoft 365 does not support backup of dynamic distribution groups. Members of dynamic distribution groups cannot be resolved.
* Resource/equipment mailboxes are presented and available for backup with the general User type.
* Microsoft 365 group owner data backup is not supported if the group owner is not a member of the Group.
* The Type property for discovery search, resource and equipment mailboxes is not resolved. Such mailboxes are available for backup with the general User type.
* Grouping of lists with To Do tasks is ignored during backup.
* The TeamsMessagesData folder is not supported for backup.

OneDrive and SharePoint Online Backup

* To back up SharePoint Online and OneDrive objects, make sure that a user account has a valid Microsoft 365 license with a SharePoint Online plan enabled.
* If a SharePoint item has several versions with identical owshiddenversion values, only the latest version of this item is backed up. All the other versions are skipped from processing.
* SharePoint web parts can only be backed up if their ‘exportmode’ property is enabled. Non-exportable web parts are not supported. For more information, see [this Veeam KB article](https://www.veeam.com/kb3146).
* SharePoint web parts export mode can only be changed automatically if such type of a property is supported and can be modified in the source SharePoint Online site or OneDrive account.
* To back up and restore SharePoint sites with certain specific templates, such as Business Intelligence Center, Product Catalog, and Visio Process Repository, an organization must have a valid SharePoint license.
* SharePoint Online personal site and OneDrive account backup will fail if the site has reached its storage space quota and if your service account is not granted with the Site Collection Administrator (site admin) permissions for this site.
* A backup of a SharePoint site created within the last 24 hours before the backup policy run may be performed with an error because of the time required for its configuration update.
* Version history backup is not supported for the Microsoft SharePoint .aspx web pages.
* Backup of the SharePoint App Store applications added to a site is not supported.
* Backup of the SharePoint App Store applications that use JavaScript redirects is not supported.
* In organizations with the renamed SharePoint domain, sites explicitly selected for backup need to be re-added to a backup policy.
* After a SharePoint site URL has been changed, a site with an old URL can still be selected for backup. Processing of a site with an old URL will fail with the warning: Site was moved to another URL. As a workaround, to suppress the unwanted warnings, you can exclude these sites from a backup policy.
* Backup of personal SharePoint sites that use the SPSPERS#1–SPSPERS#10 templates and are not associated with any user fails with the warning: Cannot resolve personal site owner. The user may not have a valid Microsoft Office 365 license with SharePoint plan enabled.
* Backup of a SharePoint team site that has the information barriers mode set to Implicit fails with error: Exception from HRESULT: 0x87FA0080.
* Items count in a backed-up OneDrive folder is not updated on incremental backup policy runs. When exploring OneDrive backups, you will see the item count as it was at the time of the first full backup run.
* When you perform backup of SharePoint data, Veeam Data Cloud for Microsoft 365 does not back up the following objects:

* External SharePoint lists

For more information, see [this Microsoft article](https://support.microsoft.com/en-us/office/differences-between-native-and-external-lists-6601eda9-b722-4bf8-a2bf-ce25cf3d2fd0).

* SharePoint folder attachments
* SharePoint site collection recycle bin
* SharePoint sites created by Microsoft Loop
* Archived SharePoint sites
* SharePoint sites with blocked access
* Sensitivity labels applied to SharePoint sites and lists
* Comments on SharePoint list items
* A personal view of a SharePoint list
* Communication site owners

Teams Backup

* As part of Microsoft Teams data backup, Veeam Data Cloud backs up only the following types of channel tabs: Website, Planner, Word, Excel, PowerPoint, Visio, PDF, Document Library, OneNote, SharePoint, Stream, Forms, Power BI, Power Automate (ex Flow) and Azure DevOps.
* When you perform backup of Microsoft Teams data, Veeam Data Cloud for Microsoft 365 does not back up the following objects:

* One-on-one and group posts.

For more information about posts in Microsoft Teams, see [this Microsoft article](https://support.microsoft.com/en-us/office/first-things-to-know-about-chat-in-microsoft-teams-88ed0a06-6b59-43a3-8cf7-40c01f2f92f2).

* Audio and video calls, meeting notes and meeting posts.
* Video recordings saved to Microsoft Stream.
* Contacts.
* Tags.
* Calendar: information about meetings and meeting posts.
* Code snippets, audio files and banner notifications in posts.
* Data of applications added as channel tabs (such as Website, Planner, Word, Excel, PowerPoint, Visio, PDF, Document Library, OneNote, SharePoint, Stream, Forms, Power BI, Power Automate and Azure DevOps) and other 3rd party applications if their data does not reside in the SharePoint document library of the team.
* The TeamsMessagesData folder of the group mailbox that belongs to the Microsoft 365 group associated with the backed-up team.
* Wiki tabs.
* The ‘Allow members to upload custom apps’ team property.
* Instant meetings (Meet Now) and scheduled meeting cards.
* Team channel settings.
* Team tabs linked to files stored in personal OneDrive accounts.

* Microsoft Teams service is not supported for organizations in Microsoft Entra China and legacy Microsoft Entra Germany regions. For more information about Microsoft Entra Germany, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/germany/).
* Team posts backup is not supported for Microsoft 365 organizations in Microsoft Entra China, Germany and US Government regions.
* During backup and restore of an archived team, Veeam Data Cloud for Microsoft 365 does not preserve the Make the SharePoint site read-only for team members property of the team on the Microsoft 365 side.
* Veeam Data Cloud for Microsoft 365 does not back up the TeamsMessagesData folder.
* Backup of a team linked to a SharePoint site that has the information barriers mode set to Implicit fails with error: Exception from HRESULT: 0x87FA0080.
* The latest version of a Teams channel message with an attachment may not be returned by the Microsoft Graph Teams Export APIs, and consequently, such a message may be missing from a backup. This behavior is due to the current limitations of the Microsoft Graph Teams Export APIs.
* Backup of shared channels is not supported for Microsoft 365 organizations in the China region. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/graph/teamwork-national-cloud-differences#implementation-differences-in-microsoft-graph-for-microsoft-graph-china-operated-by-21vianet).

Express Backup Considerations

* Backup of mailbox draft items is not supported.

* For Outlook backup policies, you can back up user mailboxes and shared mailboxes. Discovery search mailboxes, public folder mailboxes, remote mailboxes and resource mailboxes are not supported. Veeam Data Cloud will display the following warning when you add an unsupported mailbox to a backup policy: Mailbox cannot be added to policy since the recipient type is not supported.

* For SharePoint backup policies, Veeam Data Cloud for Microsoft 365 only backs up root SharePoint sites.

Restore

Before you restore your data, consider the listed recommendations and best practices for Veeam Data Cloud for Microsoft 365.

General Restore Considerations

* [Data restore methods](m365_restore.md) apply to Microsoft Outlook mailboxes, entire Microsoft OneDrives and Microsoft SharePoint sites. For other types of Outlook, OneDrive and SharePoint objects, you do not need to select the restore method.
* Backup and restore of Microsoft Teams data is available for Flex-based backup policies only. Users can restore Teams data flexibly and do not need to select the restore method.
* Smaller restores may be quicker with Flex; benefits of Express are best realized with large restores.
* Veeam Data Cloud for Microsoft 365 supports a maximum of 2 restore operations in parallel. To raise this limit in urgent cases, contact Veeam Customer Support.
* Restore of OneNote notebooks from backups of Microsoft SharePoint Online, Microsoft OneDrive and Microsoft Teams data is not supported.

As a workaround, you can download the required OneNote file to your computer and then upload this OneNote file to your OneDrive or SharePoint site.

* Preservation Hold items are not available for restore under the Foundation and Advanced plans.
* The maximum size for download in background of OneDrive and SharePoint Online data is 200 GB.

Flex Restore Considerations

Exchange Online Restore

* Mailboxes can be restored only to mailboxes of the same type. For example, a user mailbox to a user mailbox, an archive mailbox to an archive mailbox.

* Veeam Data Cloud for Microsoft 365 only restores public folders located under the IPM\_SUBTREE folder.
* Search results for queries built with the ‘is not’ and ‘doesn’t contain’ criteria will not include emails where the corresponding fields are empty.
* Restore of the Team Chat and TeamsMessagesData folders is not supported.
* Restoring an entire mailbox to a specified folder in Exchange Online results in the duplication of Tasks, Contacts, and Calendars content.

OneDrive Restore

* Restore of OneNote notebooks from backups of Microsoft OneDrive data is not supported.
* Restoring Shortcuts to shared folders is not supported.
* Item size is displayed as zero bytes if this item was being uploaded to OneDrive during backup.

SharePoint Online Restore

Status Restore Limitations

* If a document or an item was in the Check Out state when the backup was created, the last version of the item will not be restored to the target SharePoint and will be available for viewing only. Previous versions (if any) will be restored.
* If automatic declaration of items as records was originally applied to the list item, the relevant status will not be preserved. Instead, the restored item status will be set in accordance with the target list or target library content approval workflow.
* If the On Hold status was originally applied to the list item, this item will not be restored.
* The approval status of SharePoint items of the Document Set type is restored to Pending if an item is restored to another location.

Documents, Libraries and Lists Restore

* Versioning settings of SharePoint lists are not preserved during restore.
* Restoring Generic List and Pages Library may fail with the No content type 'XXX' found in web YYY error.
* The Created By field of restored documents is updated with the account performing restore.
* Some values of the Rating Settings of Discussion lists are not restored.
* When you restore items to a library or list that has been renamed, the items are restored to the renamed library or list. The name of the library or list is not re-created after the restore. For example, you renamed library\_1 to library\_2. You restore a folder from the Veeam Data Cloud backup of library\_1. The folder is restored and is now part of library\_2.
* Restore of sensitivity labels applied to SharePoint lists is not supported.
* If your SharePoint file history maintains both major and minor versions, restoring a specific major file version creates two files: one preserving the backup version and another incremented to a minor version. The preserved version has the Modified and Modified By properties different from the backup, while the incremented version retains the backup property values. This behavior is expected and results from Microsoft API specifics.
* Hidden and unsupported Microsoft SharePoint lists are not available for restore. For more information, see [Unsupported SharePoint Lists](m365_considerations_unsupported_sharepoint_lists.md).
* Information Rights Management (IRM) settings for SharePoint lists and libraries are not preserved upon restore.
* Shortcuts to shared folders are not supported for restore.
* A SharePoint item with minor versions is restored with major versions if the target library or list is set for major versions only.
* A SharePoint item might be incompletely restored to another location, if this item has references to other items in its original location.
* Restore of a folder named Folder and the items within it to a new location fails with the warning: A file or folder with the name %URL% already exists.

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
* A field value in a list column changes to the default after restore, if the field value has not been specified.
* Managed Metadata columns are not supported for restore.
* Managed Metadata columns are displayed incorrectly after restoring SharePoint list items.

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

* Before restoring team sites, make sure that the user account used for authorization has access to the root SharePoint site of the tenant organization.
* When restoring team sites, Veeam Data Cloud for Microsoft 365 does not restore team site owners or Microsoft 365 group members.
* If you plan to restore SharePoint site pages, consider that Veeam Data Cloud for Microsoft 365 does not support the restore of items that are not stored in the SharePoint content database (in particular, pages, page references and items based on default templates). Such items cannot be restored, except for data from Wiki Content (text and images), which is stored in the database. Thus, site pages that contain only text and images can be restored and displayed properly.
* The SharePoint web part customized template cannot be preserved upon a restore. All web parts will be restored with the default template.

* When restoring a site, make sure the target site already exists in the target location; Veeam Data Cloud for Microsoft 365 does not create sites.

* SharePoint root site node restore is not supported if only subsites of this root are included in a backup. The node is displayed and accessible for restore in Veeam Data Cloud, but the restore will finish with a new web part created and a warning that no master page is available for this web part.
* SharePoint App Store applications restore is not supported.
* SharePoint Team site restore to another location is not supported for the STS#0 and STS#3 site templates.
* SharePoint site custom RSS settings are not preserved upon site restore. RSS settings are restored with the default configuration.
* Restore of custom apps added to a SharePoint site from the organization’s App Catalog is not supported.
* SharePoint site group settings are not preserved upon site restore. Group settings are restored with the default configuration.
* Custom SharePoint site templates are not preserved upon site restore.
* A personal site is restored with errors if the ‘Add And Customize Pages’ permission for the user is set to ‘Deny’. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/sharepoint/allow-or-prevent-custom-script).
* Restore of personal sites to an organization where the Custom Scripts option is disabled for personal sites is not supported.
* Restore of a personal site to another location is not supported if this user account does not exist in the target organization.
* Restore of a subsite to another organization fails if this subsite uses a template that does not exist in the target organization.
* Site collection features may not be preserved upon a site restore to another organization. After restore, such features can be activated for a subsite manually in Microsoft 365.
* In a site URL, a SharePoint domain is changed to the target organization after the site restore to another location.
* Restoring SharePoint sites created for Teams private and shared channels fails with the error: Web template not found: TEAMCHANNEL#1 if these sites are restored to a different location or to their original location where the parent site no longer exists.
* Restoring master pages and custom Style Library items to SharePoint sites with the DenyAddAndCustomizePages restriction enabled is not supported. Other content types may be affected as well. This is a Microsoft limitation and SharePoint does not allow customizations to be written to sites where it is active. Note that this restriction is enabled permanently by default on OneDrive personal sites.

Teams Restore

* You can restore Microsoft Teams data to the original organization only.
* Veeam Data Cloud for Microsoft 365 does not change roles for team owners during restore. For example, you create a backup of your organization, and then change the role for a team member from Member to Owner. In this case, if you restore this team member from the backup, Veeam Data Cloud for Microsoft 365 will not set their role to Member.
* Restore of OneNote notebooks from backups of Microsoft Teams data is not supported.
* When restoring a channel tab, Veeam Data Cloud for Microsoft 365 does not preserve the relation between the link to a file published on the tab and the file itself. You will need to link the tab to the file manually after restore. This limitation does not apply to the scenario where you restore an entire team.
* Veeam Data Cloud for Microsoft 365 does not restore posts to their original location in the team channel. Instead, Veeam Data Cloud for Microsoft 365 exports posts to a file of the HTML format, creates a separate tab in the original channel and attaches the HTML file to this tab.
* If a user never opened the Files tab of a team channel in Microsoft Teams before data backup, files from this tab are not displayed in Veeam Data Cloud for Microsoft 365.
* When restoring a channel, Veeam Data Cloud for Microsoft 365 cannot rename this channel.
* Before restoring teams data, make sure that the user account used for authorization has access to the root SharePoint site of the tenant organization.

* During backup and restore of an archived team, Veeam Data Cloud for Microsoft 365 does not preserve the Make the SharePoint site read-only for team members property of the team on the Microsoft 365 side.
* When restoring a deleted team, a renamed General channel and its contents are not restored. A new empty General channel is created during team restoration. To recover the renamed General channel, restore it separately after the team is restored. The data will not be merged into the existing General channel.
* When restoring team posts, the post creation or modification timestamp is converted to the locale of the back-end server in your Veeam Data Cloud for Microsoft 365 region.

* Teams group settings are restored as default.
* In Veeam Data Cloud Teams restore, team guest members are shown as regular members. For restore, guest membership status is preserved.
* Some channels may be skipped during the restore if the total number of restored channels plus the existing channels (including deleted) in the target team exceeds 200. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/microsoftteams/limits-specifications-teams).
* An entire team restore fails with the error The directory object quota limit for the Tenant has been exceeded, if the number of teams (including archived teams) in this Microsoft 365 organization exceeds 500,000. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).
* For a team with 100 owners, backup and restore fails with the error: Unable to perform operation as '101' would exceed the maximum quota count '100' for forward-link 'owners'. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).
* Headlines of announcement posts are not shown in the Posts view of Veeam Data Cloud. Subheadings of announcement posts are shown in the Subject field.
* Restore of a tab with more than 127 characters in its name fails with the error: DisplayName is too long.
* Restore of a team with more than 127 characters in its name fails with the error: Resource provisioning is in progress. Please try again.
* Teams objects restore fails if the team site cannot be accessed.
* Long channel names are cut to 31 characters after restoring to include the restore timestamp and fit the maximum of 50 allowed characters.
* Restoring a team within less than 10 minutes from its deletion may fail with the error: Failed to restore Team: The object id "%value%" is invalid.
* Team posts restore fails with the error: App id com.microsoft.teamspace.tab.web needs to be installed to the scope … and be in an unblocked state to install/update a tab, if the WebSite Teams App has been manually blocked through the Teams Admin Center.
* Team posts are displayed as deleted and with empty content, if in the production environment a channel with these posts has been deleted and then restored natively through Microsoft Teams tools.
* Restore of a deleted private Teams channel may fail with the error: No active channel found with channel id: %ID%. This issue is caused by the behavior of Microsoft Graph API and may occur if a tab is restored immediately after restoring the private channel.
* The author name is displayed incorrectly for Teams channel messages with scheduled meetings. This issue is caused by the incorrect displayName parameter returned by Microsoft Graph APIs.
* Restore of files belonging to Teams channels of different types is not supported.
* Deleted Teams channel messages are displayed using the Show deleted items option, but restore actions cannot be performed to these items.

Express Restore Considerations

General Express Restore Considerations

* Veeam Data Cloud for Microsoft 365 replaces data in the original location with the data from the backup. For example, if a user is making edits on a SharePoint site and you restore it to a previous state, the user will lose their edits.
* When you create a backup policy for an Exchange Online mailbox, OneDrive account or SharePoint Online site, Veeam Data Cloud for Microsoft 365 starts generating restore points.

* For Exchange Online, the restore points are created every 10 minutes. The retention period for these restore points is 52 weeks.
* For OneDrive and SharePoint Online, the restore points are created every 10 minutes. The retention period for these restore points is 2 weeks. In addition, weekly restore points are created once a week. The retention period for these restore points is 50 weeks.

For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/microsoft-365/backup/backup-restore-data?view=o365-worldwide&tabs=exchange#considerations-when-using-restore).

|  |
| --- |
| NOTE |
| The 52 and 50 weeks of retention are not applicable once a tenant is no longer under Express backup protection. When a tenant is offboarded, the protected data will be preserved for 90 days after the date of offboarding, and then the data will be deleted. |

* To restore an Exchange Online mailbox or OneDrive account for a user who is deleted from Microsoft Entra ID, do the following:

* If the user has been deleted within the past 30 days, restore the user based on the instructions in [this Microsoft article](https://learn.microsoft.com/en-us/microsoft-365/admin/add-users/restore-user).
* For Exchange Online, if the user account is permanently deleted, Microsoft retains the inactive mailbox for a set time. To restore the inactive mailbox, you must convert it to a new, active mailbox that is linked to a new user. For details, see [this Microsoft article](https://learn.microsoft.com/en-us/purview/recover-an-inactive-mailbox). Once you convert the inactive mailbox to an active one, remove the deleted user from the backup policy. Then, add the new user with the linked active mailbox to the backup policy.
* For OneDrive, you can restore the OneDrive to the original location. Once restored, the OneDrive is in an "orphaned" state. For details on how to connect the OneDrive to a user, see [this Microsoft article](https://learn.microsoft.com/en-us/sharepoint/troubleshoot/sharing-and-permissions/fix-site-user-id-mismatch).

Exchange Online Express Restore

* For Exchange Online restore, only mailbox items that were changed, deleted to the Recoverable Items folder or purged can be restored. New mailbox items are kept. This can lead to unwanted data being restored.
* You cannot back up mailbox draft items and thus cannot restore them.
* For calendar item restore, restoring the organizer copy does not automatically update the attendee copies. It only allows the organizer to send updates for this calendar item in the future. This means that if an attendee has already accepted or declined the meeting, their copy of the calendar item will not be updated to match the restored organizer's copy, unless the organizer explicitly updates the meeting request.
* Items moved to the Deleted Items folder will not be restored. Mailbox users can recover these items themselves by moving them back to the Inbox from the Deleted Items folder.
* If the parent folder of an item has been deleted, the item will be restored to a newly created folder named Recovered Items YYYY-MM-DD, HH:MM.
* The Outlook mailbox folder structure is not backed up. This means that while you perform a mailbox restore with multiple hierarchical folders, the folder structure is not reconstructed when restored. The restored mailbox items are located in a different folder, created by Microsoft.
* Discovery search mailboxes, public folder mailboxes, remote mailboxes and resource mailboxes are not supported. Veeam Data Cloud will display the following warning when you add an unsupported mailbox to a backup policy: Mailbox cannot be added to policy since the recipient type is not supported.

OneDrive and SharePoint Online Express Restore

* Restore is only available for cloud root SharePoint sites, as Veeam Data Cloud for Microsoft 365 only backs up cloud root SharePoint sites.

* Subsites are restored at the root SharePoint site level and are not available in the SharePoint restore tab. To restore a subsite, you must restore the root SharePoint site.
* Personal sites are included in the OneDrive restore and are not available in the SharePoint restore tab.

* If there is old "My Site" data before the transition to OneDrive, the data will also be protected by the OneDrive backup policy.

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
* Restore will fail for OneDrive accounts or SharePoint Online sites under the strict SEC 17a-4(f) hold policy. You must remove the hold before you perform restore.
* If you rename a tenant, move a tenant or change a SharePoint site URL, you cannot revert those changes when performing restore.
* For OneDrive restore, discovery search mailboxes, shared mailboxes, public folder mailboxes, remote mailboxes and resource mailboxes are not supported.

Page updated 2026-07-24
