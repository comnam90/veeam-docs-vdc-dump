---
title: "Provider-Managed Onboarding"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/sp_customers_onboard_managed.html"
last_updated: "1/21/2026"
product_version: ""
---

# Provider-Managed Onboarding


You can onboard customers that have the subscription assigned. For details on assigning subscriptions, see [Requesting Subscriptions](sp_subscriptions_request.md).

To onboard a customer, add their tenants to Veeam Data Cloud. You can add tenants to the following Veeam Data Cloud workloads:

* Veeam Data Cloud for Microsoft 365 — for details, see [Adding Microsoft 365 Tenants](m365_tenant_add.md).
* Veeam Data Cloud for Microsoft Azure — for details, see [Adding Microsoft Azure Tenants](azure_tenant_add.md).
* Veeam Data Cloud for Microsoft Entra ID — for details, see [Adding Microsoft Entra ID Tenants](entra_id_tenant_add.md).
* Veeam Data Cloud for Salesforce — for details, see [Adding Salesforce Tenants](sf_tenants_add.md).
* Veeam Data Cloud Vault — for details, see [Adding Veeam Data Cloud Vault Tenants](vault_tenants_adding.md).

After you add the first tenant to the Veeam Data Cloud organization of your customer, Veeam Data Cloud will automatically enable the Delegated management by partner option in the customer Veeam Data Cloud organization. If this option is enabled, you can manage Veeam Data Cloud tenants and users in the customer organization. Customers can also disable the Delegated management by partner option if they want to prevent their service provider from managing their organization. For details, see the [Configuring Partner Access](https://helpcenter.veeam.com/docs/vdc/userguide/sp_partner_access.html) section of the Veeam Data Cloud User Guide.

