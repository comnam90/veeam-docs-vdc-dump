---
title: "Restoring SharePoint Folders"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_restore_sharepoint_folders.html"
last_updated: "9/19/2025"
product_version: ""
---

# Restoring SharePoint Folders

In this article

Before you start performing restore, check [Considerations and Limitations](m365_considerations_limitations.md#restore).

To restore a SharePoint folder from the backup:

1. On the Microsoft 365 page, click the name of the tenant you want to manage.
2. Select Restore.
3. On the SharePoint tab, expand the SharePoint site and library that contains the folder you want to restore.
4. Select the SharePoint folder you want to restore.
5. Click Restore Selected Folder.

[![Restoring SharePoint Folders](images/m365_restore_sharepoint_folders.png)](images/m365_restore_sharepoint_folders.png "Restoring SharePoint Folders")

1. In the Restore SharePoint Folder window, check the name of the folder you want to restore and the time when the backup that contains the folder was created.
2. In the Restore to section, select where to restore the SharePoint folder. You can select one of the following options:

* Original location. Select this option if you want to restore the folder to its original location.

1. Restore items to the original list. If you select this option, the folder will be restored to the Documents list of the original site.
2. Restore items to the following list. If you select this option, type the name of the list. The folder will be restored to the original site, to the list you specified. If the target list does not exist, the restore process will fail.

* The following site alias. Select this option if you want to restore the folder to another site within the same SharePoint instance. Type the site alias. Veeam Data Cloud for Microsoft 365 will display the resulting URL of the target site. If the target site does not exist, the restore process will fail.

1. Restore items to the original list. If you select this option, the folder will be restored to the Documents list of the site you specified.
2. Restore items to the following list. If you select this option, type the name of the list. The folder will be restored to the site and list you specified. If the target list does not exist, the restore process will fail.

You can click Advanced options to display more options. For details, see the next step of the procedure.

* Local computer. Select this option if you want to download the SharePoint folder to your computer. Use this option for SharePoint folders whose size does not exceed 1 GB. Veeam Data Cloud for Microsoft 365 will save the SharePoint folder to a .ZIP file.
* Download in background. Select this option if you want to download the SharePoint folder to your computer. Use this option for SharePoint folders whose size exceeds 1 GB or if the download process takes more than 3.5 minutes. Veeam Data Cloud for Microsoft 365 will save the SharePoint folder to a .ZIP file. For more information on how to get the downloaded data, see [Obtaining Downloaded Items](m365_obtain_downloaded_items.md).

[![Restoring SharePoint Folders](images/m365_restore_sharepoint_folders_original.png)](images/m365_restore_sharepoint_folders_original.png "Restoring SharePoint Folders")

1. [For restore to another site] If you want to specify advanced restore options, do the following:

1. Click Advanced options.
2. In the Restore the following items section, do the following:

1. Select the Changed items check box if you want to restore items that have been modified in the production environment.
2. Select the Missing items check box if you want to restore items that are missing in your target location. For example, some of the items were removed and you want to restore them from the backup.

1. In the History restore options section, select the Restore only the latest version check box if you want to restore only the latest version of items. If you select this check box, you can select one of the following options:

* Overwrite. Select this option to overwrite items in the production environment with the latest version of items in the backup.
* Merge. Select this option to merge the latest version of items in the backup into items in the production environment.

[![Restoring SharePoint Folders](images/m365_restore_sharepoint_folders_options.png)](images/m365_restore_sharepoint_folders_options.png "Restoring SharePoint Folders")

1. Start the restore process:

* Click Restore if you selected to restore data to the original location or to a site alias.
* Click Download if you selected to download data to the local computer or download data in the background.

Page updated 9/19/2025
