---
title: "Step 3. Specify Account and Restore Mode"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_restore_sql_mode.html"
last_updated: "4/17/2026"
product_version: ""
---

# Step 3. Specify Account and Restore Mode


At the Restore Mode step of the wizard, specify the following restore settings:

* [Azure account](#account)
* [Restore mode and destination](#mode)

Specifying Azure Account

Make sure the Default Azure account is selected. This is the Veeam service principal account that was created by Veeam Data Cloud for Microsoft Azure. This account has all the necessary roles and permissions for the restore operation.

Specifying Restore Mode and Destination

In the Restore mode section, select one of the following options:

* Restore to the original location — select this option to restore an Azure SQL database with the original name and settings.
* Restore to original location with different settings — select this option to restore an Azure SQL database with a different name or settings.

[![Step 3. Specify Account and Restore Mode](images/azure_restore_sql_mode.png)](images/azure_restore_sql_mode.png)

