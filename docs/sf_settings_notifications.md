---
title: "Managing Notifications"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_settings_notifications.html"
last_updated: "3/25/2025"
product_version: ""
---

# Managing Notifications

In this article

Veeam Data Cloud can notify you about important events, state changes and issues. All users that have access to your Salesforce tenant can view the notifications in the Notification and Dashboard sections. You can also specify email addressees that will receive selected notifications.

You can create notifications for the following types of events:

* Backup policy — a notification created for this type of events is triggered by a specific backup session status. You can choose whether you want to receive notifications in case any of the backup policies configured for your Salesforce tenants complete successfully, complete with warnings or complete with errors.
* Restore job — a notification created for this type of events is triggered by a specific restore job status. You can choose whether you want to receive notifications in case any of the restore job configured for your Salesforce tenants complete successfully, complete with warnings or complete with errors.
* Salesforce connection — a notification created for this type of events is triggered when the connection to Salesforce is lost.
* Archival policy — a notification created for this type of events is triggered by a specific archival session status. You can choose whether you want to receive notifications in case any of the archival policies configured for your Salesforce tenants complete successfully, complete with warnings or complete with errors.
* Encryption session — a notification created for this type of events is triggered by a specific encryption session status. You can choose whether you want to receive notifications in case any of the encryption sessions configured for your Salesforce tenants complete successfully, complete with warnings or complete with errors that are related to the AWS KMS connection.
* Data change — a notification created for this type of events is triggered when Veeam Data Cloud detects any changes in protected data. You can choose whether you want to receive notifications in case new records are added to any of the backup policies configured for your Salesforce tenants, or any of the existing records are updated or deleted from Salesforce.

In This Section

* [Adding Notifications](sf_settings_notifications_add.md)
* [Editing Notifications](sf_settings_notifications_edit.md)
* [Removing Notifications](sf_settings_notifications_remove.md)

Page updated 3/25/2025
