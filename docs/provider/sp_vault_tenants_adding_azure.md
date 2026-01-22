---
title: "Adding Veeam Data Cloud Vault Tenants with Azure Edition Subscriptions"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/sp_vault_tenants_adding_azure.html"
last_updated: "1/21/2026"
product_version: ""
---

# Adding Veeam Data Cloud Vault Tenants with Azure Edition Subscriptions


To add a Veeam Data Cloud Vault tenant with an Azure edition subscription, do the following:

1. Launch the Add New Tenant wizard:

1. To open the list of Vault tenants, click Vault on the left.
2. Click Add Tenant.
3. On the Add Vault Tenant page, from the Subscription drop-down list, select your subscription or a subscription of the customer for which you want to create a tenant.

If the necessary subscription is not in the list, request a new subscription in VCSP Pulse. For details, see [Requesting Subscriptions](sp_subscriptions_request.md).

1. Select Direct Onboarding.
2. Click Next. Veeam Data Cloud will launch the Add New Tenant wizard.

[![Specifying Customer](images/sp_vault_tenants_adding_azure.webp)](images/sp_vault_tenants_adding_azure.webp "Specifying Customer")

1. In the Add New Tenant wizard, at the Tenant step, do the following:

1. In the Tenant Name field, specify a name for the new tenant. The name must be between 2 and 50 characters in length.
2. From the Subscription drop-down list, select a Veeam Data Cloud Vault subscription.
3. Click Next.

[![Adding New Tenant](images/vault_tenant_add.webp)](images/vault_tenant_add.webp "Adding New Tenant")

1. At the Provision Vault step, do the following:

1. In the Vault Name field, specify the name for the new storage vault.
2. From the Country drop-down list, select the country where you want to create the new storage vault.
3. [For the Advanced Core and Advanced Non-Core editions] From the Region drop-down list, select your preferred storage region. This helps you specify location for your data more precisely in case multiple datacenters in different regions are available within the country that you selected.
4. Click Next.

[![Providing Storage Vault for Tenant](images/vault_tenant_vault.webp)](images/vault_tenant_vault.webp "Providing Storage Vault for Tenant")

1. At the Summary step, review details of the created tenant and storage vault.

[![New Tenant Summary](images/vault_tenant_summary.webp)](images/vault_tenant_summary.webp "New Tenant Summary")

1. Click Continue to return to the Vault page.

