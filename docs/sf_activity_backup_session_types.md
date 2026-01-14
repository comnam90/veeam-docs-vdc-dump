---
title: "Backup Session Types"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_activity_backup_session_types.html"
last_updated: "3/14/2025"
product_version: ""
---

# Backup Session Types

In this article

When creating a backup policy, you configure the default backup schedule according to which Veeam Data Cloud backs up the Salesforce tenant. You can also enable custom schedules in the backup policy settings to additionally protect specific objects. Veeam Data Cloud uses the configured schedules to create backup sessions of 3 different types:

* Data session — this session type is used to back up object data of the protected Salesforce tenant. Data sessions run according to each configured backup schedule (both custom and default). To learn how to configure backup schedules, see [Configure Backup Schedules](sf_backup_policies_edit_backup_schedule.md).
* Metadata session — this session type is used to back up metadata of the protected Salesforce tenant. Metadata sessions run according to default backup schedules only. For the full list of Salesforce metadata that can be backed up, see [Salesforce Documentation](https://developer.salesforce.com/docs/atlas.en-us.api_meta.meta/api_meta/meta_types_list.htm).
* File session — this session type is used to back up files and attachments of the protected Salesforce tenant. File sessions run according to default backup schedules and only if you enable backup of files and attachments in backup policy settings. To learn how to enable this functionality, see [Configure Additional Options](sf_backup_policies_edit_backup_options.md).

Additionally, Veeam Data Cloud periodically runs the following types of backup sessions:

* Validate session — this session type is used to compare backed-up data in the product database with data currently stored in Salesforce, that is, to detect hard-deleted items and mark them as deleted in the product database. Validate sessions automatically run weekly at the same time for each enabled backup policy. To learn how to enable backup policies, see [Enabling and Disabling Backup Policies](sf_backup_policies_disable_enable.md).
* Reload session — this session type is used to upload missing record fields, files and metadata to PostgreSQL databases and file repositories. Reload sessions are launched manually with no regard to backup schedules. To learn how to run a reload session, see [Reloading Fields and Files](sf_activity_backup_reload_fields.md) and [Reloading Metadata](sf_activity_backup_reload_metadata.md).
* Encryption session — this session type is used to encrypt record fields and files of the protected Salesforce tenant. Encryption sessions run according to the [configured encryption settings](sf_backup_policies_edit_encryption.md) — but only for those backup policies that have already been used to protect fields and files (meaning these items already have backups) and that previously had the encryption functionality disabled.

If you disable encryption for a backup policy, the next run of the encryption session will decrypt data that has been previously encrypted. To learn how to disable encryption, see [Editing Backup Policies](sf_backup_policies_edit.md#encryption_start).

For each object specified while [configuring encryption settings](sf_backup_policies_edit_encryption.md), Veeam Data Cloud runs a separate encryption session. If an encryption session completes with failure, the session is automatically restarted in an hour. The product will continue to restart the session every hour until it completes successfully.

Page updated 3/14/2025
