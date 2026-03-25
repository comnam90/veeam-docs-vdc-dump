---
title: "Adding Microsoft 365 Tenants"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_tenant_add.html"
last_updated: "3/24/2026"
product_version: ""
---

# Adding Microsoft 365 Tenants


To start protecting the Microsoft 365 tenant data, you must add the Microsoft 365 tenant to Veeam Data Cloud.

Before you start adding the tenant, check [Considerations and Limitations](m365_considerations_limitations.md).

For information on how to add a multi-geo tenant to Veeam Data Cloud, see [Adding Multi-Geo Microsoft 365 Tenants](m365_tenant_add_multigeo.md).

To add a Microsoft 365 tenant, use the Add Microsoft 365 tenant wizard and do the following:

1. Click Microsoft 365 on the left to open the list of Microsoft 365 tenants.
2. Click Add Tenant.

[![Launching Add Microsoft 365 Tenant Wizard](images/m365_tenant_add_launch.png)](images/m365_tenant_add_launch.png "Launching Add Microsoft 365 Tenant Wizard")

|  |
| --- |
| Note |
| If you are a customer of a Veeam Cloud & Service Provider partner, you cannot launch the Add Microsoft 365 tenant wizard. Ask your service provider to add your Microsoft 365 tenant or send you an email with an invitation link that allows you to launch the wizard. |

1. Choose how you want to connect Veeam Data Cloud to the Microsoft tenancy:

