---
title: "Restoring Azure SQL Databases"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_restore_sql.html"
last_updated: "2026"
product_version: ""
---

# Restoring Azure SQL Databases


You can restore an entire Azure SQL database from an image-level backup. Veeam Data Cloud for Microsoft Azure allows you to restore one or more databases at a time, to the original location or to a new location. A new location can be a different region within the same Azure subscription, or the same or a different region in another Azure subscription. The target region must be one of the supported Azure regions.

To restore an Azure SQL database, do the following:

1. [Launch the SQL Database Restore wizard](azure_restore_sql_launch.md).
2. [Select a restore point](azure_restore_sql_point.md).
3. [Select Veeam service account and restore mode](azure_restore_sql_mode.md).
4. [Specify settings for the restored SQL server and databases](azure_restore_sql_settings.md).
5. [Review the restore setup and complete the restore process](azure_restore_sql_complete.md).

Page updated 2026-07-21
