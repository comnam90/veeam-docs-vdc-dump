---
title: "Step 3. Start Restore Session"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_restore_vm_files_session.html"
last_updated: "1/19/2026"
product_version: ""
---

# Step 3. Start Restore Session


At the Summary step of the wizard, review summary information and start the restore session.

1. Click Restore.

[![Step 3. Start Restore Session](images/azure_restore_vm_files_summary.webp)](images/azure_restore_vm_files_summary.webp)

Veeam Data Cloud for Microsoft Azure will start a restore session.

[![Step 3. Start Restore Session](images/azure_restore_vm_files_session_launched.webp)](images/azure_restore_vm_files_session_launched.webp)

During the restore session, Veeam Data Cloud for Microsoft Azure will launch a worker instance and attach virtual disks of the processed Azure VM to it. After the restore point is mounted and ready for browsing, Veeam Data Cloud for Microsoft Azure will generate a link to the File-Level Recovery Explorer.

1. Close the Restore Virtual Machines window.

Veeam Data Cloud for Microsoft Azure will return to the Protected Data > Restore Azure > Virtual Machines tab with the list of protected VMs.

1. On the Virtual Machines tab, locate the VM whose files you are restoring and click the File-Level Recovery link.
2. In the File-Level Recovery window, click Explore.

[![Step 3. Start Restore Session](images/azure_restore_vm_files_explore_link.webp)](images/azure_restore_vm_files_explore_link.webp)

|  |
| --- |
| Tip |
| Alternatively, you can view the restore session progress and status of the File-Level Recovery Explorer in real time in the session log. To learn more, see [Viewing Session Logs](azure_logs_session.md). |

