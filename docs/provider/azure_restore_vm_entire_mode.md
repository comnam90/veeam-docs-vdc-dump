---
title: "Step 3. Select Account and Restore Mode"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/azure_restore_vm_entire_mode.html"
last_updated: "12/15/2025"
product_version: ""
---

# Step 3. Select Account and Restore Mode


At the Restore Mode step of the wizard, specify the following restore settings:

* [Azure account](#account)
* [Restore mode and destination](#mode)

Specifying Azure Account

To select the Azure service account whose permissions Veeam Data Cloud for Microsoft Azure will use to perform the restore operation, do the following:

1. Click Select account.
2. In the Select Account window, choose the default Azure service account.

Specifying Restore Mode and Destination

|  |
| --- |
| Note |
| You can restore VMs to their original location only. |

In the Restore mode section, select one of the following options:

* Restore to the original location — select this option to restore a VM with the original name and settings.
* Restore to original location with different settings — select this option to restore a VM with a different name or settings. If you choose this option, the Restore Virtual Machines wizard will display an additional step - [Settings](azure_restore_vm_entire_settings.md). At this step, you can specify new settings for the restored VM.

[![Step 3. Select Account and Restore Mode](images/azure_restore_vm_entire_mode.webp)](images/azure_restore_vm_entire_mode.webp)

