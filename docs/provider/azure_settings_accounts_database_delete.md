---
title: "Deleting SQL Server Account"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/azure_settings_accounts_database_delete.html"
last_updated: "3/4/2026"
product_version: ""
---

# Deleting SQL Server Account


You can remove a SQL Server account from the configuration database if you no longer need it.

|  |
| --- |
| Important |
| You cannot remove a database account that is associated with any backup policy. To remove such an account, you must first delete all of the affected policies or edit their settings. |

To delete a SQL Server account from Veeam Data Cloud for Microsoft Azure, do the following:

1. In the Management section of the main menu, select Settings.
2. On the Azure SQL Server Accounts tab, select the account you want to delete and click Delete.
3. In the Delete Azure Sql Account dialog window, click OK.

[![Delete Database Account](images/azure_settings_accounts_database_delete.webp)](images/azure_settings_accounts_database_delete.webp "Delete Database Account")

