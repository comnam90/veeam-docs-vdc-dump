---
title: "Switching Between Standalone and Bundle Licensing Plans"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/saas__switching_plans.html"
last_updated: "2026"
product_version: ""
---

# Switching Between Standalone and Bundle Licensing Plans


Veeam Data Cloud licensing plans are managed either as standalone subscriptions or as part of a bundle. You can hold only one active subscription for the same customer and product at a time: whether the product is provisioned individually or as part of a bundle. Veeam Data Cloud bundles combine multiple products into a subscriptions package. One product is designated as the primary, and its PPU rate applies to the entire bundle. License consumption from other products is converted to the primary product consumption using predefined ratios.

You can move from standalone to bundle licensing plan or from bundle to standalone plan, depending on your business needs and product usage.

Switching from Standalone to Bundle

You can change your licensing plan from standalone to bundle. For example, if you have active standalone Veeam Data Cloud for Microsoft 365 Foundation and Veeam Data Cloud for Microsoft Entra ID plans, you can upgrade to a bundle plan such as Veeam Data Cloud for Microsoft 365 Premium Plus.

To switch your licensing plan from standalone to bundle, follow these steps:

1. Cancel the standalone subscriptions that you want to switch from. For details, see [Canceling Subscriptions](https://helpcenter.veeam.com/docs/vdc/provider/sp_subscriptions_cancel.html).
2. Wait until the subscription status changes to Terminated. For details, see [Viewing Subscriptions](https://helpcenter.veeam.com/docs/vdc/provider/sp_subscriptions_view.html).

The status of the Veeam Data Cloud tenants then changes to In retention.

1. Request a new bundle licensing plan. For details, see [Requesting Subscriptions](https://helpcenter.veeam.com/docs/vdc/provider/sp_subscriptions_request.html).

After the bundle is activated, the status of the Veeam Data Cloud tenants included in this subscription changes from In retention to Provisioned. Veeam Data Cloud automatically continues protecting the tenants.

|  |
| --- |
| Note |
| To take advantage of the bundle and start protecting the newly included workloads, you must take action in Veeam Data Cloud, depending on the bundle type:   * Enable Microsoft 365 Express backup. For details, see [Enabling Express Backup](https://helpcenter.veeam.com/docs/vdc/provider/m365_settings_enable_express_backup.html) and [Creating Express Backup Policies](https://helpcenter.veeam.com/docs/vdc/provider/m365_backup_create_express.html). * Add a Microsoft Entra ID tenant. For details, see [Adding Microsoft Entra ID Tenants](https://helpcenter.veeam.com/docs/vdc/provider/entra_id_tenant_add.html). * Add a Salesforce tenant. For details, see [Adding Salesforce Tenants](https://helpcenter.veeam.com/docs/vdc/provider/sf_tenants_add.html).   For details on available bundles, see [License Consumption](saas_license_consumption.md). |

Switching from Bundle to Standalone

You can change your licensing plan from bundle to standalone. For example, if you have an active bundle Veeam Data Cloud for Microsoft 365 Premium Plus, you can switch to a standalone plan such as Veeam Data Cloud for Microsoft 365 Foundation.

To switch your licensing plan from bundle to standalone, follow these steps:

1. Cancel the bundle subscription that you want to switch from. For details, see [Canceling Subscriptions](https://helpcenter.veeam.com/docs/vdc/provider/sp_subscriptions_cancel.html).
2. Wait until the subscription status changes to Terminated. For details, see [Viewing Subscriptions](https://helpcenter.veeam.com/docs/vdc/provider/sp_subscriptions_view.html).

The status of the Veeam Data Cloud tenants then changes to In retention.

1. Request a new standalone subscription. For details, see [Requesting Subscriptions](https://helpcenter.veeam.com/docs/vdc/provider/sp_subscriptions_request.html).

After the subscription is activated, the status of the Veeam Data Cloud tenants included in this subscription changes from In retention to Provisioned. Veeam Data Cloud automatically continues protecting the tenants.

Page updated 2026-07-20
