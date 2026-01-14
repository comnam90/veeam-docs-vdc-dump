---
title: "Step 4. Specify Policy Protection Settings"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_backup_create_files_sla.html"
last_updated: "12/17/2025"
product_version: ""
---

# Step 4. Specify Policy Protection Settings

In this article

At the Protection Settings step of the wizard, select an SLA template that will be applied to the protected resources:

* Gold — select this option if you want to create snapshots every hour and retain them for 1 day.
* Silver — select this option if you want to create snapshots every 8 hours and retain them for 1 day.
* Bronze — select this option if you want to create snapshots once per day and keep them for 7 days.

|  |
| --- |
| Note |
| To store backups, Veeam Data Cloud for Microsoft Azure automatically creates a repository in every Azure region whose resources are protected by the backup policy. |

[![Specify Policy Protection Settings](images/azure_backup_create_files_sla.png)](images/azure_backup_create_files_sla.png "Specify Policy Protection Settings")

Page updated 12/17/2025
