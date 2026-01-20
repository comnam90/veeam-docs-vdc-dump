---
title: "Step 4. Select Files to Restore"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_restore_vm_files_explorer.html"
last_updated: "1/20/2026"
product_version: ""
---

# Step 4. Select Files to Restore


In the File-Level Recovery Explorer, you can browse and restore files and folders of the selected Azure VM. All recovered items will be restored to the original Azure VM.

To recover files and folders from a specific folder, perform the following steps:

1. On the Browse tab, select the location of the files and folders that you want to restore:

1. Select a volume and navigate to the folder that contains the necessary files and folders.
2. In the working area, select check boxes next to the necessary items.

|  |
| --- |
| Note |
| During file-level recovery from Linux-based Azure VMs, all files and folders are structured according to their physical location. That is why the file system tree displayed in the File-Level Recovery Explorer may differ from the logical file system tree of the processed Azure VM. |

1. To restore the selected files and folders, click Restore and choose one of the available restore options:

* To restore copies of the selected files and folders to the original location, click Restore > Keep.

If files and folders with the same names exist in the original location, Veeam Data Cloud for Microsoft Azure will save the selected files to this file share using the following naming format: <file\_name>\_RESTORED\_<date>\_<time>. Otherwise, Veeam Data Cloud for Microsoft Azure will save the selected files with their original names.

* To overwrite the files and folders in the original location, click Restore > Overwrite.

If files and folders with the same names already exist in the original location, Veeam Data Cloud for Microsoft Azure will overwrite these files. Otherwise, Veeam Data Cloud for Microsoft Azure will save the selected files with the names from the backup.

As soon as you click Restore, Veeam Data Cloud for Microsoft Azure will save the selected files to their original location.

|  |
| --- |
| Note |
| If the folder that contains the restored items was deleted in the original location, Veeam Data Cloud for Microsoft Azure will prompt you to provide a new path for saving the restored items. |

[![Step 4. Select Files to Restore](images/azure_restore_vm_files_select.webp)](images/azure_restore_vm_files_select.webp)

