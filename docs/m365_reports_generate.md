---
title: "Generating Reports"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_reports_generate.html"
last_updated: "1/6/2026"
product_version: ""
---

# Generating Reports

In this article

You can generate reports on Veeam Data Cloud for Microsoft 365 usage. To do this, perform the following steps:

1. On the Microsoft 365 page, click the name of the tenant you want to manage.
2. Select Reports.
3. In the Generate tab, select the report you want to generate from the following options:

* Mailbox Protection Report. This report shows information about protected and unprotected mailboxes.

* User Protection Report. This report shows information about protected and unprotected users.

* Backup Summary Report. This report summarizes backup information for the specified month.
* Restore Activity Report. This report shows information about restore process activities.
* Backup Policy Detail Report. This report shows session information of backup policies for the specified month.

[![Generating Reports](images/m365_reports_generate.png)](images/m365_reports_generate.png "Generating Reports")

[For Backup Summary Report, Restore Activity Report and Backup Policy Detail Report] Select the month for which you want the report to be generated.

[![Generating Reports](images/m365_reports_generate_month.png)](images/m365_reports_generate_month.png "Generating Reports")

1. Click Generate Report. Veeam Data Cloud for Microsoft 365 will generate the report in the .CSV format.

* For Mailbox Protection Report and User Protection Report, Veeam Data Cloud for Microsoft 365 will display the The report is being generated and you will be notified once it is complete message.

Click Notifications to view the status of the report. In the list of notifications, click the link in the Name column of the notification about the report. Veeam Data Cloud will display a session log with detailed information.

In the window with the details of the operation, click Download File.

[![Generating Reports](images/m365_reports_generate_download.png)](images/m365_reports_generate_download.png "Generating Reports")

* The report is saved to your browser download location.

Report Fields

Veeam Data Cloud for Microsoft 365 generates reports in the .CSV format that include the following fields:

* Mailbox Protection Report

* The Mailbox field shows the mailbox name.

* The E-mail field shows the email address of the user.
* The Organization field shows the name of the company or organization in Veeam Data Cloud for Microsoft 365.
* The Protection Status field shows whether the mailbox is with the Protected or Unprotected status.
* The Last Backup Date field shows the date when the latest backup file was created by the user.

For example:

|  |
| --- |
| Mailbox,Email,Organization,Protection Status,Last Backup Date  Retail,Retail@example.onmicrosoft.com,example.onmicrosoft.com,Protected,8/4/2025  Megan Bowen,MeganB@example.onmicrosoft.com,example.onmicrosoft.com,Protected,8/4/2025  Alex Wilber,AlexW@example.onmicrosoft.com,example.onmicrosoft.com,Protected,8/4/2025 |

* User Protection Report

* The Username field shows the name of the Veeam Data Cloud for Microsoft 365 user.
* The E-mail field shows the email address of the Veeam Data Cloud for Microsoft 365 user.
* The Organization field shows the name of the company or organization in Veeam Data Cloud for Microsoft 365.
* The Protection Status field shows whether the user is with the Protected or Unprotected status.
* The Last Backup Date field shows the date when the latest backup file was created by the user.

For example:

|  |
| --- |
| Username,E-mail,Organization,Protection Status,Last Backup Date  Adele Vance,AdeleV@example.onmicrosoft.com,example.onmicrosoft.com,Protected,08/04/2025  Alex Wilber,AlexW@example.onmicrosoft.com,example.onmicrosoft.com,Protected,08/04/2025  Discovery Search Mailbox,DiscoverySearchMailbox{D919BA05-76A6-215f-40AD-7E09534BB852}@example.onmicrosoft.com,example.onmicrosoft.com,Protected,08/04/2025 |

* Backup Summary Report

