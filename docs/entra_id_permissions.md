---
title: "Permissions"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/entra_id_permissions.html"
last_updated: "11/19/2025"
product_version: ""
---

# Permissions

In this article

The accounts that Veeam Data Cloud uses to manage Microsoft Entra ID must be granted the following permissions.

Veeam Data Cloud User Account Permissions

A user account that you plan to use when working with Entra ID tenants in Veeam Data Cloud must have one of the following Veeam Data Cloud roles or role sets assigned:

* OrganizationAdmin.
* OrganizationViewer and at least one of the built-in roles with permission to work with Entra ID tenants. For details, see [Roles](users_roles.md).

Microsoft Entra Roles and Permissions

Veeam Data Cloud requires a Microsoft Entra service principal to add Microsoft Entra ID tenants to Veeam Data Cloud and to back up and restore Microsoft Entra ID data. To allow Veeam Data Cloud to create this service principal, you need to authorize Veeam Data Cloud using your Microsoft Entra ID account with the Global Administrator privileges.

Veeam Data Cloud creates the Microsoft Entra service principal with the following set of permissions:

| API | Permission | Permission display name | Permission type |
| --- | --- | --- | --- |
| Microsoft Graph | AdministrativeUnit.ReadWrite.All | Read and write all administrative units | Application |
| Application.ReadWrite.All | Read and write all applications | Application |
| AppRoleAssignment.ReadWrite.All | Manage app permission grants and app role assignments | Application |
| AuditLog.Read.All | Read all audit log data | Application |
| Directory.ReadWrite.All | Read and write directory data | Application |
| Group.ReadWrite.All | Read and write all groups | Application |
| MailboxSettings.Read | Read all user mailbox settings | Application |
| RoleManagement.ReadWrite.Directory | Read and write all directory RBAC settings | Application |
| User.DeleteRestore.All | Delete and restore all users | Application |
| User.ReadWrite.All | Read and write all users' full profiles | Application |
| User.Read | Sign in and read user profile | Application |
| Policy.Read.All  (required for Conditional Access policies backup) | Read your organization's policies | Application |
| Policy.ReadWrite.ConditionalAccess  (required for Conditional Access policies backup) | Read and write your organization's Conditional Access policies | Application |
| Agreement.Read.All  (required for Conditional Access policies backup) | Read all terms of use agreements | Application |
| DeviceManagementConfiguration.ReadWrite.All  (required for Microsoft Intune policies policies backup) | Read and write Microsoft Intune device configuration and policies | Application |
| Azure Resource Manager | user\_impersonation | Access Azure Resource Manager as organization users | Delegated |

Veeam Data Cloud assigns the Microsoft Entra service principal the following roles:

| Property | Description |
| --- | --- |
| Privileged Authentication Administrator | This role allows Veeam Data Cloud to restore objects that are assigned privileged permissions. |
| User Administrator | This role allows Veeam Data Cloud to restore objects that are assigned privileged permissions. |

Page updated 11/19/2025
