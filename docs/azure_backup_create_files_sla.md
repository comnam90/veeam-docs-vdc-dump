---
title: "Step 4. Specify Policy Protection Settings"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_backup_create_files_sla.html"
last_updated: "1/26/2026"
product_version: ""
---

# Step 4. Specify Policy Protection Settings


At the Protection Settings step of the wizard, select an SLA template that will be applied to the protected resources.

|  |
| --- |
| Note |
| Veeam Data Cloud for Microsoft Azure takes snapshots automatically according to the schedule of the selected SLA template. You cannot modify SLA templates or take ad hoc snapshots manually. |

You can select one of the following SLA templates:

* Gold — select this option if you want to create snapshots every hour and retain them for 1 day.
* Silver — select this option if you want to create snapshots every 8 hours and retain them for 1 day.
* Bronze — select this option if you want to create snapshots once per day and keep them for 7 days.

|  |
| --- |
| Note |
| To store backups, Veeam Data Cloud for Microsoft Azure automatically creates a repository in every Azure region whose resources are protected by the backup policy. |

[![Specify Policy Protection Settings](images/azure_backup_create_files_sla.png)](images/azure_backup_create_files_sla.png "Specify Policy Protection Settings")