* The Policy Name field shows the name of the backup policy.
* The Last status field shows the final status of the last run of the backup policy.
* The Last restore point field shows the date and time when the latest backup file was created. The field uses the following format: DD/MM/YYYY HH:MM:SS AM/PM, for example, 18/06/2024 08:03:40 AM.
* The Success Runs Count, Failure Runs Count and Warning Runs Count fields show how many backup sessions of a backup policy were processed with the Success, Failed and Warning statuses.
* The Objects Processed field shows the number of objects that were processed within the backup policy.
* The Data Transferred (GiB) field shows the amount of backed-up data within the backup policy.
* The TOTAL row shows the sum totals for each of the Number of successes, Number of failures, Number of warnings, Objects Processed and Data Transferred (GiB) columns.

For example:

|  |
| --- |
| Policy Name,Last status,Last restore point,Success Runs Count,Failure Runs Count,Warning Runs Count,Objects Processed,Data Transferred (GiB)  All Exchange objects - 2025-07-08\_14-39-09, Success, 03/08/2025 02:54:20 PM, 24, 0, 0, 83, 0.01  All other objects - 2025-07-08\_14-39-09, Success, 03/08/2025 02:57:06 PM, 24, 0, 0, 2712, 0.11  TOTAL,,,48,0,0, 2795,0.12 |

* Restore Activity Report

* The Session Type field shows the type of the restore session.
* The Initiated By field shows the email of the Veeam Data Cloud for Microsoft 365 user who performed the restore activity.
* The Action field shows what kind of restore action was performed.
* The Object field shows the objects that were processed within the restore session.
* The Date field shows the date and time when the restore activity was performed.
* The Items field shows the items that were processed within the restore session.

For example:

|  |
| --- |
| Session Type,Initiated By,Action,Object,Date,Items  Teams,JOHN.DOE@EXAMPLE.COM,CreateRestoreSession,Teams,24/07/2025 10:09:26 AM,"{""SessionType"":""vet"",""DateTime"":""2025-07-23T14:40:23.425Z""}"  Outlook,JOHN.DOE@EXAMPLE.COM,CreateRestoreSession,Exchange,24/07/2025 10:02:19 AM,"{""SessionType"":""vex"",""DateTime"":""2025-07-23T14:40:14.277Z""}"  Teams,JOHN.DOE@EXAMPLE.COM,CreateRestoreSession,Teams,24/07/2025 09:59:33 AM,"{""SessionType"":""vet"",""DateTime"":""2025-07-23T14:40:23.425Z""}"  SharePoint,JOHN.DOE@EXAMPLE.COM,CreateRestoreSession,SharePoint,24/07/2025 09:57:27 AM,"{""SessionType"":""vesp"",""DateTime"":""2025-07-23T14:40:23.425Z""}" |

* Backup Policy Detail Report

* The Job name field shows the name of the backup policy.
* The Start Time field shows the date and time when the backup policy was started.
* The End Time field shows the date and time when the backup policy was finished.
* The Job Type field shows whether the type of the backup policy is Backup or Copy.
* The Status field shows the session run status of a backup policy.
* The Objects Processed field shows the number of objects that were processed in the backup policy.
* The Summary field shows information in case of a failed backup policy.

The Backup Policy Detail Report does not include information about Express backup policies.

For example:

|  |
| --- |
| Job Name,Start Time,End Time,Job Type,Status,Objects Processed,Summary  All Exchange objects - 2025-07-08\_14-39-09,08/07/2025 4:39:09 PM,08/07/2025 4:40:07 PM,Backup,Success,79,  All other objects - 2025-07-08\_14-39-09,08/07/2025 4:39:09 PM,08/07/2025 4:53:08 PM,Backup,Success,2712,  All other objects - 2025-07-08\_14-39-09,09/07/2025 4:39:09 PM,09/07/2025 4:40:26 PM,Backup,Success,0,  All Exchange objects - 2025-07-08\_14-39-09,09/07/2025 4:39:09 PM,09/07/2025 4:40:54 PM,Backup,Success,0, |

Page updated 1/6/2026
