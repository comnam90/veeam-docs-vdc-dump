---
title: "Microsoft Entra Application Permissions"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_permissions.html"
last_updated: "2/17/2026"
product_version: ""
---

# Microsoft Entra Application Permissions


Veeam Data Cloud for Microsoft 365 uses Microsoft Entra applications to establish and maintain the connection between Veeam Data Cloud for Microsoft 365 and Microsoft 365 organizations, and perform backup and restore of the organization data.

For Veeam Data Cloud for Microsoft 365, Microsoft Entra ID automatically creates the following Enterprise applications (not application registrations) in your tenant:

* Veeam Data Cloud [EMEA, AMER, APJ]

* Veeam Data Cloud Registration [EMEA, AMER, APJ]

* Veeam Data Cloud for Microsoft 365

* Multi-tenant Registration for MBS Billing

Veeam Data Cloud [EMEA, AMER, APJ]

When you log in to Veeam Data Cloud for Microsoft 365 with a Microsoft account for the first time, you must accept the following permissions:

[EMEA, AMER, APJ]

| Permission | Type | Description |
| View your basic profile |  |  |
| openid | Delegated | Allows users to sign in to the app with their work or school accounts and allows the app to see basic user profile information. |
| profile | Delegated | Allows the app to see the basic profile of the users (name, picture, user name, email address). |
| email | Delegated | Allows the app to read the primary email address of the users. |
| Maintain access to data you have given access to |  |  |
| offline\_access | Delegated | Allows the app to see and update the data you gave it access to, even when users are not currently using the app. This does not give the app any additional permissions. |

After you accept the permissions, the Veeam Data Cloud [EMEA, AMER, APJ] Enterprise application is created with those permissions. Veeam Data Cloud for Microsoft 365 uses this Enterprise application to authenticate the users who sign in to Veeam Data Cloud for Microsoft 365 with Microsoft accounts.

When users log in to Veeam Data Cloud for Microsoft 365 for the first time, they must accept the following permissions: profile — View users' basic profile and offline\_access — Maintain access to data you have given it access to.

Veeam Data Cloud Registration [EMEA, AMER, APJ]

When you [add a Microsoft 365 tenant](m365_tenant_add.md) to Veeam Data Cloud for Microsoft 365, if you choose to automatically connect Veeam Data Cloud for Microsoft 365 to Microsoft 365, you must accept the following permissions upon entering the device code:

Registration [EMEA, AMER, APJ]

| Permission | Type | Description |
| Application.Readwrite.All | Delegated | Allows the app to create, read and update application registrations required for backup and restore. |
| AppRoleAssignment.ReadWrite.All | Delegated | Enables assignment of app roles when configuring required access. |
| Directory.ReadWrite.All | Delegated | Allows the app to create and update directory objects needed for registration and configuration. |
| RoleManagement.ReadWrite.Directory | Delegated | Allows managing directory role assignments needed for app registration. |

After you accept the permissions, the Veeam Data Cloud Registration [EMEA, AMER, APJ] Enterprise application is created. Veeam Data Cloud for Microsoft 365 uses this Enterprise application to automatically create the Veeam Data Cloud for Microsoft 365 application registration that is used for backup and restore.

Once you have successfully added a Microsoft 365 tenant to Veeam Data Cloud for Microsoft 365, you can delete the Veeam Data Cloud Registration [EMEA, AMER, APJ] Enterprise application. When using features such as uploading certificates, Veeam Data Cloud for Microsoft 365 will ask for the permissions and create the Veeam Data Cloud Registration [EMEA, AMER, APJ] Enterprise application again.

When you [add a Microsoft 365 tenant](m365_tenant_add.md) to Veeam Data Cloud for Microsoft 365, if you choose to manually connect Veeam Data Cloud for Microsoft 365 to Microsoft 365, the Veeam Data Cloud Registration [EMEA, AMER, APJ] Enterprise application is not created. You must manually create and grant admin consent to the Veeam Data Cloud for Microsoft 365 application registration. For more information on how to create a new application registration, see [this Microsoft article](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/walkthrough-register-app-azure-active-directory).

