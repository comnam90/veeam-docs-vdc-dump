---
title: "Using Veeam Data Cloud Vault with Veeam Backup & Replication"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/vault_vbr_integration.html"
last_updated: "3/12/2026"
product_version: ""
---

# Using Veeam Data Cloud Vault with Veeam Backup & Replication


You can use Veeam Data Cloud Vault as a target location for backups created by Veeam Backup & Replication. To do this, you must complete the following steps in Veeam Backup & Replication:

1. Add Veeam Data Cloud Vault as an object storage repository.
2. Configure a backup job targeted at this repository.

The procedure of adding Veeam Data Cloud Vault as an object storage repository differs depending on the Veeam Data Cloud Vault editions: Azure or AWS.

Veeam Data Cloud Vault Azure Editions

For the Azure editions of Veeam Data Cloud Vault, Veeam Backup & Replication offers a dedicated object storage repository type — Veeam Data Cloud Vault. During the procedure of adding a storage vault as an object storage repository, you must connect Veeam Backup & Replication with Veeam Data Cloud Vault. This procedure differs depending on the way you work with Veeam Backup & Replication.

* Veeam Backup & Replication console. This scenario is available for all supported Veeam Backup & Replication versions. In this scenario, you must use the Veeam Data Cloud Vault option to launch the New Object Storage Repository wizard, and then follow the steps of the wizard. At the Account step of the wizard, follow the procedure to connect Veeam Backup & Replication with Veeam Data Cloud Vault. For more information, see [Connecting Veeam Data Cloud Vault with Veeam Backup & Replication Using Console](vault_vbr.md).
* Veeam Backup & Replication web UI. This scenario is available starting from Veeam Backup & Replication version 13. In this scenario, you must use the New Veeam Data Cloud Vault wizard. At the Account step of the wizard, follow the procedure to connect Veeam Backup & Replication with Veeam Data Cloud Vault. For more information, see [Connecting Veeam Data Cloud Vault with Veeam Backup & Replication Using Web UI](vault_vbr_web.md).

Veeam Data Cloud Vault AWS Editions

For the AWS editions of Veeam Data Cloud Vault, to add a storage vault as an object storage repository in Veeam Backup & Replication, you must use the Amazon S3 option to launch the New Object Storage Repository wizard, and then follow the steps of the wizard. You do not need to connect Veeam Data Cloud Vault with Veeam Backup & Replication. To work with object storage repositories of this type, you must use the Veeam Backup & Replication console. For more information, see [Adding AWS Edition Storage Vaults in Veeam Backup & Replication](vault_vbr_aws.md).

