---
title: "Salesforce Restore"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/sf_restore.html"
last_updated: "9/18/2025"
product_version: ""
---

# Salesforce Restore


Veeam Data Cloud offers the following restore options:

* [Restore records](sf_restore_records.md) — fully restores the content of a record, with all fields that are marked as updatable and creatable in Salesforce. You can also restore attachments associated with this record and the related object hierarchy.
* [Restore field value](sf_restore_field_values.md) — restores specific field values of a Salesforce record. Consider that you can only restore values of existing fields using this type of restore. If a field no longer exists in Salesforce, you must restore metadata first.
* [Restore files](sf_restore_files.md) — restores Salesforce files and attachments.
* [Restore metadata](sf_restore_metadata.md) — restores Salesforce metadata.

You can restore records, field values and metadata to the most recent state or to any available version.

With Veeam Data Cloud, you can restore data to another compatible Salesforce tenant, for example, from a production to a sandbox tenant. However, you cannot completely restore backed-up data of one Salesforce tenant to another with a single action. The following steps should be included in the full restore procedure:

1. Restore metadata.
2. Manually enable required Salesforce features.
3. Install required external packages.
4. Restore records and files.

To restore records with child hierarchy enabled, select the key root objects of your data model. The recommended maximum child hierarchy depth is 10 levels.

To recover backed-up data, Veeam Data Cloud runs restore jobs. When you create a restore job, it is created as a draft that you can further edit, remove, start and clone. Once the restore job is started, it can be only stopped or cloned.

|  |
| --- |
| Note |
| Only users assigned the OrganizationAdmin, Salesforce:Administrator, Salesforce:BackupOperator or Salesforce:RestoreOperator role can perform backup operations with Salesforce tenants. These users can create and run restore jobs within their permission scope only — that is, for Salesforce tenants whose data they can access. For details, see [Users and Roles](users_manage.md). |

In This Section

* [How Object Hierarchy Restore Works](sf_how_hierarchy_restore_works.md)
* [Creating Restore Jobs](sf_creating_restore_jobs.md)
* [Starting and Stopping Restore Jobs](sf_restore_start_stop.md)
* [Cloning Restore Jobs](sf_restore_clone.md)
* [Editing Restore Job Drafts](sf_restore_edit.md)
* [Removing Restore Job Drafts](sf_restore_remove.md)
* [Configuring Restore Mapping Settings](sf_restore_settings.md)
* [Viewing Restore Job Details](sf_viewing_restore_job_details.md)

