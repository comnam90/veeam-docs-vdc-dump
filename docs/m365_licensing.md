---
title: "Licensing"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_licensing.html"
last_updated: "1/6/2026"
product_version: ""
---

# Licensing

In this article

Plans

Veeam Data Cloud for Microsoft 365 provides you with 3 plan options: Foundation, Advanced and Premium. You can utilize multiple plan types within one tenancy of Veeam Data Cloud for Microsoft 365. You can purchase through authorized Veeam partners or in the Microsoft Azure Marketplace. For more information, see [this Veeam webpage](https://www.veeam.com/products/veeam-data-cloud/purchasing-options.html?ad=menu-products-vdc).

This section provides information on plans for Veeam Data Cloud for Microsoft 365.

Foundation

Flex backup policies can be implemented under Foundation. This prioritizes control and flexibility. Supports Microsoft Exchange Online, Microsoft SharePoint Online, Microsoft OneDrive for Business and Microsoft Teams. Offers comprehensive control and customization of backups and retention periods. Granular and bulk data recovery options. Data is stored separately from your Microsoft 365 tenant in the Azure location of your choice. Offers advanced security capabilities including granular Role Based Access Control.

Advanced

Combines the features available in Foundation with the addition of Entra ID protection. This includes data resilience for Entra ID users, groups, policies, logs and granular restore of Entra ID tenant data.

Premium

All features included in Advanced with addition of Express backup policies. Prioritizes speed and scale. Powered by Veeam’s integration with Microsoft 365 Backup Storage. Fast backup of initial Microsoft 365 tenant and other large datasets. Offers bulk restores at scale. Provides the strictest adherence to the 3–2–1 rule with multiple backup and restore options.

Mix and Match

Customers have the flexibility to mix and match licensing. For example, you can have the Premium plan for top users or a certain department or location, and Foundation or Advanced plans for the remainder of your Microsoft 365 users.

Variable License Model

Veeam Data Cloud for Microsoft 365 provides you with the Variable License Model. You can purchase through authorized Veeam partners or in the Microsoft Azure Marketplace.

The Variable License Model provides rich capabilities and automation and ensures the protection of all your Microsoft 365 data. Backup policies can be defined with variable scope, with entire organizations backed up or backups created with predefined rules such as using AD groups. Administrators can automatically add new users who join the Microsoft 365 organization to the backup, based on the backup rules defined. All objects that fit backup rules are backed up automatically. Administrators can manage backups (for example, create new backup policies, edit, disable or delete existing backup policies). Any additional users beyond the contract quantity are subject to overage charges.

|  |
| --- |
| IMPORTANT |
| The Fixed License Model has been deprecated. Any existing users will be moved to the Variable License Model, which provides additional functionality. No features will be lost in this transition. |

License Consumption

Veeam Data Cloud for Microsoft 365 licensing is determined by the user accounts for which you perform backups. Each protected user account consumes one Veeam Data Cloud for Microsoft 365 license.

Veeam Data Cloud for Microsoft 365 licenses are consumed by the following objects related to a user account:

* Microsoft Exchange Online mailboxes — each Microsoft Exchange Online mailbox requires one Veeam Data Cloud for Microsoft 365 license unit.

* Microsoft OneDrive for Business account — each OneDrive for Business account consumes one Veeam Data Cloud for Microsoft 365 license unit.

* Microsoft SharePoint Online personal sites — a personal SharePoint site of a licensed user consumes one Veeam Data Cloud for Microsoft 365 license unit.

For users under the Foundation plan, a Veeam Data Cloud for Microsoft 365 license unit covers a user mailbox, OneDrive for Business account and SharePoint personal site for which at least one restore point has been created within the last 31 days. For example, if the mailbox and personal site of the same user were backed up in the last 31 days, one Veeam Data Cloud for Microsoft 365 license will be consumed. If an object was not backed up for 31 days, its license is automatically revoked and will not count towards total license count.

|  |
| --- |
| NOTE |
| When you plan the number of Veeam Data Cloud for Microsoft 365 licenses you require, consider the following:   * All users in your Microsoft 365 subscription that are members of a backed-up team or have access to a backed-up team, communication, collaboration and other non-personal SharePoint sites must be licensed.  * If you back up only Microsoft Teams objects or non-personal SharePoint sites, the licenses are not consumed by Veeam Data Cloud for Microsoft 365. You must purchase enough licenses to cover all users who have access to these Microsoft Teams objects or non-personal SharePoint sites. |

The following objects do not consume a Veeam Data Cloud for Microsoft 365 license:

* Microsoft Teams objects — these objects do not consume a Veeam Data Cloud for Microsoft 365 license.
* Group and non-personal SharePoint sites — these sites do not consume a Veeam Data Cloud for Microsoft 365 license.
* Shared mailboxes, resource mailboxes, group mailboxes and public folder mailboxes — these mailboxes do not consume Veeam Data Cloud for Microsoft 365 licenses if such mailboxes do not have a Microsoft 365 license assigned. If such mailboxes do have a Microsoft 365 license assigned, then they will consume a Veeam Data Cloud for Microsoft 365 license. If a shared mailbox is licensed over the 50 GB threshold or licensed under a multi-geo mailbox, then it will consume a Veeam Data Cloud for Microsoft 365 license. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/microsoft-365/admin/email/about-shared-mailboxes?view=o365-worldwide).
* External SharePoint users — an external SharePoint user is a user from outside your Microsoft 365 subscription who has access to one or more sites, files or folders. External authenticated users are limited to basic collaboration tasks, and external anonymous users can edit or view specific documents if they have specific permissions.
* Guest Microsoft Teams users — a guest Teams user is a user from outside your Microsoft 365 subscription who has access to a backed-up team.

License Expiration

If your licenses expire and you do not renew them, Veeam Data Cloud will handle your backed-up data according to the Veeam Data Cloud Service Agreement. For more information, see [this Veeam article](https://www.veeam.com/legal/veeam-data-cloud-service-agreement.html).

Related Topics

* [Viewing License Details](m365_settings_view_license_model.md)
* [Activating Subscription in Microsoft Azure Marketplace](m365_settings_activate_subscription_azure.md)

Page updated 1/6/2026
