---
title: "Adding Storage Vaults"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/vault_storage_vaults_add.html"
last_updated: "12/18/2025"
product_version: ""
---

# Adding Storage Vaults


The first storage vault is created as part of onboarding a new Vault tenant. You can add new storage vaults later, for example, if you need to increase storage size or want to store data in another region.

You can use your Veeam Data Cloud Vault to provide storage vaults to your fully managed customers. In this case, create a dedicated storage vault for each customer.

To add another storage vault, do the following:

1. On the Vault page, find the necessary tenant in the list of tenants. Click the button with three dots at the end of the row, then click Manage.
2. In the left menu, click Storage Vaults.
3. On the Storage Vaults page, click Add Vault.
4. In the Add Vault wizard, at the Vault Details step, do the following:

1. In the Vault Name field, specify the name of the new storage vault. The name must be between 3 and 50 characters in length.
2. From the Country drop-down list, select the country where you want to create the new storage vault.
3. [For the Advanced Core and Advanced Non-Core editions] From the Region drop-down list, select your preferred storage region. This helps you specify a location for your data more precisely in case multiple data centers in different regions are available within the country you selected.
4. Do either of the following:

* [For Azure editions] Click Finish. Veeam Data Cloud Vault will create the storage vault.
* [For AWS editions] Click Next. Veeam Data Cloud Vault will create the storage vault and display the storage vault credentials at the next step of the wizard.

[![Adding Another Storage Vault](images/vault_storage_vaults_add.webp)](images/vault_storage_vaults_add.webp "Adding Another Storage Vault")

1. [For AWS editions] At the Credentials step of the wizard, Veeam Data Cloud Vault will display the access key and secret key required to access the storage vault. You can use these keys to add Veeam Data Cloud Vault as an object storage repository in Veeam Backup & Replication.

Copy the access key and storage key and save them for future use. Once you finish working with the Add Vault wizard, you will not be able to view and copy the secret key, and will need to regenerate it, if necessary. For more information, see [Managing Storage Vaults](vault_storage_vaults_edit.md).

1. To view the keys, click Reveal next to the values in the Access Key and Secret Key fields.
2. To copy the keys, click the copy icon next to the values in the Access Key and Secret Key fields.

Click Continue to return to the Vault page.

[![New Storage Vault Credentials](images/vault_storage_vaults_add_credentials.webp)](images/vault_storage_vaults_add_credentials.webp "New Storage Vault Credentials")

