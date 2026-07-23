---
title: "Veeam Data Cloud Encryption Keys"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/encryption_keys.html"
last_updated: "2026"
product_version: ""
---

# Veeam Data Cloud Encryption Keys


Veeam Data Cloud supports BYOK (Bring Your Own Key) encryption for greater control over the encryption of your backup data. With BYOK encryption, you host and manage your own encryption keys in Microsoft Azure Key Vault. Veeam Data Cloud uses your key to encrypt backup data, but never stores it, and you can revoke access at any time.

On the Encryption Keys page, you register and manage the customer-managed keys that your workloads use for encryption. After you add and validate a key, it becomes available for selection when you configure encryption for backup storage.

This feature is available only for users with the OrganizationAdmin role assigned.

|  |
| --- |
| NOTE |
| This feature is available on request. To enable encryption key management in your Veeam Data Cloud organization, contact [Veeam Customer Support](https://my.veeam.com/my-cases).  You can use encryption keys managed on the Encryption Keys page for Veeam Data Cloud Vault only. For details, see [Managing Storage Vaults](vault_storage_vaults_edit.md). |

Before You Begin

Before you add an encryption key, you must meet the following requirements:

* You must have a paid Microsoft Azure subscription.
* You must have Microsoft Azure Key Vault that uses the Azure role-based access control (RBAC) permission model. The legacy vault access policy model is not supported.
* Your Microsoft Azure Key Vault must have soft-delete and purge protection enabled.
* You must have permissions in Microsoft Azure to create and manage Key Vault keys, to assign RBAC roles and to grant admin consent to applications in Microsoft Entra ID.
* You must prepare an RSA key in your Microsoft Azure Key Vault. For details, see [Preparing Microsoft Azure Key Vault](encryption_keys_azure.md).

Configuring BYOK Encryption

To encrypt your backup data with a customer-managed key, do the following:

1. Prepare your Microsoft Azure Key Vault. Create the Key Vault and an RSA key, then copy the Azure tenant ID and the key identifier. For details, see [Preparing Microsoft Azure Key Vault](encryption_keys_azure.md).
2. Add the encryption key in Veeam Data Cloud. Register the key with the Azure tenant ID and the key identifier. For details, see [Adding Encryption Keys](encryption_keys_add.md).
3. Validate the encryption key. Grant Veeam Data Cloud access to the key in Microsoft Azure and run the validation. For details, see [Validating Encryption Keys](encryption_keys_validate.md).
4. Select the validated key when you configure encryption for backup storage.

After you add a key, you can also view the key details and delete the key. For details, see [Viewing Encryption Key Details](encryption_key_details.md) and [Deleting Encryption Keys](encryption_keys_delete.md).

Encryption Key Statuses

The Status column shows the current status of each key:

* Pending Setup — Veeam Data Cloud cannot access the key yet. To complete the setup, validate the key.
* Ready — Veeam Data Cloud has validated the key and the key is ready to use for encryption.
* Validation Failed — the last validation attempt failed. To see the reason, view the key details.
* Active — the key is in use by one or more of your workload tenants
* Pending Deletion — You requested deletion of the key. The key can no longer be selected for encryption and Veeam Data Cloud will permanently delete it.

Ongoing Maintenance

After you configure BYOK encryption, consider the following:

|  |
| --- |
| IMPORTANT |
| If you lose the key, you will lose access to the encrypted data with no way to recover it. |

* If you have a key rotation security policy, you can manage it in Microsoft Azure Key Vault. Veeam Data Cloud always uses the latest version of the key, so no action is needed in Veeam Data Cloud. For information on key rotation, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/key-vault/keys/how-to-configure-key-rotation).
* To revoke access to Veeam Data Cloud, remove the role assignment for the key. If you revoke access, backup and restore operations that use the key will fail.

Page updated 2026-07-22
