---
title: "Performing File-Level Restore"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_restore_efs_item.html"
last_updated: "3/30/2026"
product_version: ""
---

# Performing File-Level Restore


In case a disaster strikes, you can recover corrupted or missing files of an EFS file system from a cloud-native backup. Veeam Data Cloud for AWS allows you to restore files and folders to the original file system or to another file system.

To recover files and folders of a protected file system, do the following:

1. [Launch the EFS File-level Recovery wizard](restore_item_launch_efs.md).
2. [Configure restore settings](restore_item_settings_efs.md).
3. [Specify account settings for restore](restore_item_account_efs.md).
4. [Choose a restore mode](restore_item_mode_efs.md).
5. [Specify a restore reason](restore_item_reason_efs.md).
6. [Finish working with the wizard](restore_item_finish_efs.md).

How EFS File-Level Recovery Works

To recover files and folders of a backed-up file system using specific file paths, Veeam Data Cloud for AWS sends an API request to AWS to restore the specified files to the selected file system.

