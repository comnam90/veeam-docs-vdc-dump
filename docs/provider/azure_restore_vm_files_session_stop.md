---
title: "Step 5. Review and Stop Restore Session"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/azure_restore_vm_files_session_stop.html"
last_updated: "1/19/2026"
product_version: ""
---

# Step 5. Review and Stop Restore Session


After you restore the necessary files and folders, you can review the restore session information. Do do this, click Sessions.

[![Step 5. Review and Stop Restore Session](images/azure_restore_vm_files_review_session.webp)](images/azure_restore_vm_files_review_session.webp)

After you finish working with the File-Level Recovery Explorer, it is recommended that you stop the restore session so that Veeam Data Cloud for Microsoft Azure can unmount and detach virtual disks of the processed Azure VM from the worker instance and deallocate the worker instance.

|  |
| --- |
| Tip |
| If you do not perform any actions in the File-Level Recovery Explorer for 30 minutes, and if no files are being restored, Veeam Data Cloud for Microsoft Azure will stop the recovery session automatically. |

To stop the restore session, do either of the following:

* On the File-level Recovery Explorer page, click Stop session. The File-Level Recovery Explorer will stop the session and return to the page with the list of protected VMs.

* In the Restore section of the main menu, navigate to Azure > Virtual machines and do the following:

* Locate the VM whose files you are restoring and, in the File-level Recovery column, click the File-level Recovery link.
* In the File-level Recovery window, click Stop session.

[![Step 5. Review and Stop Restore Session](images/azure_restore_vm_files_stop_session.webp)](images/azure_restore_vm_files_stop_session.webp)

