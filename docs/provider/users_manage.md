---
title: "Users and Roles"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/users_manage.html"
last_updated: "1/26/2026"
product_version: ""
---

# Users and Roles


Veeam Data Cloud allows you to create, edit and delete users in your Veeam Data Cloud organization and Veeam Data Cloud organizations of your customers. You can assign multiple roles to a user and configure a role scope. User roles define the operations that the user can perform, including backup, restore and user management.

You can assign a role with access to your entire Veeam Data Cloud organization or a specific workload, such as Microsoft Entra ID, Salesforce or Microsoft 365. Role scopes define which tenants the user can access. This can be helpful in larger organizations with multiple tenants where users are assigned to manage specific tenants.

To simplify user management, you can use Veeam Data Cloud groups. Groups allows Veeam Data Cloud to automatically grant access and assign roles to users that use Microsoft Entra ID single sign-on (SSO) to log in to Veeam Data Cloud. With this functionality, you do not need to invite users and add a user account for each Veeam Data Cloud user manually.

User management is available only to users with the OrganizationAdmin role assigned. User management of your customer organization is available only if the customer allowed you to manage their organization. For details, see the [Configuring Partner Access](https://helpcenter.veeam.com/docs/vdc/userguide/sp_partner_access.html) section of the Veeam Data Cloud User Guide.

In This Section

* [Roles](users_roles.md)
* [Users](users.md)
* [Groups](users_groups.md)
* [Managing Customer Users](sp_customer_users.md)

