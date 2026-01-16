---
title: "Considerations and Limitations"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_limitations.html"
last_updated: "1/12/2026"
product_version: ""
---

# Considerations and Limitations

In this article

When you plan to protect your Salesforce data with Veeam Data Cloud, keep in mind the following limitations and considerations.

Supported Salesforce Offerings

* Salesforce provides multiple offerings that are built on one Salesforce Platform — Sales Cloud, Service Cloud, Financial Cloud, Health Cloud and Education. Veeam Data Cloud supports backup of all data and objects available on the Salesforce Platform if these resources can be retrieved using the Salesforce API version 63.0 and earlier. This means that if an object or data cannot be obtained using standard Salesforce API requests, backup of these objects is not supported.

Salesforce Marketing Cloud is built on another platform and is not protected by the product.

* Both Salesforce Classic and Lightning Experience interfaces are supported.
* Salesforce production and sandbox tenants can be protected by Veeam Data Cloud.

* All Salesforce API-enabled editions are supported: Developer, Enterprise, Performance, Professional (API access must be enabled), Unlimited.

Salesforce User

* Set the English language in the locale and account language settings for the user in Salesforce. It is required for error handler to work properly.
* Make sure that you have assigned the user all the [required permissions](sf_permissions.md). Note that if a Salesforce user does not have permissions required to back up specific files or object fields, Veeam Data Cloud will not be able able to back up these files or fields. To work around the issue, reload object fields or files as described in section [Reloading Fields and Files](sf_activity_backup_reload_fields.md).

Salesforce Session

* To allow Veeam Data Cloud to connect to your Salesforce tenant, make sure that the Lock sessions to the IP address from which they originated option is disabled. For more details on how to set this option, see [Salesforce Documentation](https://help.salesforce.com/s/articleView?id=000380975&type=1).
* If you restrict login IP addresses in Salesforce user profiles, you may need to add at least two specific Veeam Data Cloud IP addresses to the allowed login IP ranges in your Salesforce tenant. If necessary, Veeam Data Cloud will request that you do so when adding your Salesforce tenant. The required IP addresses may be different for each Salesforce tenant you add. For more details on how to specify allowed IP ranges, see [Salesforce Documentation](https://help.salesforce.com/s/articleView?id=platform.login_ip_ranges.htm&type=5).

|  |
| --- |
| Tip |
| To be notified as soon as possible if the connection to your Salesforce tenant is not working correctly, specify an email recipient for the Salesforce Connection notification with the notify on error option. For details, see [Managing Notifications](sf_settings_notifications.md). |

Backup and Restore

* Backup and restore of EmailTemplate, Document, Report and Dashboard types of metadata objects located in private folders are not supported since Salesforce does not provide API to export and restore this type of data.
* Backup of KnowledgeArticle types of objects is not supported.
* Backup of BigObject types of objects is not supported.
* Backup and restore of TenantSecret types of objects is not supported.
* Backup of embedded images added to ContentNote types of objects is not supported.
* Backup of embedded images in rich text area fields is supported only if the fields are not encrypted.
* Backup of FeedItem and FeedAttachment types of objects can be performed only when back up of ContentVersion object is enabled.

* Restore of the Apex class metadata type is not supported in the Professional edition due to Salesforce API limitations.

* Restore of MobileApplicationDetail and MailmergeTemplate types of content is not supported.
* Restore of embedded images deleted from ContentNote types of objects is not supported.
* Restore of FeedAttachment types of objects can be performed only when restoring the related FeedItem object hierarchy and only if the related FeedItem object is deleted from Salesforce.
* Restore of ContentVersion types of objects can be performed only if they were added as attachments (not embedded images) to the related FeedItem object.
* Backup of Salesforce objects listed in [Unsupported Salesforce Objects](sf_unsupported_objects.md) is not supported.
* Backup of certain metadata types is not supported due to Salesforce limitations. For more information, see [Salesforce Documentation](https://developer.salesforce.com/docs/atlas.en-us.api_meta.meta/api_meta/meta_unsupported_types.htm).

|  |
| --- |
| Important |
| For fields that already have backups, it is recommended that you do not change their types in Salesforce since this may cause backup failures. |

Page updated 1/12/2026
