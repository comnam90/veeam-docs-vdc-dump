---
title: "Step 3. Specify Account and Restore Mode"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/azure_restore_sql_mode.html"
last_updated: "12/15/2025"
product_version: ""
---

# Step 3. Specify Account and Restore Mode


At the Restore Mode step of the wizard, specify the following restore settings:

* [Azure account](#account)
* [Restore mode and destination](#mode)

Specifying Azure Account

To select the account whose permissions Veeam Data Cloud for Microsoft Azure will use to perform the restore operation, do the following:

1. Click Select account.
2. In the Select Azure Account window, select an account that you want to use for the restore procedure.

Specifying Restore Mode and Destination

In the Restore mode section, select one of the following options:

* Restore to the original location — select this option to restore an Azure SQL database with the original name and settings. If you choose this option, you must also specify an Azure SQL account that will be used to access the restored database. To do this, in the SQL Account section, click Select account and choose the necessary SQL account.
* Restore to original location with different settings — select this option to restore an Azure SQL database with a different name or settings. If you choose this option, the SQL Database Restore wizard will display an additional step - [Settings](azure_restore_sql_settings.md). At this step, you can specify new settings for the restored VM.

[![Step 3. Specify Account and Restore Mode](images/azure_restore_sql_mode.webp)](images/azure_restore_sql_mode.webp)

