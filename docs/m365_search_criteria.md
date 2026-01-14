---
title: "Advanced Search Criteria"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_search_criteria.html"
last_updated: "8/19/2025"
product_version: ""
---

# Advanced Search Criteria

In this article

When you use advanced search to search for objects in backups created by Veeam Data Cloud for Microsoft 365, you can customize the search with parameters and conditions to narrow the search criteria.

To specify the primary and secondary search criteria, you select a category, select a field associated with that category, set a condition for the search and then add or select a value for the search.

For example, if you want to search for an email with a specific word in the email subject, you set the following criteria:

Category: Common Fields; Field: Subject; Condition: contains; Value: contract

Veeam Data Cloud for Microsoft 365 searches whether the subject of an email in the backup of the Outlook mailbox contains the word contract.

The available conditions are the following:

* contains
* doesn't contain
* is exactly
* is not
* between
* less than
* less than or equal
* greater than
* greater than or equal

The specific search categories, fields and values for each application are described in the following tables:

* [Outlook](#outlook)
* [OneDrive and SharePoint](#one)
* [Teams](#team)

Outlook

The following table contains parameters that you can set in advanced search for Outlook backups.

| Category | Field | Value |
| --- | --- | --- |
| Common Fields | Size | number and size unit (for example, 1KB, 1MB, 1GB) |
| Subject | text |
| Body | text |
| Categories | text |
| Company | text |
| Date Completed | Choose date from calendar (dd/mm/yyyy) |
| Date Created | Choose date from calendar (dd/mm/yyyy) |
| Date Modified | Choose date from calendar (dd/mm/yyyy) |
| Due Date | Choose date from calendar (dd/mm/yyyy) |
| End Date | Choose date from calendar (dd/mm/yyyy) |
| Flag | true or false |
| Flag Status | NotFlagged, Completed or FollowUp |
| Message | Bcc Address | text |
| Bcc Name | text |
| Cc Address | text |
| Cc Name | text |
| From Address | text |
| From Name | text |
| Received | Choose date from calendar (dd/mm/yyyy) |
| Sender Address | text |
| Sender Name | text |
| Sent | Choose date from calendar (dd/mm/yyyy) |
| To Address | text |
| To Name | text |
| Attachment Contains | text |
| Attachments | true or false |
| Color | Blue, Green Pink, Yellow, White or LightGreen |
| Owner | text |
| Calendar | Duration | text |
| Location | text |
| Optional Attendee Addresses | text |
| Optional Attendees | text |
| Organizer | text |
| Organizer Address | text |
| Recurring | true or false |
| Reminder Time | Choose date from calendar (dd/mm/yyyy) |
| Required Attendee Addresses | text |
| Required Attendees | text |
| Response Status | None, Organized, Tentative, Accepted, Declined or NotResponded |
| Show Time As | text |
| Contact | Assistant Name | text |
| Assistant's Phone | text |
| Birthday | Choose date from calendar (dd/mm/yyyy) |
| Business Address | text |
| Business Address City | text |
| Business Address Postal Code | text |
| Business Address Street | text |
| Business Fax | text |
| Business Home Page | text |
| Business Phone | text |
| Callback Phone Number | text |
| Car Phone | text |
| Children | text |
| Department | text |
| Email | text |
| First Name | text |
| Full Name | text |
| Home Address | text |
| Home Address City | text |
| Home Address Postal Code | text |
| Home Address Street | text |
| Home Fax | text |
| Home Phone | text |
| IM Address | text |
| Last Name | text |
| Mailing Address | text |
| Mobile Phone | text |
| Nickname | text |
| Office Location | text |
| Other Address | text |
| Other Address City | text |
| Other Address Postal Code | text |
| Other Address Street | text |
| Pager | text |
| Policy Title | text |
| Profession | text |
| Spouse | text |
| Title (Personal) | text |
| Webpage | text |

OneDrive and SharePoint

The following table contains parameters that you can set in advanced search for OneDrive and SharePoint backups.

| Category | Field | Value |
| --- | --- | --- |
| Contact | Full Name | text |
| Anniversary | Choose date from calendar (dd/mm/yyyy) |
| Assistant Number | text |
| Assistant's Name | text |
| Birthday | Choose date from calendar (dd/mm/yyyy) |
| Business Telephone | text |
| Callback Number | text |
| Car Number | text |
| Company Number | text |
| Company Phonetic | text |
| Department | text |
| Email Address | text |
| Email Sender | text |
| First Name | text |
| First name pronunciation | text |
| Gender | text |
| Hobbies | text |
| Home Address City | text |
| Home Address Country | text |
| Home Address Postal Code | text |
| Home Address State or Province | text |
| Home Address Street | text |
| Home Fax Number | text |
| Home Telephone | text |
| IM Address | text |
| Initials | text |
| Last Name Phonetic | text |
| Middle Name | text |
| Mobile Telephone | text |
| Nickname | text |
| Office Location | text |
| Other Address City | text |
| Other Address Country | text |
| Other Address Postal Code | text |
| Other Address State | text |
| Other Address Street | text |
| Pager Number | text |
| Primary Number | text |
| Profession | text |
| Spouse Name | text |
| Suffix | text |
| Telex Number | text |
| TTYTDD Number | text |
| Work Address | text |
| Work City | text |
| Work Country | text |
| Work Fax | text |
| Work State | text |
| Work Zip | text |
| File Fields | File Extension | text |
| File Name | text |
| Object Type | text |
| User Name | text |
| Billing Information | text |
| Body | text |
| Computer Network Name | text |
| Contributor | text |
| Copyright | text |
| Date Completed | Choose date from calendar (dd/mm/yyyy) |
| Date Created | Choose date from calendar (dd/mm/yyyy) |
| Date Modified | Choose date from calendar (dd/mm/yyyy) |
| Deleted | true or false |
| Description | text |
| Due Date | Choose date from calendar (dd/mm/yyyy) |
| Email Cc | text |
| Email From | text |
| Email To | text |
| End Date | Choose date from calendar (dd/mm/yyyy) |
| File Size | number and size unit (for example, 1KB, 1MB, 1GB) |
| Folder Child Count | text |
| Folder Path | text |
| Has Attachments | true or false |
| Image Height | text |
| Image Width | text |
| Item Path | text |
| Item URL | text |
| Language | text |
| Last Author | text |
| Length (seconds) | text |
| Mark As Read | true or false |
| Mileage | text |
| Personal Website | text |
| Publisher | text |
| Revision | text |
| Source | text |
| Start Date | Choose date from calendar (dd/mm/yyyy) |
| Status | text |
| Subject | text |
| Title | text |
| Version | text |
| Common Fields | Category | text |
| Comment | text |
| Company | text |
| Created By | text |
| Expires | Choose date from calendar (dd/mm/yyyy) |
| Task Status | text |

Teams

The following table contains parameters that you can set in advanced search for Teams backups.

| Category | Field | Value |
| --- | --- | --- |
| File Fields | Created | Choose date from calendar (dd/mm/yyyy) |
| Created By | text |
| File Extension | text |
| Modified | Choose date from calendar (dd/mm/yyyy) |
| Modified By | text |
| Name | text |
| Size | number and size unit (for example, 1KB, 1MB, 1GB) |
| Version | text |

Page updated 8/19/2025
