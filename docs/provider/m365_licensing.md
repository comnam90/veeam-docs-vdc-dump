---
title: "Licensing"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/m365_licensing.html"
last_updated: "4/16/2026"
product_version: ""
---

# Licensing


Plans

Veeam Data Cloud for Microsoft 365 provides you with 6 plan options: Foundation, Express, Advanced, Advanced Plus, Premium and Premium Plus. You can utilize multiple plan types within one tenancy of Veeam Data Cloud for Microsoft 365. You can request a new subscription with Veeam Data Cloud for Microsoft 365 plan in VCSP Pulse. For details, see [Requesting Subscriptions](sp_subscriptions_request.md).

This section provides information on plans for Veeam Data Cloud for Microsoft 365. For more information on available products, see [License Consumption](saas_license_consumption.md).

Foundation

Flex backup policies can be implemented under Foundation. This prioritizes control and flexibility. Supports Microsoft Exchange Online, Microsoft SharePoint Online, Microsoft OneDrive for Business and Microsoft Teams. Offers comprehensive control and customization of backups and retention periods. Granular and bulk data recovery options. Data is stored separately from your Microsoft 365 tenant in the Azure location of your choice. Offers advanced security capabilities including granular Role Based Access Control.

Express

Express backup policies can be implemented under the Express plan. Prioritizes speed and scale. Powered by Veeam integration with Microsoft 365 Backup Storage. Fast backup of initial Microsoft 365 tenant and other large datasets. Offers bulk restores at scale.

Advanced

Combines the features available in Foundation with the addition of Entra ID protection. This includes data resilience for Entra ID users, groups, policies, logs and granular restore of Entra ID tenant data.

Advanced Plus

Combines the features available in Advanced with the addition of Salesforce protection.

Premium

All features included in Advanced with addition of Express backup policies. Prioritizes speed and scale. Powered by Veeam integration with Microsoft 365 Backup Storage. Fast backup of initial Microsoft 365 tenant and other large datasets. Offers bulk restores at scale. Provides the strictest adherence to the 3–2–1 rule with multiple backup and restore options.

Premium Plus

Combines the features available in Premium with the addition of Salesforce protection.

Mix and Match

Customers have the flexibility to mix and match licensing. For example, you can have the Premium plan for top users or a certain department or location, and Foundation or Advanced plans for the remainder of your Microsoft 365 users.

Variable License Model

Veeam Data Cloud for Microsoft 365 provides you with the Variable License Model.

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

|  |
| --- |
| NOTE |
| When you plan the number of Veeam Data Cloud for Microsoft 365 licenses you require, consider the following:  To ensure license consumption and protection coverage, all users in your Microsoft 365 subscription that are members of a backed-up team or have access to a backed-up team, communication, collaboration and other non-personal SharePoint sites must be licensed. For Flex-based backups, you can achieve this with the Foundation, Advanced, Advanced Plus, Premium and Premium Plus plans. For Express-based backups, you can achieve this with the Express, Premium and Premium Plus plans. As a best practice, it is recommended to license all Microsoft 365 users in your environment. |

The following objects do not consume a Veeam Data Cloud for Microsoft 365 license:

* Microsoft Teams objects — these objects do not consume a Veeam Data Cloud for Microsoft 365 license.
* Group and non-personal SharePoint sites — these sites do not consume a Veeam Data Cloud for Microsoft 365 license.
* Shared mailboxes, resource mailboxes, group mailboxes and public folder mailboxes — these mailboxes do not consume Veeam Data Cloud for Microsoft 365 licenses if such mailboxes do not have a Microsoft 365 license assigned. If such mailboxes do have a Microsoft 365 license assigned, then they will consume a Veeam Data Cloud for Microsoft 365 license. If a shared mailbox is licensed over the 50 GB threshold or licensed under a multi-geo mailbox, then it will consume a Veeam Data Cloud for Microsoft 365 license. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/microsoft-365/admin/email/about-shared-mailboxes?view=o365-worldwide).
* External SharePoint users — an external SharePoint user is a user from outside your Microsoft 365 subscription who has access to one or more sites, files or folders. External authenticated users are limited to basic collaboration tasks, and external anonymous users can edit or view specific documents if they have specific permissions.
* Guest Microsoft Teams users — a guest Teams user is a user from outside your Microsoft 365 subscription who has access to a backed-up team.

|  |
| --- |
| tip |
| License consumption differs between subscriptions. For more information see [the Veeam Licensing Policy](https://www.veeam.com/legal/licensing-policy.html). |

License Expiration

If your licenses expire and you do not renew them, Veeam Data Cloud will handle your backed-up data according to the Veeam Data Cloud Service Agreement. For more information, see [this Veeam article](https://www.veeam.com/legal/veeam-data-cloud-service-agreement.html).

Related Topics

* [Viewing License Details](m365_settings_view_license_model.md)

