---
title: "Restoring Files"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/sf_restore_files.html"
last_updated: "3/28/2025"
product_version: ""
---

# Restoring Files


File restore jobs allow you to recover changed and deleted content and attachments.

Before you restore files, consider the following:

* When you restore any of the previous content versions of an existing Salesforce document, Salesforce creates a new version of this content document.
* When you restore an attachment, Veeam Data Cloud creates a new file with the same file name and new ID. If the source file still exists, the file content is be updated.
* Restore of the MobileApplicationDetail and MailmergeTemplate types of content is not supported in Veeam Data Cloud.
* Restore of embedded images deleted from ContentNote, FeedItem and FeedComment types of objects is not supported.
* Restore of FeedAttachment types of objects can be performed only when restoring the related FeedItem object hierarchy. Note that ContentVersion types of objects can be restored only if they were added as attachments (not embedded images) to FeedItem types of objects.
* To restore an attachment of an email message, the user whose credentials are used to authorize the connection to Salesforce must be assigned the Update Email Messages permission. For more information, see [Permissions](sf_permissions.md).

To restore files, take the following steps:

1. [Launch the Restore Files wizard](sf_restore_files_launch.md).
2. [Specify a name and description for the restore job](sf_restore_files_name.md).
3. [Select a target Salesforce tenant](sf_restore_files_organization.md).
4. [Select files and attachments to restore](sf_restore_files_files.md).
5. [Finish working with the wizard](sf_restore_files_summary.md).

