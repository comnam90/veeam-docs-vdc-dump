---
title: "Groups"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/users_groups.html"
last_updated: "4/22/2026"
product_version: ""
---

# Groups


Veeam Data Cloud groups integrate with Microsoft Entra ID single sign-on (SSO) to provide centralized, group-based access control. Group membership determines which users can log in to Veeam Data Cloud and which roles are assigned to them. This allows you to manage access without creating individual user accounts in Veeam Data Cloud. Group-based access ensures that permissions are consistently applied and updated based on user membership in Microsoft Entra ID.

How Veeam Data Cloud Groups Work

Veeam Data Cloud groups correspond to groups in Microsoft Entra ID. In Microsoft Entra ID, you manage group membership by adding or removing members. In Veeam Data Cloud, you assign roles to a group by specifying the object ID of the matching Microsoft Entra ID group. The object ID you specify in Veeam Data Cloud must exactly match the object ID of the group in your Microsoft Entra ID organization because Veeam Data Cloud uses object IDs to verify whether a user is a member of the group.

When a group member logs in to Veeam Data Cloud for the first time, Veeam Data Cloud automatically creates a user account and grants permissions based on the roles assigned to the group. Veeam Data Cloud verifies group membership and updates user permissions every time the user logs in. If you delete a user account from Veeam Data Cloud but the user remains a group member, Veeam Data Cloud will recreate the user account the next time the user logs in to Veeam Data Cloud.

You can assign additional roles to the user individually after the user logs in and Veeam Data Cloud creates the user account. For details, see [Editing Users](users_edit.md). If you assign roles both individually and through group membership, Veeam Data Cloud combines the permissions.

Before You Begin

Before you start working with groups in Veeam Data Cloud, consider the following:

* Veeam Data Cloud verifies group membership only for users who use Microsoft Entra ID for single sign-on (SSO) with Veeam Data Cloud. Veeam Data Cloud cannot verify group membership for users who use the Veeam My Account credentials to log in to Veeam Data Cloud.
* You can use Entra ID security groups and Microsoft 365 groups to manage group membership.
* Veeam Data Cloud does not support Entra ID group nesting. Users must be direct members of the groups.
* When you remove a user from an Entra ID group, Veeam Data Cloud preserves the user account. If you no longer need the user account, delete it manually. For details, see [Deleting Users](users_delete.md).
* If you delete the matching group in Microsoft Entra ID, Veeam Data Cloud will not be able to use this group to authenticate the group members that log in to Veeam Data Cloud for the first time and to assign them roles. To restore the functionality, create a new group in Veeam Data Cloud and map it to an existing Entra ID group.

Configuring Groups

To configure group-based access in Veeam Data Cloud, follow these steps:

1. Prepare a group in Microsoft Entra ID and add group members. For more information on Entra ID groups, see [Microsoft documentation](https://learn.microsoft.com/en-us/entra/fundamentals/concept-learn-about-groups).
2. Create a group in Veeam Data Cloud. For details, see [Creating Groups](users_groups_create.md).
3. [Optional] After group members log in to Veeam Data Cloud, assign additional roles to them individually. For details, see [Editing Users](users_edit.md).

In This Section

* [Creating Groups](users_groups_create.md)
* [Editing Groups](users_groups_edit.md)
* [Deleting Groups](users_groups_delete.md)

