---
title: "Salesforce Archiving"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_archiving.html"
last_updated: "11/18/2025"
product_version: ""
---

# Salesforce Archiving

In this article

You can configure archival policies and instruct Veeam Data Cloud to delete obsolete or excessive data from Salesforce production tenants to consume less storage space in Salesforce and improve its performance.

When Veeam Data Cloud removes data while performing an archival operation, the archived data is only removed from Salesforce — but remains in Veeam Data Cloud, and is marked as Archived. You can restore data archived by a specific archival session. For details, see [Restoring Archived Data](sf_activity_archive_create_jobs.md).

You can also deploy Veeam Data Cloud Salesforce Extension that allows you to access and restore Salesforce archived data directly from the Salesforce console. The extension improves user experience and reduces administrative workload required to process data requests. For details, see [Configuring Salesforce Package Connection](sf_settings_connections_package.md).

|  |
| --- |
| Note |
| * Only users assigned the Salesforce:Administrator or Salesforce:BackupOperator role can perform archival operations in Veeam Data Cloud. However, these users can create and run archival policies within their permission scope only — that is, for tenants whose data they can access. * You can archive only records and files that have been backed up; for the list of objects that cannot be archived, see [Unsupported Salesforce Objects](sf_unsupported_objects.md). |

In This Section

* [Creating Archival Policies](sf_archival_policies_create.md)
* [Starting and Stopping Archival Policies](sf_archival_policies_start_stop.md)
* [Enabling and Disabling Archival Policies](sf_archival_policies_enable_disable.md)
* [Editing Archival Policies](sf_archival_policies_edit.md)
* [Removing Archival Policies](sf_archival_policies_remove.md)

Page updated 11/18/2025
