---
title: "Removing Database Accounts"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_settings_accounts_database_remove.html"
last_updated: "3/17/2026"
product_version: ""
---

# Removing Database Accounts


Veeam Data Cloud for AWS allows you to permanently remove a database account from the Veeam Data Cloud database if you no longer need it:

1. On the tenant administration page, navigate to Settings > Database Accounts.
2. Select the account and click Remove.

|  |
| --- |
| Important |
| You cannot remove a database account that is associated with any backup policy. Delete all of the affected policies or [edit their settings](aws_settings_accounts_database_edit.md) — and then try removing the account again. |

[![Removing Database Accounts](images/aws_settings_accounts_database_remove.webp)](images/aws_settings_accounts_database_remove.webp "Removing Database Accounts")

