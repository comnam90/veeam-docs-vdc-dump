---
title: "BYOK Encryption"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_settings_byok_encryption.html"
last_updated: "12/4/2025"
product_version: ""
---

# BYOK Encryption

In this article

Veeam Data Cloud for Microsoft 365 offers BYOK (Bring Your Own Key) encryption as a Limited Availability Preview for added control over your backup data. Only customers of Veeam Data Cloud for Microsoft 365 Premium can participate in this early access program. With BYOK encryption, you host, manage and control the encryption keys on your own Microsoft Azure Key Vault. Veeam Data Cloud for Microsoft 365 encrypts your backup data and never stores the encryption keys. You can revoke the Veeam Data Cloud access at any time.

Before You Begin

Before you can request to use BYOK encryption, you must fulfill the following prerequisites:

* You must have a paid Microsoft Azure subscription.
* You must have a Microsoft 365 tenancy connected to Veeam Data Cloud. You can encrypt an existing Microsoft 365 workload tenant or add a new one. For details, see [Adding Microsoft 365 Tenants](m365_tenant_add.md).
* You must have Microsoft Azure Key Vault.
* The user account performing the process must have permissions to create and manage app registrations and client secrets, create and manage Key Vault keys and assign RBAC roles.

Configuring BYOK Encryption

To protect Veeam Data Cloud for Microsoft 365 backups with BYOK encryption, follow these steps:

1. [Create a new application registration and client secret in Microsoft Entra ID](#appreg).
2. [Create and configure a key in your Microsoft Azure Key Vault](#key).
3. [Contact Veeam Customer Support with the required information](#supp).

Creating New App Registration

To create a new application registration in your Microsoft tenancy, go to Microsoft Entra ID and do the following:

1. Go to App registrations and click New Registration.

1. Specify a name for the application registration.
2. In Supported account types, select Accounts in this organizational directory only (Single tenant).
3. Click Register.

For more information on how to create an application registration, see [this Microsoft article](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app).

|  |
| --- |
| NOTE |
| To maintain good security practices, you must only use this new application registration to give access to the key. You must not assign additional permissions to the application registration. |

1. On the new application registration Overview page, copy the Application (client) ID and Directory (tenant) ID values. You will need to provide those values to Veeam Customer Support.
2. Go to Certificates & secrets and on the Client secrets tab, create a New client secret. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/entra/identity-platform/how-to-add-credentials?tabs=client-secret).

1. Specify a name for the client secret and set an expiration date.

The client secret is required for ongoing operations (not a one-time access). You must create a new client secret and repeat the BYOK configuration before the current client secret expires.

1. Click Add.

1. Copy the secret Value. You will need to provide this value to Veeam Customer Support.

|  |
| --- |
| IMPORTANT |
| This secret value only appears once, immediately after the creation of the client secret. You must record it, because once you leave the page, it is never displayed again. |

Configuring Key in Microsoft Azure Key Vault

After you create the new application registration, you must do the following:

1. Create a key in Microsoft Azure Key Vault, in the same Microsoft tenancy where you created the application registration.
2. Create a custom role for the key.
3. Add role assignment to the key.

Creating Key

To create a key in Microsoft Azure Key Vault, do the following:

1. Go to Key Vault in the same Microsoft tenancy where you created the new application registration.
2. On the Key Vault Overview page, copy the Vault URI value. You will need to provide this value to Veeam Customer Support.
3. Go to Objects > Keys and click Generate/Import.
4. Create a key with the following parameters:

* Name. Specify a name for the key. You will need to provide this value to Veeam Customer Support.
* Key type. Select the RSA key type.
* RSA key size. Select 2048, 3072 or 4096.

Creating Custom Role

To create a custom role for the key, do the following:

1. In Key Vault, go to Access control (IAM).
2. Click Add and select Add custom role.
3. The role must have the following DataActions permissions:

1. Microsoft.KeyVault/vaults/keys/wrap/action

Wraps a symmetric key with a Key Vault key. Note that if the Key Vault key is asymmetric, this operation can be performed by principals with read access.

1. Microsoft.KeyVault/vaults/keys/unwrap/action

Unwraps a symmetric key with a Key Vault key.

1. The Assignable scopes tab should already list the Key Vault scope. If not, the minimum assignable scope must be the key you created.

|  |
| --- |
| tip |
| If you prefer to use a built-in role, you can use the Key Vault Crypto Service Encryption User built-in role. |

For more information on creating custom roles, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/role-based-access-control/custom-roles-portal).

Adding Role Assignment

To add role assignment to the key you created, do the following:

1. In Key Vault, go to Objects > Keys and select the key you created.
2. Go to Access control (IAM).
3. Click Add and select Add role assignment.
4. On the Roles tab, select the custom role you created.
5. On the Members tab, click Select members and choose the application registration you created.

Contacting Veeam Customer Support

After you create a new application registration with a client secret, create a key in Microsoft Azure Key Vault and assign the application registration to the key, contact [Veeam Customer Support](https://my.veeam.com/my-cases) to request BYOK encryption for your Veeam Data Cloud for Microsoft 365 data.

You must provide the following information to Veeam Customer Support:

1. The Workload Tenant ID of the Veeam Data Cloud for Microsoft 365 workload tenant where you want to use BYOK encryption.

To find the workload tenant ID, in Veeam Data Cloud, on the Microsoft 365 page, click the name of the tenant you want to manage. The workload tenant ID is part of the URI.

In the following example URI, the workload tenant ID is in bold:

https://cloud.veeam.com/m365/tenant/ed590258-2795-437b-8113-07ade30d79cc/manage/dashboard

1. The Application (client) ID of the application registration you created.
2. The Directory (tenant) ID of the application registration you created.
3. The client secret Value from the application registration.
4. [Optional] The client secret expiration date.
5. The Key Vault URI of the Microsoft Azure Key Vault.
6. The Name of the key you created in Microsoft Azure Key Vault.

Veeam Customer Support will configure BYOK encryption for your Microsoft 365 workload tenant.

Ongoing Maintenance

After BYOK encryption is configured for your Veeam Data Cloud for Microsoft 365 workload tenant, consider the following:

|  |
| --- |
| important |
| In the event of key loss, you will lose the access to the encrypted data with no way to recover them. |

* You must monitor the client secret expiration date. You must create a new client secret and provide the new client secret Value to Veeam Customer Support before the current one expires. If the client secret expires, Veeam Data Cloud will lose access and operations (backup and restore) in the Veeam Data Cloud for Microsoft 365 workload tenant will fail.
* If you have a key rotation security policy, you can manage it in Microsoft Azure Key Vault. If you use the latest key version, there is no action needed in Veeam Data Cloud. For information on key rotation, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/key-vault/keys/how-to-configure-key-rotation).
* If you decide to revoke the access to Veeam Data Cloud, disable the key in Microsoft Azure Key Vault. You will still be able to browse the data in Veeam Data Cloud. Backup and restore operations in the Microsoft 365 workload tenant will fail.

Other ways to revoke the access are to delete the application registration you created, remove the role assignment from the key, delete the client secret or delete the key.

Page updated 12/4/2025
