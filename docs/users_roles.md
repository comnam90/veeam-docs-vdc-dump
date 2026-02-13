---
title: "Roles"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/users_roles.html"
last_updated: "2/11/2026"
product_version: ""
---

# Roles


Veeam Data Cloud provides built-in roles that you can assign to Veeam Data Cloud users. User roles define the operations that the user can perform, including backup, restore and user management. You can assign a role with access to your entire Veeam Data Cloud organization or a specific workload, such as Microsoft Entra ID, Salesforce, Microsoft 365, or Microsoft Azure.

To view the list of available roles, click the settings icon in the top-right corner and then select Roles.

Veeam Data Cloud Organization Roles

You can assign the following roles to users to allow them to work with your Veeam Data Cloud organization.

* OrganizationAdmin — can manage users and perform all configuration actions, backup and restore operations. This role gives a user access to all workloads and tenants. The first user invited to your Veeam Data Cloud organization becomes OrganizationAdmin.
* OrganizationViewer — can view the lists of Veeam Data Cloud users and tenants. This role is granted for all Veeam Data Cloud users.

Entra ID Roles

You can assign the following roles to users working with Veeam Data Cloud for Microsoft Entra ID:

* EntraID:Administrator — can add tenants and perform all configuration actions, backup and restore operations. You can limit access to specific Entra ID tenants when assigning this role.

To prohibit a user with the EntraID:Administrator role to add tenants, limit access to specific Entra ID tenants when assigning this role and assign the user the OrganizationViewer role.

* EntraID:SettingsAdministrator — can manage tenant settings. You can limit access to specific Entra ID tenants when assigning this role.
* EntraID:RestoreAdministrator — can only perform restore operations. You can limit access to specific Entra ID tenants when assigning this role.
* EntraID:Viewer — can monitor backup and restore processes without performing any operations. You can limit access to specific Entra ID tenants when assigning this role.

The following table describes the functionality available to users with different roles in Veeam Data Cloud. Note that users with EntraID:Administrator, EntraID:SettingsAdministrator, EntraID:RestoreAdministrator and EntraID:Viewer roles assigned will have the described permissions only within the specified scope of tenants.

| Role | Entra ID Tenant Management | Entra ID Restore | Entra ID Tenant Settings |
| --- | --- | --- | --- |
| OrganizationAdmin | Full | Full | Full |
| OrganizationViewer | View tenants | — | — |
| EntraID:Administrator | Full | Full | Full |
| EntraID:SettingsAdministrator | View tenants | — | Full |
| EntraID:RestoreAdministrator | View tenants | Full | — |
| EntraID:Viewer | View tenants | View restore sessions, backed-up objects and logs | — |

Salesforce Roles

You can assign the following roles to users working with Veeam Data Cloud for Salesforce:

* Salesforce:Administrator — can add, rename and delete tenants and perform all configuration actions, backup and restore operations. You can limit access to specific Salesforce tenants when assigning this role.
* Salesforce:BackupOperator — can add tenants, manage backup policies, manage protected data and perform all restore and archival operations. You can limit access to specific Salesforce tenants when assigning this role.
* Salesforce:RestoreOperator — can only perform restore operations. You can limit access to specific Salesforce tenants when assigning this role.
* Salesforce:Viewer — can monitor backup and restore processes without performing any operations. You can limit access to specific Salesforce tenants when assigning this role.

The following table describes the functionality available to users with different roles in Veeam Data Cloud. Note that users with Salesforce:Administrator, Salesforce:BackupOperator, Salesforce:RestoreOperator and Salesforce:Viewer roles assigned will have the described permissions only within the specified scope of tenants.

| Role | Salesforce Tenant Management | Salesforce Backup | Salesforce Restore | Salesforce Tenant Settings |
| --- | --- | --- | --- | --- |
| OrganizationAdmin | Full | Full | Full | Full |
| OrganizationViewer | View tenants | — | — | — |
| Salesforce:Administrator | Full | Full | Full | Full |
| Salesforce:BackupOperator | View and add tenants | Full | Full | — |
| Salesforce:RestoreOperator | View tenants | View backup policies and sessions | Full | — |
| Salesforce:Viewer | View tenants | View backup policies and sessions | View restore sessions | — |

Microsoft 365 Roles

You can assign the following roles to users working with Veeam Data Cloud for Microsoft 365:

* M365:Administrator — can add and manage tenants and perform all configuration actions and backup and restore operations.
* M365:BackupOperator — can add and manage tenants and create and manage backup policies.
* M365:RestoreOperator — can view tenants and perform restore operations.

Veeam Data Cloud for Microsoft 365 also offers the option to create custom user roles. For more information, see [Creating Roles](users_roles_custom.md).

The following table describes the functionality available to users with different roles in Veeam Data Cloud. Note that users with the M365:Administrator, M365:BackupOperator and M365:RestoreOperator roles assigned have the described permissions only within the specified scope of tenants.

| Role | Microsoft 365 Tenant Management | Microsoft 365 Backup | Microsoft 365 Restore | Microsoft 365 Tenant Settings |
| --- | --- | --- | --- | --- |
| OrganizationAdmin | Full | Full | Full | Full |
| OrganizationViewer | View tenants | — | — | — |
| M365:Administrator | Full | Full | Full | Full |
| M365:BackupOperator | View, add and manage tenants | Full | — | — |
| M365:RestoreOperator | View tenants | — | Full | — |

Microsoft Azure Roles

You can assign the Azure:Administrator role to users working with Veeam Data Cloud for Microsoft Azure. Users with the Azure:Administrator role assigned can view and manage resources within the tenant to which they are assigned this role. Users with the Azure:Administrator role cannot add new tenants.

The following table describes the functionality available to users with different roles in Veeam Data Cloud. Note that users with Azure:Administrator role assigned have the described permissions only within the specified scope of tenants.

| Role | Microsoft Azure Tenant Management | Microsoft Azure Backup | Microsoft Azure Restore | Microsoft Azure Tenant Settings |
| --- | --- | --- | --- | --- |
| OrganizationAdmin | Full | Full | Full | Full |
| OrganizationViewer | View tenants | — | — | — |
| Azure:Administrator | View tenants | Full | Full | Full |

Veeam Data Cloud Vault Roles

You can assign the following roles to users working with Veeam Data Cloud Vault:

* Vault:Administrator — can add tenants and perform all configuration actions, backup and restore operations.

To prohibit a user with the Vault:Administrator role to add tenants, limit access to specific Veeam Data Cloud Vault tenants when assigning this role and assign the user the OrganizationViewer role.

* Vault:Viewer — can monitor backup and restore processes without performing any operations.

You can limit access to specific Veeam Data Cloud Vault tenants when assigning roles.

The following table describes the functionality available to users with different roles in Veeam Data Cloud. Note that users with Vault:Administrator role assigned have the described permissions only within the specified scope of tenants.

| Role | Veeam Data Cloud Vault Tenant Management |
| --- | --- |
| OrganizationAdmin | Full |
| OrganizationViewer | View tenants |
| Vault:Administrator | Full |
| Vault:Viewer | View tenants |

