---
title: "How Salesforce Backup Works"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_how_backup_works.html"
last_updated: "11/18/2025"
product_version: ""
---

# How Salesforce Backup Works

In this article

Veeam Data Cloud performs the following types of backup:

* Initial — this type of backup is performed during the first backup session. Veeam Data Cloud copies all records, files and metadata and creates a backup. The initial backup becomes a starting point in the incremental backup.

To improve the initial backup performance, Veeam Data Cloud starts a separate backup session for each object with more than 20,000,000 records. For all objects with less than 20,000,000 records, Veeam Data Cloud starts a single session. This approach may increase the number of backup sessions for each backup policy run.

* Incremental — this type of backup is performed during subsequent backup sessions. Veeam Data Cloud copies only those records, files and metadata that have changed since the previous backup session, and stores these data blocks to incremental backups. The content of each incremental backup depends on the content of the initial backup and the preceding incremental backups in the regular backup chain.

Veeam Data Cloud performs an incremental backup in the following way:

1. The product checks whether new objects (records, fields, files and metadata) have been added to Salesforce and creates metadata, file and data sessions to process new items. For more information on session types, see [Backup Session Types](sf_activity_backup_session_types.md).

Note that if you have cleared the Automatically add new objects and Automatically add new fields on objects check boxes [when configuring the backup policy](sf_backup_policies_edit_backup_options.md), Veeam Data Cloud will not add new items to the backup scope.

1. Veeam Data Cloud runs all backup sessions in parallel comparing backed-up data in the product database with data currently stored in Salesforce. If the product detects an object whose value in the latest version of the backed-up object is different from the value in Salesforce, Veeam Data Cloud will back up the data creating a new restore point for the object. Otherwise, the object will be skipped from processing.

For objects that have no incremental fields, Veeam Data Cloud compares values of the object records in the Salesforce tenant with their values in the latest restore point. If any difference is found, Veeam Data Cloud creates a full backup of the object. This approach may increase the number of backup sessions for each backup policy run. By default, the ContentWorkspaceMember and AssetAttribute objects are backed up this way.

|  |
| --- |
| Note |
| If a backup session does not respond for more than 24 hours (no data is uploaded), the session is terminated automatically. |

Page updated 11/18/2025
