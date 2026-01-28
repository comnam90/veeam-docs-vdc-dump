---
title: "Viewing Tenants"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/vault_tenants_view.html"
last_updated: "1/27/2026"
product_version: ""
---

# Viewing Tenants


On the Vault page, you can view all added Veeam Data Cloud Vault tenants and information about the Veeam Data Cloud Vault subscription. You can also add a new Vault tenant. For details on adding tenants, see [Adding Veeam Data Cloud Vault Tenants](vault_tenants_adding.md).

To view the Vault page, select Vault on the left.

Viewing Tenants

In the upper section, the Active Subscriptions field shows the number of subscriptions your customers has assigned for this workload.

In the tenant list, Veeam Data Cloud displays the following properties for each tenant:

* The Tenant Name column displays the name you assigned to the tenant.

The subscription edition that is used for the tenant is listed below the tenant name. To learn more, see [Veeam Data Cloud Vault Product Editions](vault_editions.md).

* The Customer column displays the customer organization where the tenant is created.
* The Storage Consumed column displays the amount of storage used by the tenant.
* The Vaults column displays vault storages available to the tenant.
* The Status column displays current status of the tenant account.
* The Region column displays locations selected while adding a tenant.

[![Viewing Vault Page](images/sp_vault_tenants_view.webp)](images/sp_vault_tenants_view.webp "Viewing Vault Page")

Working with Tenant List

On the Vault page, you can perform the following actions with the list of tenants:

* Search

Use the Search tenants field to search with tenant names.

* Filter

Click Filters to display only tenants with specific tenant status. Use check boxes to select the statuses.

[![Filtering Tenants by Subscription Edition](images/sp_vault_tenants_view_filter.webp)](images/sp_vault_tenants_view_filter.webp "Filtering Tenants by Subscription Edition")

* Refresh

Click Refresh to update the list of tenants and displayed details. The refresh action does not cancel the set filters.

* Sort

Use arrows next to the column name to sort the list of your tenants alphabetically by their names, subscriptions and storage regions.