Veeam Data Cloud for Microsoft 365

When you run your first backup session, the Veeam Data Cloud for Microsoft 365 Enterprise application is created. Veeam Data Cloud for Microsoft 365 uses this Enterprise application for backup and restore purposes.

Multi-tenant Registration for MBS Billing

For Premium, you must (create, if manual connection, and) grant admin consent to a fourth Enterprise application, called Multi-tenant Registration for MBS Billing. To view the required permissions for this Enterprise application, see [Express or Premium Permissions for Microsoft Entra Application](#express).

Required User Account Roles for Microsoft Entra Application

The user account that the Microsoft Entra application uses to log in to Microsoft 365 must be assigned the following roles:

* Global Administrator — required for adding organizations, creating Microsoft Entra application for the Microsoft Azure service account.
* Owner — required for backing up public folder mailboxes.

If you plan to back up public folder mailboxes, this user account must have a valid Exchange Online license and an active mailbox within the Microsoft 365 organization.

|  |
| --- |
| NOTE |
| Veeam Data Cloud for Microsoft 365 does not support Microsoft Entra Privileged Identity Management. |

Required Permissions for Microsoft Entra Application

In this section you can find a list of permissions for Microsoft Entra applications that are granted automatically by Veeam Data Cloud for Microsoft 365 when you add your organization during onboarding.

If you prefer to manually add your organization, make sure to manually grant all the listed permissions.

The Microsoft Entra application requires the Global Reader role. To learn how to grant the Global Reader role to the Microsoft Entra application, see [Granting Global Reader Role to Microsoft Entra Application](#globalreader).

Permissions for Backup

All listed permissions are of the Application type.

Permissions for Backup

| API | Permission name | Exchange Online | SharePoint Online and OneDrive for Business | Microsoft Teams | Description |
| Microsoft Graph | Directory.Read.All | ✔ | ✔ | ✔ | Querying Microsoft Entra ID for organization properties, the list of users and groups and their properties. |
| Group.Read.All | ✔ | ✔ | ✔ | Querying Microsoft Entra ID for the list of groups and group sites. |
| Sites.Read.All |  | ✔ | ✔ | Querying Microsoft Entra ID for the list of sites and getting download URLs for files and their versions. |
| TeamSettings.ReadWrite.All |  |  | ✔ | Accessing archived teams. |
| ChannelMessage.Read.All |  |  | ✔ | Accessing Microsoft Teams public channel messages. |
| ChannelMember.Read.All |  |  | ✔ | Accessing Microsoft Teams private and shared channels. |
| Sites.Read.All |  | ✔ | ✔ | Retrieving the list of sites when creating a backup policy, during backup and restore and for objects caching. |
| Reports.Read.All | ✔ | ✔ | ✔ | Building the Veeam Data Cloud dashboard. |
| Office 365 Exchange Online1 | full\_access\_as\_app | ✔ |  | ✔ | Reading mailboxes content. |
| Exchange.ManageAsApp | ✔ |  |  | Accessing Exchange Online PowerShell to do the following:   * Back up public folder and discovery search mailboxes. * Determine object type for shared mailboxes as Shared Mailbox.   Note: This permission is required to back up public folders and discovery search mailboxes. This permission works along with the Global Reader role granted to the Microsoft Entra application. For more information, see [Granting Global Reader Role to Microsoft Entra Application](#globalreader). |
| Office 365 SharePoint Online | Sites.FullControl.All |  | ✔ | ✔ | Reading SharePoint sites and OneDrive accounts content. |
| User.Read.All |  | ✔ | ✔ | Reading OneDrive accounts (getting site IDs).  Note: This permission is not used to back up Microsoft Teams data, but you must grant it along with SharePoint Online and OneDrive for Business permission to add a Microsoft 365 organization successfully. |

1You can check permissions for Office 365 Exchange Online API. For more information, see [Checking Permissions for Office 365 Exchange Online API](m365_check_perms_for_o365_exchange_api.md).

Permissions for Restore

All listed permissions are of the Application type.

Permissions for Restore

| API | Permission name | Exchange Online | SharePoint Online and OneDrive for Business | Microsoft Teams | Description |
| Microsoft Graph | Directory.Read.All | ✔ |  | ✔ | Querying Microsoft Entra ID for organization properties, the list of users and groups and their properties. |
| Group.ReadWrite.All |  | ✔ | ✔ | Recreating in Microsoft Entra ID an associated group in case of a deleted team site restore. |
| Sites.Read.All |  | ✔ | ✔ | Retrieving the list of sites when creating a backup policy, during backup and restore and for objects caching. |
| Directory.ReadWrite.All |  | ✔ | ✔ | When creating or accessing a M365 group for a Multi-Geo tenant in case of teams or sites restore:   * Setting the preferred data location. * Creating sites that have Microsoft Teams template. |
| Files.ReadWrite.All |  |  | ✔ | Reading the current state and restoring files of Microsoft Teams shared channels. |
| ChannelMember.ReadWrite.All |  |  | ✔ | Reading the current state and restoring Microsoft Teams private and shared channels. |
| Office 365 Exchange Online1 | full\_access\_as\_app | ✔ |  | ✔ | Restoring mailboxes content. |
| Office 365 SharePoint Online | Sites.FullControl.All |  | ✔ | ✔ | Reading and restoring SharePoint sites and OneDrive accounts content. |
| User.Read.All |  | ✔ | ✔ | Reading OneDrive accounts (getting site IDs).  Note: This permission is not used to back up Microsoft Teams data, but you must grant it along with SharePoint Online and OneDrive for Business permission to add a Microsoft 365 organization successfully. |

1You can check permissions for Office 365 Exchange Online API. For more information, see [Checking Permissions for Office 365 Exchange Online API](m365_check_perms_for_o365_exchange_api.md).

|  |
| --- |
| Note |
| To restore data using Microsoft Entra application, make sure that you configure the Microsoft Entra application settings. For more information, see [Configuring Microsoft Entra Application Settings](m365_configuring_ms_entra_app_settings.md). |

Premium Permissions for Microsoft Entra Application

If you are under the Premium plan, the following additional permissions are required for the Microsoft Entra application:

Premium Permissions for Microsoft Entra Application

| API | Permission name | Application type | Delegated type | Description |
| Microsoft Graph | BackupRestore-Control.ReadWrite.All | ✔ | ✔ | Updating or reading the status of the Microsoft 365 backup service.  Note: This is needed to back up and restore data through Microsoft Backup Storage and to manage the backup and restore service from the Microsoft side. |
| BackupRestore-Configuration.ReadWrite.All | ✔ | ✔ | Reading and editing backup configuration policies. |
| BackupRestore-Restore.ReadWrite.All | ✔ |  | Reading restore all sessions and starting restore sessions from backups. |
| BackupRestore-Search.Read.All | ✔ |  | Searching for metadata properties in backup snapshots. |
| BackupRestore-Monitor.Read.All | ✔ |  | Reading all monitoring, quota and billing information for the tenant. |
| Group.Read.All | ✔ |  | Reading all groups.  Note: This is needed to resolve logic related to a group or the entire workload backup. Additionally, logic must pull details about items, sites, OneDrives, mailboxes and users it handles. |
| Sites.Read.All | ✔ |  | Reading items in all site collections. |
| Directory.Read.All | ✔ |  | Reading directory data. |
| User.Read | ✔ |  | Signing in and reading user profile. |

Granting Global Reader Role to Microsoft Entra Application

Veeam Data Cloud for Microsoft 365 needs access to Exchange Online PowerShell for backup. To access Exchange Online PowerShell, Microsoft Entra application requires the Global Reader role.

To grant the Global Reader role to the Microsoft Entra application, do the following:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/).
2. Go to Identity > Roles & admins > Roles & admins.
3. In the Administrative roles list, find the Global Reader role and click on it.
4. In the Global Reader window, click Add assignments. The Add assignments wizard runs.
5. In the Select member(s) section, click the link.
6. In the Select a member window, select the Microsoft Entra application in the list and click Select. The selected application will appear in the Selected member(s) list.
7. Click Next and then click Assign to finish working with the wizard.

