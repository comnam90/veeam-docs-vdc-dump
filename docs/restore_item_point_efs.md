---
title: "Step 2a. Select Restore Point"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/restore_item_point_efs.html"
last_updated: "3/23/2026"
product_version: ""
---

# Step 2a. Select Restore Point


By default, Veeam Data Cloud for AWS uses the most recent valid restore point. However, you can restore files and folders to an earlier state.

To select a restore point:

1. In the Restore point section of the Restore List step of the wizard, click the link next to the Restore point filed.
2. In the Choose restore point window, select the necessary restore point and click Apply.

To help you choose a restore point, Veeam Data Cloud for AWS provides the following information on each available restore point:

* Date — the date when the restore point was created.
* Size — the size of the restore point.
* Type — the type of the restore point:

* EFS backup — an EFS backup created by a backup policy.
* EFS backup copy — a backup copy created by a backup policy.
* Manual backup — an EFS backup created manually.

* Restore Point Region — an AWS Region where the restore point is stored.

[![Select Restore Point](images/restore_item_point_efs.webp)](images/restore_item_point_efs.webp "Select Restore Point")

