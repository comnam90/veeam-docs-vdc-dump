---
title: "Viewing Session Logs"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_logs_session.html"
last_updated: "5/12/2026"
product_version: ""
---

# Viewing Session Logs


You can view all backup and restore sessions on the Session Logs page.

To view the details of a specific session, do the following:

1. In the Management section of the main menu, select Session Logs.
2. Locate the session whose details you want to view. You can search for a session by policy or protected workload name, and filter sessions by type, run time and status.

|  |
| --- |
| Tip |
| During Azure Cosmos DB restore, Veeam Data Cloud for Microsoft Azure always writes data to a new target location, and the session log records only the target account name. To find a Cosmos DB restore session, search by the target account name. Searching by the source account name returns no results. |

1. Select the session and click View Details. Alternatively, right-click the session and choose View Details from the context menu.

[![Viewing Session Logs](images/azure_logs_session.png)](images/azure_logs_session.png)

