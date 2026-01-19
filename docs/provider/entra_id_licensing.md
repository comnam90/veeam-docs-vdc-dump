---
title: "Licensing"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/entra_id_licensing.html"
last_updated: "1/19/2026"
product_version: ""
---

# Licensing


Licensing for Veeam Data Cloud for Microsoft Entra ID is based on the user accounts you back up. Each enabled Entra ID member user is counted towards your purchased license or free allowance. Groups, roles and other Microsoft Entra ID objects do not consume the license or allowance, but Veeam Data Cloud protects them too.

|  |
| --- |
| note |
| In Entra ID, the type of the user account is specified by the value of the userType attribute (Member or Guest). Microsoft Entra ID users who were created before the introduction of the userType attribute on August 31, 2014, have this value unset (null). Veeam Data Cloud licenses and processes these user accounts the same way it licenses and processes Entra ID member users. |

Licensing Plans

To protect your Entra ID data, you can choose one of the following licensing plans depending on the Veeam Data Cloud subscriptions that you want to use. The Entra ID Standalone plan allows you to protect your Entra ID data only. If you also want to protect your Microsoft 365 data, you can choose one of the bundle plans.

Note that subscriptions with the Express or Premium Veeam Data Cloud for Microsoft 365 plan are not available for service providers and their customers at the moment. For more information on available products, see [License Consumption](saas_license_consumption.md).

| Licensing Plan | Included Options | License Unit |
| --- | --- | --- |
| Veeam Data Cloud for Microsoft Entra ID Standalone | Veeam Data Cloud for Microsoft Entra ID | Entra ID user |
| Veeam Data Cloud for Microsoft 365 Advanced | Veeam Data Cloud for Microsoft Entra ID  Veeam Data Cloud for Microsoft 365 Flex backup | Microsoft 365 user |

License Expiration

If your subscription expires and you do not renew it, Veeam Data Cloud will suspend your backup policy for 30 days. During this period, your existing Entra ID backups are still available, and you can use Veeam Data Cloud to restore your Entra ID data. After 30 days, Veeam Data Cloud will permanently delete your Entra ID tenant and all related data.

