---
title: "Restoring Shared Items"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_restore_teams_files.html"
last_updated: "3/24/2026"
product_version: ""
---

# Restoring Shared Items


You can use Veeam Data Cloud for Microsoft 365 to restore shared items of Microsoft Teams channels. You can restore either all shared items of a channel or specific shared items.

Restoring All Shared Items

To restore all shared items of a Microsoft Teams channel:

1. On the Microsoft 365 page, click the name of the tenant you want to manage.

|  |
| --- |
| Note |
| Consider the following:   * If the organization does not have any backups, the Teams Restore tab will be empty.  * Backup and restore of Microsoft Teams data is available to users of the Foundation and Premium plans only. Users can restore Teams data flexibly and do not need to select the restore method. * Before you start performing restore, check [Considerations and Limitations](m365_considerations_limitations.md#restore). |

1. Select Restore.
2. On the Teams tab, expand the team whose channel shared items you want to restore.
3. Expand the channel whose shared items you want to restore and select Shared.
4. Click Restore Selected Shared.

[![Restoring Teams Files](images/m365_restore_teams_files.png)](images/m365_restore_teams_files.png "Restoring Teams Files")

1. In the Restore Shared window, check the name of the team and channel whose shared items you want to restore, and the time when the backup was created.
2. In the Restore to section, select where to restore shared items. You can select one of the following options:

* Original location. Select this option if you want to restore shared items to the original channel.
* Download in background. Select this option if you want to download the shared items to your computer. For more information on how to get the downloaded data, see [Obtaining Downloaded Items](m365_obtain_downloaded_items.md).

1. [For restore to the original location] If you want to specify advanced restore options, do the following:

1. In the Restore the following items section, do the following:

1. Select the Changed items check box if you want to restore items that have changed since the time when the backup was created. When you select this option, Veeam Data Cloud for Microsoft 365 overwrites existing items in the original team.
2. Select the Missing items check box if you want to restore items that are missing in the original team. For example, some of the items were removed and you want to restore them from the backup.

1. In the History restore options section, select the Restore only the latest version check box if you want to restore only the latest version of items.

1. Start the restore process:

* Click Restore if you selected to restore data to the original location.
* Click Download if you selected to download data in the background.

[![Restoring Teams Files](images/m365_restore_teams_files_original.png)](images/m365_restore_teams_files_original.png "Restoring Teams Files")

Restoring Specific Shared Items

To restore specific shared items of a Microsoft Teams channel:

1. On the Microsoft 365 page, click the name of the tenant you want to manage.
2. Select Restore.
3. On the Teams tab, expand the team whose channel shared items you want to restore.
4. Expand the channel whose shared items you want to restore and select Shared.
5. Select the check box next to the necessary shared items in the list of items and click Restore Selected Shared Item. You can select multiple items.

[![Restoring Teams Files](images/m365_restore_teams_files_specific.png)](images/m365_restore_teams_files_specific.png "Restoring Teams Files")

1. In the Restore Shared Item window, check the name of the team, channel and shared item you want to restore, and the time when the backup was created.
2. In the Restore to section, select where to restore shared items. You can select one of the following options:

* Original Location. Select this option if you want to restore shared items to the original channel.
* Download in background. Select this option if you want to download the shared items to your computer.

1. [For restore to the original location] If you want to specify advanced restore options, do the following:

1. In the Restore the following items section, do the following:

1. Select the Changed items check box if you want to restore items that have changed since the time when the backup was created. When you select this option, Veeam Data Cloud for Microsoft 365 overwrites existing items in the original team.
2. Select the Missing items check box if you want to restore items that are missing in the original team. For example, some of the items were removed and you want to restore them from the backup.

1. In the History restore options section, select the Restore only the latest version check box if you want to restore only the latest version of items.

1. Start the restore process:

* Click Restore if you selected to restore data to the original location.
* Click Download if you selected to download data in the background.

[![Restoring Teams Files](images/m365_restore_teams_files_specific_options.png)](images/m365_restore_teams_files_specific_options.png "Restoring Teams Files")

