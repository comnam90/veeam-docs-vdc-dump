---
title: "License Consumption"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/saas_license_consumption.html"
last_updated: "2/10/2026"
product_version: ""
---

# License Consumption


Veeam Data Cloud is licensed per user or terabyte (TB). Each licensed unit under protection consumes the license at a Point Per Unit (PPU) rate. In comparison with software licensed workloads, Veeam Data Cloud PPU is based on the SaaS Pricing curve. If you already have a software rental agreement, the number of points available to you in terms of this agreement will be inherited by the SaaS rental licensing but the SaaS pricing rate will be applied. For example, if you have a 800 Point software rental agreement, you will have 800 SaaS points at the SaaS pricing rate.

Veeam Data Cloud bundles combine multiple products into a subscription package. One product is designated as the primary, and its PPU rate applies to the entire bundle. License consumption from other products is converted to the primary product consumption using predefined ratios.​

| Product | Licensed Unit | PPU |
| --- | --- | --- |
| Veeam Data Cloud for Microsoft 365 (Foundation) | User | 2.5 |
| Veeam Data Cloud for Microsoft Entra ID | User | 0.7 |
| Veeam Data Cloud for Salesforce | User | 3 |
| Veeam Data Cloud for Microsoft Azure | 1 TB | 38 |
| Veeam Data Cloud Vault (Advanced Core — Azure and AWS) | 1 TB | 24 |
| Veeam Data Cloud Vault (Advanced Non-Core — Azure only) | 1 TB | 38 |
| Veeam Data Cloud Vault (Foundation Core — Azure and AWS) | 1 TB | 14 |
| Veeam Data Cloud Vault (Foundation Non-Core — Azure and AWS) | 1 TB | 22 |

For more information on Veeam Data Cloud Vault editions, see the [Product Editions](https://helpcenter.veeam.com/docs/vdc/userguide/vault_editions.html) section of the Veeam Data Cloud User Guide.

