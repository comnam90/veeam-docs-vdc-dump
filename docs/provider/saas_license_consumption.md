---
title: "License Consumption"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/saas_license_consumption.html"
last_updated: "2/24/2026"
product_version: ""
---

# License Consumption


Veeam Data Cloud is licensed per user or terabyte (TB). Each licensed unit under protection consumes the license at a Point Per Unit (PPU) rate. In comparison with software licensed workloads, Veeam Data Cloud PPU is based on the SaaS Pricing curve. If you already have a software rental agreement, the number of points available to you in terms of this agreement will be inherited by the SaaS rental licensing but the SaaS pricing rate will be applied. For example, if you have a 800 Point software rental agreement, you will have 800 SaaS points at the SaaS pricing rate.

Veeam Data Cloud licensing plans are managed either as standalone subscriptions or as part of a bundle. You can hold only one active subscription for the same product at a time: whether the product is provisioned individually or as part of a bundle.

You can move from standalone to bundle licensing plan or from bundle to standalone plan, depending on your business needs and product usage. For more information, see [Switching Between Standalone and Bundle Licensing Plans](saas__switching_plans.md).

Bundle Licensing Plans

Veeam Data Cloud bundles combine multiple products into a subscription package. Microsoft 365 is designated as the primary product, and its PPU rate applies to the entire bundle. License consumption from other products is converted to the primary product consumption using predefined ratios. You can protect up to three Entra ID member users for every backed-up Microsoft 365 user.

The following table lists the available Veeam Data Cloud bundles, the options included in each plan, the licensed unit type, and the corresponding price per unit.​

Bundle Licensing Plans

| Bundle | Included Options | Licensed Unit | PPU |
| Veeam Data Cloud for Microsoft 365 Premium Plus | Veeam Data Cloud for Microsoft Entra ID | Microsoft 365 User | 6.5 |
| Veeam Data Cloud for Microsoft 365 Premium | Veeam Data Cloud for Microsoft Entra ID Veeam Data Cloud for Microsoft 365 Foundation Veeam Data Cloud for Microsoft 365 Express | Microsoft 365 User | 5.5 |
| Veeam Data Cloud for Microsoft 365 Advanced Plus | Veeam Data Cloud for Microsoft Entra ID Veeam Data Cloud for Microsoft 365 Foundation Veeam Data Cloud for Salesforce Advanced | Microsoft 365 User | 4 |
| Veeam Data Cloud for Microsoft 365 Advanced | Veeam Data Cloud for Microsoft Entra ID Veeam Data Cloud for Microsoft 365 Foundation | Microsoft 365 User | 3 |

Standalone Licensing Plans

Standalone editions are provisioned individually, allowing you to subscribe to a single product without bundling it with others.

The following table lists the available Veeam Data Cloud standalone editions, along with their licensed units and price per unit.

Standalone Licensing Plans

| Product Edition | Licensed Unit | PPU |
| Veeam Data Cloud for Microsoft 365 Foundation | Microsoft 365 User | 2.5 |
| Veeam Data Cloud for Microsoft 365 Express | Microsoft 365 User | 4 |
| Veeam Data Cloud for Microsoft Entra ID | Microsoft Entra ID User | 0.7 |
| Veeam Data Cloud for Salesforce | Salesforce User | 3 |
| Veeam Data Cloud for Microsoft Azure | 1 TB | 38 |
| Veeam Data Cloud Vault Advanced Core (Azure and AWS) | 1 TB | 24 |
| Veeam Data Cloud Vault Advanced Non-Core (Azure) | 1 TB | 38 |
| Veeam Data Cloud Vault Foundation Core (Azure and AWS) | 1 TB | 14 |
| Veeam Data Cloud Vault Foundation Non-Core (Azure and AWS) | 1 TB | 22 |

For more information on Veeam Data Cloud Vault editions, see the [Product Editions](https://helpcenter.veeam.com/docs/vdc/userguide/vault_editions.html) section of the Veeam Data Cloud User Guide.

