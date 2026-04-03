---
title: "Step 5. Specify Policy Processing Settings"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/azure_backup_create_sql_process.html"
last_updated: "3/30/2026"
product_version: ""
---

# Step 5. Specify Policy Processing Settings


At the Processing Settings step of the wizard, select the database processing options:

* [Process databases using the production server](#production) — if you select this option, Veeam Data Cloud will create a restore point of the database and transfers it directly to the backup repository. In this case, the database is exported as is, which may result in an inconsistent backup. This process can impact the performance of the production database.
* [Use staging servers](#staging) — if you select this option, Veeam Data Cloud first will copy the database to a staging server, create a restore point, and then transfer it to the backup repository. This process ensures a consistent backup, as the copied database has no active connections and the online database experiences no performance impact during backup. Keep in mind that only one staging server can be used, so if the policy protects databases from multiple servers, all copies will be sent to a single server.

|  |
| --- |
| Note |
| Veeam Data Cloud for Microsoft Azure does not support using staging servers to back up [free offer Azure SQL databases](https://learn.microsoft.com/en-us/azure/azure-sql/database/free-offer?view=azuresql). |

Protecting Databases Without Staging Server

To back up the selected databases without a staging server, do the following:

1. Select the Process databases using the production server option and click Configure Credentials.
2. In the Choose credentials window, for each SQL Server added to the policy, specify an Azure SQL account whose permissions Veeam Data Cloud will use to authenticate against the server. To do that, select a server and click Edit. In the Choose the authentication method window, select the necessary account and click Apply.

For an account to be displayed in the Account list, it must be added to Veeam Data Cloud as described in section [Adding Database Account](azure_settings_accounts_database_add.md). If you have not added the necessary Azure SQL account beforehand, you can do it without closing the New Azure SQL Policy wizard. To add an account, click Add and complete the [New SQL server account wizard](azure_settings_accounts_database_add.md).

1. Click Apply.

[![Specify Policy Processing Settings](images/azure_backup_create_sql_process_production.webp)](images/azure_backup_create_sql_process_production.webp "Specify Policy Processing Settings")

Protecting Databases Using Staging Server

To back up the selected databases using a staging server, do the following:

1. Select Use staging servers.
2. Specify a staging server and account for each type of protected resources. To do that, click Choose server next to the resource type. The available options depend on the resources added at the [Source](azure_backup_create_sql_source.md) step of the wizard:

* SQL Managed Instance — for protecting individual databases within a managed instance.
* SQL Server — for protecting the entire SQL Server.

1. In the Choose staging server window, do the following:

1. From the Staging Server drop-down list, select a SQL Server that will be used to copy the databases. If you plan to back up a database located on an Azure SQL Managed Instance, you must specify the source SQL Server as a staging server.

For a server to be displayed in the Staging server list, it must be added to the Microsoft Azure environment as described in [Microsoft Docs](https://docs.microsoft.com/en-us/azure/azure-sql/database/single-database-manage).

|  |
| --- |
| Important |
| If you use custom Transparent Data Encryption (TDE) to protect SQL Server data, consider that the same Azure Key Vault cryptographic key must be used to encrypt the source and the staging SQL Servers to allow Veeam Data Cloud to perform backup using the Use staging servers option. |

1. Select an Azure SQL account whose permissions Veeam Data Cloud will use to authenticate against the staging server.

For an account to be displayed in the SQL Account section, it must be added to Veeam Data Cloud as described in section [Adding Database Account](azure_settings_accounts_database_add.md). If you have not added the necessary Azure SQL account beforehand, you can do it without closing the New Azure SQL Policy wizard. To add an account, click Add and complete the [New SQL server account wizard](azure_settings_accounts_database_add.md).

|  |
| --- |
| Important |
| If the Azure SQL account you use to authenticate against the staging server does not have the sysadmin [server-level role](https://learn.microsoft.com/en-us/sql/relational-databases/security/authentication-access/server-level-roles?view=sql-server-ver16) assigned, you can only use the source SQL Server as a staging server — otherwise, the backup operation will fail. |

1. Click Apply.

[![Specify Policy Processing Settings](images/azure_backup_create_sql_process_staging.webp)](images/azure_backup_create_sql_process_staging.webp "Specify Policy Processing Settings")

