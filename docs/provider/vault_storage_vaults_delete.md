---
title: "Deleting Storage Vaults"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/vault_storage_vaults_delete.html"
last_updated: "1/29/2026"
product_version: ""
---

# Deleting Storage Vaults


You can permanently remove a storage vault from the backup infrastructure. To do that, you must contact [Veeam Customer Support](https://www.veeam.com/support.html#Data_Cloud_Support).

|  |
| --- |
| Important |
| Immutable data cannot be removed from a storage vault. The Veeam Backup & Replication immutability settings determine how long the data remains in the vault. |

The procedure to delete a storage vault works in the following way:

1. The user contacts [Veeam Customer Support](https://www.veeam.com/support.html#Data_Cloud_Support) with a request to delete storage account.
2. Veeam Customer Support team verifies the storage account information and asks the customer to visit the Microsoft Entra admin center to ensure that the storage account is unlinked from customer's App Registration. This prevents unintended operations before deletion.
3. Veeam Data Cloud Vault switches the storage vault status from Active to IsDeleting and the 30 day grace period begins.
4. After the 30 day grace period, Veeam Data Cloud Vault switches the storage vault status from IsDeleting to Delete.

|  |
| --- |
| Important |
| The customer can cancel the storage vault deletion within the 30 day grace period. After the grace period, the customer cannot cancel the storage vault deletion. |

1. The storage vault is deleted from Microsoft Azure and from the Veeam database.
2. The customer receives a confirmation email from the Veeam Customer Support team that the storage vault has been deleted.

