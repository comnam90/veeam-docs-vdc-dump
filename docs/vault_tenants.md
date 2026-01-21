---
title: "Managing Veeam Data Cloud Vault Tenants"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/vault_tenants.html"
last_updated: "1/12/2026"
product_version: ""
---

# Managing Veeam Data Cloud Vault Tenants


To start protecting your data with Veeam Data Cloud Vault, you must add a Vault tenant to Veeam Data Cloud. Vault tenants provide a mechanism to organize storage vaults, associate them with subscriptions, and control management access.

In Veeam Data Cloud Vault, you can create multiple tenants. Each tenant is linked to only one subscription, but a single subscription can be assigned to multiple tenants. Tenants help you organize storage vaults in the following ways:

* Each tenant can manage its storage vaults under its assigned subscription, this enables you to separate and organize data storages.
* You can control which subscription is associated with each tenant.
* By adding more tenants, you can customize user access so that each user can only access the necessary data.

|  |
| --- |
| Note |
| Note that in most common scenarios, a single tenant is sufficient to manage all required storage vaults and user roles within a subscription. Only create additional tenants if you need to further segment management access or organize resources for specific use cases. For more information, see [Roles](users_roles.md#vault_user_roles). |

You can manage Veeam Data Cloud Vault tenants in the following ways:

* [Add a tenant](vault_tenants_adding.md)
* [View tenant details](vault_tenants_view.md)
* [Access the tenant dashboard](vault_tenants_dashboard.md)

