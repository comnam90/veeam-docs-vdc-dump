---
title: "Organization Activity"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/activity.html"
last_updated: "2026"
product_version: ""
---

# Organization Activity


Organization activities are the data protection sessions and audit log events generated across all workloads in the Veeam Data Cloud organizations of your customers. The Activity page consolidates these records into a single, filterable interface, so you can quickly identify issues, verify backup session statuses, and ensure that all objects are properly protected.

|  |
| --- |
| Note |
| The Activity page currently supports the Microsoft 365, Microsoft Azure, Entra ID and Salesforce workloads and can display data only from customer organizations that have the Delegated management by partner option enabled. For details on configuring partner access, see the [Configuring Partner Access](https://helpcenter.veeam.com/docs/vdc/userguide/sp_partner_access.html) section of the Veeam Data Cloud User Guide.  For the Microsoft Azure workload, only events related to VM and SQL backup policies are supported. |

The Activity page is available to users with one of the following roles or role sets assigned:

* OrganizationAdmin.
* OrganizationViewer and a role that allows the user to work with one or more workloads. For example, OrganizationViewer, EntraID:Administrator and M365:BackupOperator.

The Activity page displays only the data to which the user has access based on the roles assigned.

To open the Activity page, click the activity icon on the left.

In This Section

* [Viewing Backup Sessions](activity_backup.md)
* [Viewing Restore Sessions](activity_restore.md)
* [Viewing Audit Logs](activity_audit.md)

Page updated 2026-07-24
