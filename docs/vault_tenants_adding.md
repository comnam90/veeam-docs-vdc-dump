---
title: "Adding Veeam Data Cloud Vault Tenants"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/vault_tenants_adding.html"
last_updated: "12/16/2025"
product_version: ""
---

# Adding Veeam Data Cloud Vault Tenants

In this article

To add a Veeam Data Cloud Vault tenant, do the following:

1. On the Vault page, click Add Tenant.

|  |
| --- |
| Note |
| If you are a customer of a Veeam Cloud & Service Provider partner, you cannot launch the Add New Tenant wizard. Ask your service provider to add your Veeam Data Cloud Vault tenant or send you an email with an invitation link that allows you to launch the wizard. |

[![Viewing Tenants](images/vault_dashboard.png)](images/vault_dashboard.png "Viewing Tenants")

1. In the Add New Tenant wizard, at the Tenant step, do the following:

1. In the Tenant Name field, specify a name for the new tenant.
2. From the Subscription drop-down list, select a Veeam Data Cloud Vault subscription.
3. Click Next.

[![Adding New Tenant](images/vault_tenant_add.png)](images/vault_tenant_add.png "Adding New Tenant")

1. At the Provision Vault step, do the following:

1. In the Vault Name field, specify the name of the new storage vault.
2. From the Country drop-down list, select the country where you want to create the new storage vault.
3. [For the Advanced Core and Advanced Non-Core editions] From the Region drop-down list, select your preferred storage region. This helps you specify location for your data more precisely in case multiple datacenters in different regions are available within the country that you selected.
4. Click Next.

[![Providing Storage Vault for Tenant](images/vault_tenant_vault.png)](images/vault_tenant_vault.png "Providing Storage Vault for Tenant")

1. At the Summary step, review details of the created tenant and click Finish. Veeam Data Cloud Vault will create the tenant and storage vault.

[![New Tenant Summary](images/vault_tenant_summary.png)](images/vault_tenant_summary.png "New Tenant Summary")

1. [For AWS editions] At the Credentials step of the wizard, Veeam Data Cloud Vault will display the access key and secret key required to access the storage vault. You can use these keys to add Veeam Data Cloud Vault as an object storage repository in Veeam Backup & Replication.

Copy the access key and storage key and save them for future use. Once you finish working with the Add New Tenant wizard, you will not be able to view and copy the secret key, and will need to regenerate it, if necessary.

1. To view the keys, click Reveal next to the values in the Access Key and Secret Key fields.
2. To copy the keys, click the copy icon next to the values in the Access Key and Secret Key fields.

[![New Tenant Credentials](images/vault_tenant_credentials.png)](images/vault_tenant_credentials.png "New Tenant Credentials")

1. Click Continue to return to the Vault page.

Page updated 12/16/2025
