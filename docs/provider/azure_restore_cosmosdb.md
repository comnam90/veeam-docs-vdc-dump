---
title: "Restoring Cosmos DB"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/azure_restore_cosmosdb.html"
last_updated: "2/26/2026"
product_version: ""
---

# Restoring Cosmos DB


In case a disaster strikes, you can restore an entire Cosmos DB account or its specific items from a timestamp. Veeam Data Cloud for Microsoft Azure allows you to restore one Cosmos DB account at a time to a new location.

|  |
| --- |
| Important |
| Consider the following:   * Point-in-time restore is not available for Cosmos DB accounts that have the Deleting status. * Point-in-time restore is not available for Cosmos DB for PostgreSQL accounts that have either the Deleted, Stopped or Dropping status. |

How to Restore Cosmos DB Account

To restore a Cosmos DB account to a point in time, do the following:

1. [Launch the Cosmos DB Restore wizard](azure_restore_cosmos_pit_launch.md)
2. [Select a restore point](azure_restore_cosmos_pit_point.md)
3. [Specify a service account](azure_restore_cosmos_pit_account.md)
4. [Configure restore settings](azure_restore_cosmos_pit_settings.md)
5. [Finish working with the wizard](azure_restore_cosmos_pit_summary.md)

