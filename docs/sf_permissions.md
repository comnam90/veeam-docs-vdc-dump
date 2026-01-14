---
title: "Permissions"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_permissions.html"
last_updated: "12/11/2025"
product_version: ""
---

# Permissions

In this article

To perform backup, restore and archival operations of Salesforce data, Veeam Data Cloud requires the following permissions to be provided.

Salesforce User

Veeam Data Cloud requires a Standard User with the Salesforce license type to connect to a Salesforce tenant to back up restore and archive Salesforce resources. Note that free Salesforce Integration Users cannot perform backup, restore and archival operations. The user whose credentials are used to authorize the connection must be assigned full permissions required to read and modify data.

Veeam Data Cloud can automatically assign specific permissions when you add a tenant or edit the backup policy. You must manually assign permissions that are not automatically assigned. For details on automatic assignment of permissions, see [Configure Backup Policy](sf_tenants_add_backup.md) and [Configure API Limits and Verify Permissions](sf_backup_policies_edit_connection.md).

| Permission type | Permission details | Automatically Assigned |
| --- | --- | --- |
| System Administrator profile | Assigning System Administrator profile to a Salesforce user grants broad permissions immediately, but not all the required ones. | No |
| General permissions | [Query All Files](https://help.salesforce.com/s/articleView?id=000381258&type=1) permission to back up and archive all files. If you do not provide the permission, file backup will be disabled in the backup policy. | Yes |
| [View Encrypted Data](https://help.salesforce.com/s/articleView?id=sf.fields_about_encrypted_fields.htm&type=5) permission to back up object records with encrypted fields (Salesforce Classic encryption). | Yes |
| [Modify All Data](https://help.salesforce.com/s/articleView?id=000384401&type=1) permission to archive data. | Yes |
| [Bulk API Hard Delete](https://help.salesforce.com/s/articleView?id=000385694&type=1) permission to use Bulk API while archiving data. | Yes |
| [View and Edit Converted Leads](https://help.salesforce.com/s/articleView?id=sf.leads_view_edit_converted.htm&language=en_US&type=5) permission to restore converted leads. | Yes |
| Permissions for all [custom record types of objects](https://help.salesforce.com/s/articleView?id=sf.perm_sets_record_types_assign.htm&language=en_US&type=5) to restore and archive records of custom types. | Yes |
| [Set Audit Fields upon Record Creation](https://help.salesforce.com/s/articleView?id=000386699&type=1) permission to restore original values in audit fields when restoring deleted records. | The permissions are automatically assigned if the "Set Audit Fields upon Record Creation" and "Update Records with Inactive Owners" organization-wide permission is enabled in your Salesforce tenant. |
| [Update Records with Inactive Owners](https://help.salesforce.com/s/articleView?id=000386699&type=1) permission to restore deleted records owned by inactive users. |
| [Update Email Messages](https://help.salesforce.com/s/articleView?id=release-notes.rn_service_email_user_perm.htm&release=244&type=5) permission to restore attachments of email messages. | Yes |
| [Author Apex](https://help.salesforce.com/s/articleView?id=000386957&type=1) permission to allow Veeam Data Cloud to restore Apex classes. This feature is not available for Salesforce Professional edition. | Yes |
| [Manage Authentication Providers](https://help.salesforce.com/s/articleView?id=xcloud.sso_provider_sfdc.htm&type=5) permission to allow Veeam Data Cloud to create and edit Authentication Providers. | Yes |
| [Prompt Template Manager](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_enable.htm&type=5) permission to allow Veeam Data Cloud to restore prompt templates. | The permission is automatically assigned if the Prompt Builder feature is enabled in your Salesforce tenant. |
| [Modify Metadata Through Metadata API Functions](https://help.salesforce.com/s/articleView?id=platform.meta_modify_metadata_perm.htm&type=5) permission to allow Veeam Data Cloud to create permission set with missing permissions (automatically assigned permissions). If the user whose credentials are used to authorize the connection is not assigned this permission, Veeam Data Cloud will display the Failed to assign required permissions because user doesn't have permission "Modify Metadata Through Metadata API Functions" message in the backup session log. | No |
| Connected app permission | [Approve Uninstalled Connected Apps](https://help.salesforce.com/s/articleView?id=005132365&type=1) permission to allow Veeam Data Cloud to register the VDC Salesforce Backup connected app in the target Salesforce tenant. This permission is required only when you add a Salesforce tenant for the first time to Veeam Data Cloud. After you add the Salesforce tenant successfully, it can be revoked. For details, see [Connect to Salesforce Tenant](sf_tenants_add_connect.md). | No |
| Permission set licenses | For any managed application license that is required for accessing the data. For example, HVS and CPQ. | No |
| Feature-based user licenses | Marketing User | Yes |
| Service Cloud User | No |
| Knowledge User | Yes |
| Salesforce CRM Content User | Yes |
| Einstein Prompt Templates | Yes |
| Salesforce CRM Content feature permissions | To allow Veeam Data Cloud to restore and archive files in libraries, the user must have the Salesforce CRM Content User option enabled and permission to manage all libraries granted. For more information, see [Salesforce Documentation](https://help.salesforce.com/s/articleView?id=experience.content_initialsetup.htm&type=5). | Yes |
| Salesforce CRM Content specific permissions | Manage Salesforce CRM Content to allow Veeam Data Cloud to restore and archive files in libraries if the Salesforce CRM content feature is enabled in the target Salesforce tenant. | The permissions are automatically assigned if the Salesforce CRM content feature is enabled in your Salesforce tenant. |
| Manage Content Permissions to allow Veeam Data Cloud to assign user roles for libraries if the Salesforce CRM content feature is enabled in the target Salesforce tenant. |
| Knowledge Base specific permissions | Allow View Knowledge | The permissions are automatically assigned if the Salesforce Knowledge feature is enabled in your Salesforce tenant |
| Manage Articles |
| Manage Salesforce Knowledge |
| Manage Data Categories |
| View Data Categories in Setup |

|  |
| --- |
| Note |
| Permissions that were provided to a user on production Salesforce tenant will not be automatically transferred when sandbox organization is created. Any managed application needs to be enabled and license provided to the user. For example, High Velocity Sales requires application activation. |

AWS Key Management Service

The IAM and key policies that Veeam Data Cloud uses when encrypting data with AWS KMS keys must provide permissions to perform the following operations. For more information on the IAM and key policies, see [AWS Documentation](https://docs.aws.amazon.com/kms/latest/developerguide/control-access.html).

| Operation | Details |
| --- | --- |
| ListKeys | Allows Veeam Data Cloud to get the list of available keys. |
| Encrypt | Allows Veeam Data Cloud to encrypt data with AWS KMS keys. |
| Decrypt | Allows Veeam Data Cloud to decrypt data with AWS KMS keys. |
| DescribeKey | Allows Veeam Data Cloud to retrieve information about AWS KMS keys. |

Page updated 12/11/2025
