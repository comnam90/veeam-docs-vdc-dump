---
title: "Obtaining Downloaded Items"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_obtain_downloaded_items.html"
last_updated: "9/19/2025"
product_version: ""
---

# Obtaining Downloaded Items


When restoring Microsoft Exchange Online, OneDrive for Business, SharePoint Online and Teams data in Veeam Data Cloud for Microsoft 365, you can use the Download in background option. You can select this option in the following scenarios:

* You want to restore items whose total size exceeds 1 GB.
* The download process takes more than 3.5 minutes.
* The download process fails.

Consider that the maximum size for download in background of OneDrive for Business and SharePoint Online data is 200 GB.

After you select what Microsoft Exchange Online, OneDrive for Business, SharePoint Online or Teams items to restore, select the Download in background option, and click Download. The restore process begins in the background.

[![Obtaining Downloaded Items](images/m365_obtain_downloaded_items.png)](images/m365_obtain_downloaded_items.png "Obtaining Downloaded Items")

When the download process is completed, Veeam Data Cloud for Microsoft 365 notifies you.

To obtain the downloaded items, do the following:

1. Select Notifications.
2. In the list of notifications, find the restore session and click the link in the Name column.

[![Obtaining Downloaded Items](images/m365_obtain_downloaded_items_notifications.png)](images/m365_obtain_downloaded_items_notifications.png "Obtaining Downloaded Items")

1. In the window with the details of the operation, click Download File.

[![Obtaining Downloaded Items](images/m365_obtain_downloaded_items_download.png)](images/m365_obtain_downloaded_items_download.png "Obtaining Downloaded Items")

1. The items are saved to your browser download location.

|  |
| --- |
| tip |
| If you download a large mailbox, Veeam Data Cloud for Microsoft 365 will split the data into smaller .PST files, with each file representing up to 10 GB of the total size. For example, if your mailbox is 36 GB, Veeam Data Cloud for Microsoft 365 will generate a .ZIP file containing 4 .PST files: 3 .PST files of the 10 GB size and another .PST file of the 6 GB size. |

