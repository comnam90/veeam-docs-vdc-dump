---
title: "Step 3. Specify Account and Restore Mode"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_restore_files_mode.html"
last_updated: "3/2/2026"
product_version: ""
---

# Step 3. Specify Account and Restore Mode


At the Restore Mode step of the wizard, specify the following restore settings:

* [Azure account](#account)
* [Restore mode and destination](#mode)

Specifying Azure Account

Make sure the Default Azure account is selected. This is the Veeam service principal account that was created by Veeam Data Cloud for Microsoft Azure. This account has all the necessary roles and permissions for the restore operation.

Specifying Restore Mode and Destination

In the Restore Mode section, choose whether you want to restore files from the selected file share to the original or to a custom location.

If you select the Restore to new location with different settings option, you must also select an Azure subscription, region and target file share in which the restored Azure VM will reside. To do this, in the Destination section, perform the following steps:

1. From the Subscription drop-down list, select the necessary Azure subscription.

For a subscription to be displayed in the list of available subscriptions, it must be [created](https://learn.microsoft.com/en-us/azure/cost-management-billing/manage/create-subscription) in Microsoft Azure and [associated](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) with the Microsoft Entra tenant to which the specified service account belongs.

1. From the Region drop-down list, select an Azure region.
2. Click File Share and select a file share in the Choose file share window.

|  |
| --- |
| Note |
| Data transfer to a new location may result in additional costs and may take more time to complete. |

[![Step 3. Specify Account and Restore Mode](images/azure_restore_files_mode.png)](images/azure_restore_files_mode.png)

