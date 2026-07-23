---
title: "Preparing Microsoft Azure Key Vault"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/encryption_keys_azure.html"
last_updated: "2026"
product_version: ""
---

# Preparing Microsoft Azure Key Vault


Before you add an encryption key in Veeam Data Cloud, you must prepare a Microsoft Azure Key Vault with an RSA key in it. The key vault must use the Azure role-based access control (RBAC) permission mode and must have the soft-delete and purge protection options enabled. After you prepare the key vault, you will have two values that you provide to Veeam Data Cloud when you add the encryption key: the Azure tenant ID and the key identifier.

|  |
| --- |
| NOTE |
| Do not assign any role to Veeam Data Cloud at this stage. You grant Veeam Data Cloud access to the key later, when you validate the key. For details, see [Validating Encryption Keys](encryption_keys_validate.md).  To strenghten security, restrict the network access of the key vault. If you restrict access, enable Allow trusted Microsoft services to bypass this firewall and add Veeam Data Cloud IP ranges to the key vault firewall allowlist; otherwise, key validation and backup and restore operations will fail. For the required IP ranges, contact [Veeam Customer Support](https://my.veeam.com/my-cases). |

Creating a Key Vault

If you already have a Microsoft Azure Key Vault that uses the Azure role-based access control (RBAC) permission model, you can use it and skip this section.

To create a key vault, do the following:

1. Sign in to the Microsoft Azure portal as a user who can create resources.
2. Search for Key vaults and open the service.
3. Click Create.
4. On the Basics tab, specify the subscription, resource group, key vault name and region. The key vault name becomes part of the key identifier.
5. Make sure that Soft-delete is enabled.
6. Select Enable purge protection.
7. On the Access configuration tab, in Permission model, select Azure role-based access control.
8. Proceed through the remaining tabs, then on the Review + create tab, click Create.

|  |
| --- |
| IMPORTANT |
| Veeam Data Cloud supports the Azure role-based access control permission model only. The legacy vault access policy model is not supported. If your existing vault uses the vault access policy model, migrate it to Azure RBAC first. For details, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/key-vault/general/rbac-migration). |

For more information on how to create a key vault, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/key-vault/general/quick-create-portal).

Creating an Encryption Key

After you create the key vault, create an RSA key in it.

|  |
| --- |
| NOTE |
| To create a key in a vault that uses the Azure RBAC permission model, you must have a key vault data-plane role, such as Key Vault Administrator or Key Vault Crypto Officer. The subscription Contributor role is not sufficient. |

To create a key, do the following:

1. In the key vault, under Objects, click Keys.
2. Click Generate/Import.
3. In Options, select Generate.
4. Specify a name for the key. The key name becomes part of the key identifier.
5. In Key type, select RSA.
6. In RSA key size, select 2048, 3072 or 4096.
7. Make sure that Enabled is set to Yes, then click Create.

For more information on how to create a key, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/key-vault/keys/quick-create-portal).

Copying the Key Identifier

After you create the key, copy the key identifier. You provide this value to Veeam Data Cloud when you add the key.

1. In the key vault, under Objects, click Keys, then click the key you created.
2. Click the current version of the key.
3. Copy the Key Identifier value.

The key identifier has the following format: https://<vault-name>.vault.azure.net/keys/<key-name>/<version>.

|  |
| --- |
| NOTE |
| Veeam Data Cloud always uses the latest version of the key. Provide the key identifier to Veeam Data Cloud exactly as Microsoft Azure shows it. You do not need to edit the value. |

Copying the Azure Tenant ID

You also provide your Azure tenant ID to Veeam Data Cloud when you add the key.

1. In the Microsoft Azure portal, search for Microsoft Entra ID and open the service.
2. On the Overview page, copy the Tenant ID value.

After you copy the Azure tenant ID and the key identifier, you can add the encryption key in Veeam Data Cloud. For details, see [Adding Encryption Keys](encryption_keys_add.md).

Page updated 2026-07-21
