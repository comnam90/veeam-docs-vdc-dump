---
title: "Enabling Microsoft Team Posts Backup"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/m365_enable_team_chats_backup.html"
last_updated: "3/25/2026"
product_version: ""
---

# Enabling Microsoft Team Posts Backup


To create Microsoft Teams backups that include private and shared channels and public channel messages, you must configure the team posts backup settings. Microsoft Teams channels, tabs, files and metadata are protected regardless of whether you enable Microsoft team posts backup or not.

Before You Begin

Before you configure the Microsoft team posts backup, consider the following:

* When you perform backup of Microsoft Teams data, Veeam Data Cloud for Microsoft 365 does not back up the following objects:

* One-on-one and group chats.

For more information about chats in Microsoft Teams, see [this Microsoft article](https://support.microsoft.com/en-us/office/first-things-to-know-about-chat-in-microsoft-teams-88ed0a06-6b59-43a3-8cf7-40c01f2f92f2).

* Audio and video calls.
* Video recordings saved to Microsoft Stream.
* Contacts.
* Calendar: information about meetings and meeting chats.
* Code snippets, audio files and banner notifications in posts.
* Data of applications added as channel tabs (such as Website, Planner, Word, Excel, PowerPoint, Visio, PDF, Document Library, OneNote, SharePoint, Stream, Forms, Power BI, Power Automate and Azure DevOps) and other 3rd party applications if their data does not reside in the SharePoint document library of the team.
* The TeamsMessagesData folder of the group mailbox that belongs to the Microsoft 365 group associated with the backed-up team.

* Microsoft Teams service is not supported for organizations in Microsoft Entra China and legacy Microsoft Entra Germany regions. For more information about Microsoft Entra Germany, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/germany/).
* Team posts backup is not supported for Microsoft 365 organizations in Microsoft Entra China, legacy Germany, US Government DOD and US Government GCC High regions.
* During backup and restore of an archived team, Veeam Data Cloud for Microsoft 365 does not preserve the Make the SharePoint site read-only for team members property of the team on the Microsoft 365 side.

Enabling Team Posts Backup

To enable Microsoft team posts backup, do the following:

1. On the Microsoft 365 page, click the name of the tenant you want to manage.
2. Select Settings.
3. Go to the Microsoft 365 tab.
4. In the Teams Backups section, click Set up Teams Posts.

[![Enabling Team Chats Backup](images/m365_enable_team_chats.webp)](images/m365_enable_team_chats.webp "Enabling Team Chats Backup")

1. In the Set up Teams Posts window, select one of the following:

* Turn on Teams Posts backups for all existing backup policies. The team posts objects will be automatically included to all existing backup policies.
* Manually add Teams Posts to backup policies. You must manually add the team posts objects to existing backup policies. For information on how to edit backup policies, see [Editing Flex Backup Policies](m365_backup_edit_flex.md).

1. Click Finish.

[![Enabling Team Chats Backup](images/m365_enable_team_chats_options.webp)](images/m365_enable_team_chats_options.webp "Enabling Team Chats Backup")

|  |
| --- |
| NOTE |
| If you receive the You cannot enable Teams Posts due to missing required permissions. Please reauthorize your app registration and try again. notification, you must reauthorize Veeam Data Cloud for Microsoft 365. For more information, see [Reauthorizing Veeam Data Cloud for Microsoft 365](m365_settings_reauthorize.md). |

