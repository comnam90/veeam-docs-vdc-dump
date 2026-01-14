---
title: "Audit Log Events"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/activity_audit_events.html"
last_updated: "11/14/2025"
product_version: ""
---

# Audit Log Events

In this article

This article lists all events that are recorded in the Veeam Data Cloud audit log.

Access Management

| Event | Description |
| --- | --- |
| User Invite Sent | Organization administrator invited a new user to Veeam Data Cloud. For details, see [Adding Users](users_add.md). |
| User Invite Canceled | Organization administrator canceled a user invitation. For details, see [Deleting Users](users_delete.md). |
| User Created | Invited user was added to the organization. This event occurs together with the User Invite Sent event. |
| User Deleted | User was removed from an organization. For details, see [Deleting Users](users_delete.md). |
| Role Added | Role was assigned to a user. For details, see [Editing Users](users_edit.md). |
| Role Removed | Role assignment was removed from a user. For details, see [Editing Users](users_edit.md). |
| Workload Tenant Added | Workload tenant was added to an organization. |
| Workload Tenant Deleted | Workload tenant was removed from an organization. |

Resource Access

| Event | Description |
| --- | --- |
| User Login | User logged in to a Veeam Data Cloud organization. |

Page updated 11/14/2025
