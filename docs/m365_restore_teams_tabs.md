---
title: "Restoring Tabs"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_restore_teams_tabs.html"
last_updated: "9/19/2025"
product_version: ""
---

# Restoring Tabs


To restore a Microsoft Teams channel tab:

1. On the Microsoft 365 page, click the name of the tenant you want to work with.

|  |
| --- |
| Note |
| Consider the following:   * If the organization does not have any backups, the Teams Restore tab will be empty.  * Backup and restore of Microsoft Teams data is available to users of the Flex and Premium plans only. Users can restore Teams data flexibly and do not need to select the restore method. * Before you start performing restore, check [Considerations and Limitations](m365_considerations_limitations.md#restore). |

1. Select Restore.
2. On the Teams tab, expand the team whose channel tab you want to restore.
3. Expand the channel whose tab you want to restore and select Other Tabs.
4. Select the check box next to the necessary tab in the list of items. You can select multiple tabs.
5. Click Restore Selected Tab Item.

[![Restoring Teams Tabs](images/m365_restore_teams_tabs.png)](images/m365_restore_teams_tabs.png "Restoring Teams Tabs")

1. In the Restore Tab Item window, check the name of the team, channel and tab you want to restore, and the time when the backup was created.
2. In the Restore to section, check that the Original location option is selected. You can restore channel tabs to their original location only. Other restore options are unavailable.
3. If you want to specify advanced restore options, in the Restore the following items section, do the following:

1. Select the Changed items check box if you want to restore items that have changed since the time when the backup was created. When you select this option, Veeam Data Cloud for Microsoft 365 overwrites existing items in the original team.
2. Select the Missing items check box if you want to restore items that are missing in the original team. For example, some of the items were removed and you want to restore them from the backup.

1. Click Restore to restore the channel tab according to the specified restore options.

[![Restoring Teams Tabs](images/m365_restore_teams_tabs_original.png)](images/m365_restore_teams_tabs_original.png "Restoring Teams Tabs")

