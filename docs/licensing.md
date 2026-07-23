---
title: "Licensing"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/licensing.html"
last_updated: "2026"
product_version: ""
---

# Licensing


To protect your data with Veeam Data Cloud, you need to purchase a subscription-based license. Veeam Data Cloud is licensed per user or terabyte (TB). Each licensed unit under protection consumes a license.

The licensing model depends on the workload:

* User-based licensing — one license per user account. Applies to Microsoft 365, Microsoft Entra ID and Salesforce.
* Capacity-based licensing — one license per terabyte of compressed backup data (Back-End Terabyte, BETB). Applies to Microsoft Azure, Amazon Web Services and Vault.

For details on licensing for a specific Veeam Data Cloud workload, see the Licensing section of the workload:

* [Microsoft 365](m365_licensing.md)
* [Amazon Web Services](aws_licensing.md)
* [Microsoft Azure](azure_licensing.md)
* [Microsoft Entra ID](entra_id_licensing.md)
* [Salesforce](sf_licensing.md)
* [Vault](vault_licensing.md)

License Expiration

If your licenses expire and you do not renew them, Veeam Data Cloud will handle your backed-up data according to the Veeam Data Cloud Service Agreement. For more information, see [this Veeam article](https://www.veeam.com/legal/veeam-data-cloud-service-agreement.html).

Veeam Data Cloud Trial

Veeam Data Cloud offers a 14-day free trial for Microsoft Entra ID and Salesforce workloads. The trial provides full feature access so you can evaluate Veeam Data Cloud capabilities before you purchase a subscription. Each workload trial runs independently — starting a trial for one workload does not affect the trial period for other workloads. You cannot start a trial for a workload if the workload already has an active or completed trial in your Veeam Data Cloud organization.

To start a trial, you must have the OrganizationAdmin role assigned.

Starting Trial

To start a new trial, do the following:

1. Log in to the Veeam Data Cloud portal. For details, see [Accessing Veeam Data Cloud](accessing_vdc.md).
2. On the Overview page, click Start Trial on the workload for which you want start a trial.
3. In the confirmation window, review the trial conditions and click Start Trial. Veeam Data Cloud will launch the Add Tenant wizard for the selected workload.
4. Complete the wizard to add the tenant and start the trial.

Trial Expiration

The trial period starts when you add your tenant to Veeam Data Cloud. After the 14-day trial expires, a 30-day grace period begins. During the grace period, you can restore existing backup data, but you cannot create new backups. After the grace period ends, Veeam Data Cloud permanently deletes all backup data.

To avoid data loss, convert to a paid subscription before the grace period ends. Converting requires no reconfiguration and causes no data loss.

Page updated 2026-07-22