* Auto Connection. Select this option if you want to automatically connect Veeam Data Cloud to the Microsoft tenancy. This option is recommended and selected by default. Follow the [Automatic Connection Steps](#auto) instructions to proceed.
* Manual Connection. Select this option if you want to manually connect  Veeam Data Cloud to the Microsoft tenancy. Follow the [Manual Connection Steps](#manual) instructions to proceed.

[![Adding Microsoft 365 Tenant](images/m365_tenant_add_connection.webp)](images/m365_tenant_add_connection.webp "Adding Microsoft 365 Tenant")

Automatic Connection Steps

|  |
| --- |
| note |
| To perform the steps successfully, you must use a Microsoft 365 Global Admin account. |

If you choose to automatically connect Veeam Data Cloud to your Microsoft 365 tenancy (recommended), do the following:

1. In the Choose the type of Flex connection section, select Auto Connection.
2. If you also have a subscription to the Premium license plan and want to connect Microsoft Backup Storage to Veeam Data Cloud, select the Include Express Connection check box. To skip the Express connection, do not select the check box.

After you add the tenant, you must also enable the Express backup service in order to create Express backup policies. For more information, see [Enabling Express Backup](m365_settings_enable_express_backup.md).

1. Click Sign in with Microsoft.

[![Adding Microsoft 365 Tenant](images/m365_tenant_add_signin.webp)](images/m365_tenant_add_signin.webp "Adding Microsoft 365 Tenant")

1. In the Microsoft authentication window, select the Microsoft account under which you want to authenticate against Microsoft 365. The account must have the Microsoft 365 Global Admin permissions.
2. Accept the required permissions.
3. Return to Veeam Data Cloud. If the connection is successful, Veeam Data Cloud displays the following message: Connected. We have successfully established a connection with account Microsoft 365 Global Admin.
4. Specify the tenant settings:

1. In the Tenant Name field, specify a name for the new tenant.
2. From the Storage Region drop-down list, select a Microsoft Azure region where the backup infrastructure and storage will be provisioned.

For information on supported Microsoft Azure regions, see [Backup Storage Regions](m365_region_availability.md).

1. In the Select the service you want to protect section, make sure to select only the services that are available in the Microsoft 365 tenant that you are connecting to.
2. In the Backup policy type section, select one of the following options:

* Auto-create policies. This option is recommended and enables automatic backup policies for all users, sites and teams.

In the Retention Period section, set the number of Years or Days for the retention period of your backups, or select Unlimited to keep the backups for an indefinite time.

Once you set the retention period, you cannot reduce it. For more information, see [Backup Retention](m365_data_backup.md#retention).

* Manually create policies. This option allows you to manually configure your backup policies after onboarding.

1. Click Create Tenant.

[![Adding Microsoft 365 Tenant](images/m365_tenant_add_create.webp)](images/m365_tenant_add_create.webp "Adding Microsoft 365 Tenant")

Manual Connection Steps

If you choose to manually connect Veeam Data Cloud to the Microsoft 365 tenancy, do the following:

1. In Microsoft Entra ID, do the following:

1. Create a new App Registration.
2. Assign the [required permissions](m365_permissions.md) to the new application registration.
3. Create and assign a certificate to the application.

X.509 compatible certificates from a trusted CA (Certificate Authority) and self-signed certificates are supported. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/entra/identity-platform/how-to-add-credentials?tabs=certificate).

1. Export the certificate to a PFX file. You will use this file at step 4-c of this procedure.
2. On the overview page of the application, copy the Application (client) ID value.

1. In Veeam Data Cloud for Microsoft 365, in the Choose the type of Flex connection section, select Manual Connection.
2. Specify the following:

1. In the User Account Email field, type the email address of a Microsoft 365 user account that belongs to your Microsoft 365 tenant.
2. In the App Registration ID field, type the Application (client) ID value that you copied during the application registration in Microsoft Entra ID.
3. In the App Certificate field, click Browse and select the PFX certificate file that you exported from Microsoft Entra ID.
4. In the Certificate Password field, only type the password if you have exported the certificate with password protection enabled.

[![Manually Adding Microsoft 365 Tenant](images/m365_tenant_add_connect_manually.webp)](images/m365_tenant_add_connect_manually.webp "Manually Adding Microsoft 365 Tenant")

1. Click Connect. If the connection is successful, Veeam Data Cloud displays the following message: Connected. We have successfully established a connection with account Microsoft 365 account.
2. Specify the tenant settings:

1. In the Tenant Name field, specify a name for the new tenant.
2. From the Storage Region drop-down list, select a Microsoft Azure region where the backup infrastructure and storage will be provisioned.

For information on supported Microsoft Azure regions, see [Backup Storage Regions](m365_region_availability.md).

1. In the Select the service you want to protect section, make sure to select only the services that are available in the Microsoft 365 tenant that you are connecting to.
2. In the Backup policy type section, select one of the following options:

* Auto-create policies. This option is recommended and enables automatic backup policies for all users, sites and teams.

In the Retention Period section, set the number of Years or Days for the retention period of your backups, or select Unlimited to keep the backups for an indefinite time.

Once you set the retention period, you cannot reduce it. For more information, see [Backup Retention](m365_data_backup.md#retention).

* Manually create policies. This option allows you to manually configure your backup policies after onboarding.

1. Click Create Tenant.

[![Adding Microsoft 365 Tenant](images/m365_tenant_add_create.webp)](images/m365_tenant_add_create.webp "Adding Microsoft 365 Tenant")

1. Once the new tenant is provisioned, if you also have a subscription to the Premium license plan, you can connect Microsoft Backup Storage to Veeam Data Cloud. Click Sign in with Microsoft.

You can click Skip to skip this step if you do not want to connect the tenant to Express backups.

[![Manually Adding Microsoft 365 Tenant](images/m365_tenant_add_connection_express.webp)](images/m365_tenant_add_connection_express.webp "Manually Adding Microsoft 365 Tenant")

1. In the Microsoft authentication window, select the Microsoft account under which you want to authenticate against Microsoft 365. The account must have the Microsoft 365 Global Admin permissions.
2. Accept the required permissions.
3. Return to Veeam Data Cloud. If the connection is successful, Veeam Data Cloud displays the following message: The authorization process has been completed successfully.

After you add the tenant, you must also enable the Express backup service in order to create Express backup policies. For more information, see [Enabling Express Backup](m365_settings_enable_express_backup.md).

1. Click Ok.

|  |
| --- |
| tip |
| To ensure the manual connection is successful, confirm the following:   * You created an application registration in your Microsoft Entra ID and not an Enterprise application. * The manually created app registration is within the correct tenant ID. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/sharepoint/find-your-office-365-tenant-id). * You assigned all the required permissions to the application registration and ensured that all required permissions are consented to. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/entra/identity-platform/application-consent-experience). |

