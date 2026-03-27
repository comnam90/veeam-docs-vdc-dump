---
title: "Considerations and Limitations"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/vault_considerations.html"
last_updated: "3/26/2026"
product_version: ""
---

# Considerations and Limitations


This section lists considerations and known limitations for Veeam Data Cloud Vault.

General

Consider the following:

* Veeam Data Cloud Vault is available in several editions and backup storage regions. For more information, see [Veeam Data Cloud Vault Editions Comparison](https://www.veeam.com/veeam_data_cloud_vault_comparison_ds.pdf).

|  |
| --- |
| Note |
| Veeam Data Cloud Vault is not available in Azure Government regions. |

* You can only obtain one subscription for each edition. The maximum number of Veeam Data Cloud Vault subscriptions is 7 subscriptions for an organization.
* There is no limit to the number of vaults per Veeam Data Cloud Vault subscription.
* Veeam Data Cloud Vault only integrates with Veeam Backup & Replication, Veeam Backup for Microsoft Azure and Veeam Kasten. You are not permitted to use it with other products to upload data.

Consider the following:

* Veeam Backup & Replication supports integration with all Veeam Data Cloud Vault editions. For information on considerations for Veeam Backup & Replication integration, see [Integration with Veeam Backup & Replication](#vbr).
* Veeam Backup for Microsoft Azure and Veeam Kasten support integration with Azure Veeam Data Cloud Vault editions only.

* Azure editions of Veeam Data Cloud Vault are backed by the Cool tier of Azure Blob storage.
* You cannot seed data from the Azure Data Box device to Veeam Data Cloud Vault.
* You can use Veeam Data Cloud Vault in environments that use Azure ExpressRoute with private peering. For more information, see [this Veeam KB article](https://www.veeam.com/kb4745).

Integration with Veeam Backup & Replication

Consider the following:

* Before you start using Veeam Data Cloud Vault as an object storage repository in Veeam Backup & Replication, get familiar with considerations and limitations. For more information, see the [Veeam Data Cloud Vault Considerations and Limitations](https://helpcenter.veeam.com/docs/vbr/userguide/data_cloud_limitations.html?ver=13) section in the Veeam Backup & Replication User Guide.
* One Veeam Backup & Replication server can be connected to multiple storage vaults. This may be useful if you want to create backups in different locations.
* Multiple Veeam Backup & Replication servers can be connected to the same storage vault. In this scenario, you can add the same storage vault as an object storage repository on multiple backup servers. Each backup server will create backups in a separate folder within this object storage.

* You can use a storage vault as an object storage repository or Veeam Cloud Connect repository.

* Veeam Backup & Replication traffic throttling rules apply to Veeam Data Cloud Vault scenarios.

|  |
| --- |
| Note |
| [For Veeam Cloud Connect Backup] You can use Veeam Data Cloud Vault storage as a cloud repository only if the Veeam Data Cloud Vault object storage repository is added on the service provider side in the connection through a gateway server mode. In this scenario, traffic throttling rules are defined per tenant in the properties of the tenant account. To learn more, see the [Network Traffic Throttling](https://helpcenter.veeam.com/docs/vbr/cloud/data_encryption_and_throttling.html?ver=13#network-traffic-throttling) section in the Veeam Cloud Connect Guide. |

* Ports 443 and 80 must be opened to ensure proper communication with Veeam Backup & Replication. For more information, see the [Ports](https://helpcenter.veeam.com/docs/vbr/userguide/used_ports.html?ver=13#veeam-data-cloud-vault) section in the Veeam Backup & Replication User Guide.
* It is not possible to connect Veeam Backup & Replication 12.x running on Windows Server 2012 R2 with Veeam Data Cloud Vault because this OS does not support WebView2, which is required for the backup server authorization form.

To overcome this limitation, either upgrade the OS on the backup server or install the Veeam Backup & Replication console on a separate machine with a newer OS and connect to the backup server from that backup console. You will be able to complete the backup server authorization procedure.

* For the Azure editions of Veeam Data Cloud Vault, to connect Veeam Data Cloud Vault with Veeam Backup & Replication, the Veeam Data Cloud Vault subscription and the Veeam backup server must belong to the same organization on the Veeam My Account portal. Consider this in the scenario where the account under which you log in to Veeam My Account belongs to multiple organizations.

This requirement does not apply to Veeam Backup & Replication build 13.0.1.2067 and later. Starting from this product version, Veeam Backup & Replication and Veeam Data Cloud Vault are connected directly, without using the Veeam My Account portal.

* To use AWS editions of Veeam Data Cloud Vault with Veeam Backup & Replication, you must enable immutability for the object storage repository and data encryption for the backup job targeted at this repository in Veeam Backup & Replication.

* To enable immutability for the object storage repository, select the Make backups immutable check box at the Bucket step of the New Object Storage Repository wizard and specify the necessary immutability period. For more information, see the [Specify Object Storage Settings](https://helpcenter.veeam.com/docs/vbr/userguide/amazon_storage_details.html?ver=13) section in the Veeam Backup & Replication User Guide.
* To enable data encryption for the backup job, select the Enable backup file encryption check box at the Storage step of the New Backup Job wizard and specify the data encryption settings. For more information, see the [Storage Settings](https://helpcenter.veeam.com/docs/vbr/userguide/backup_job_advanced_storage_vm.html?ver=13) section in the Veeam Backup & Replication User Guide.

* For the AWS editions of Veeam Data Cloud Vault, you must select Infrequent Access as the Amazon S3 storage class when adding a storage vault as an object storage repository in Veeam Backup & Replication. For details, see the [Specifying Amazon S3 Storage Classes](https://helpcenter.veeam.com/docs/vbr/userguide/amazon_storage_details.html?ver=13#specifying-amazon-s3-storage-classes) section in the Veeam Backup & Replication User Guide.

Integration with Veeam Backup for Microsoft Azure

You cannot connect a storage vault as an external repository in Veeam Backup & Replication to copy backups created by Veeam Backup for Microsoft Azure or to restore data from such backups. To create backup copies of Veeam Backup for Microsoft Azure backups or to restore data from them in Veeam Data Cloud Vault, you must add the storage vault as an Azure-type object storage repository using your Microsoft Azure storage account credentials. To be able to do that, perform the following steps:

1. Configure Veeam Backup for Microsoft Azure to work with Veeam Data Cloud Vault. For more information, see the [Adding Storage Vaults Using Web UI](https://helpcenter.veeam.com/docs/vbazure/guide/repository_vdc_add_ui.html?ver=8.1https://helpcenter.veeam.com/docs/vbazure/guide/repository_vdc_add_ui.html?ver=8.1) section in the Veeam Backup for Microsoft Azure User Guide.
2. Configure Veeam Backup for Microsoft Azure backup jobs with a Veeam Data Cloud storage vault used as the target location.
3. Contact [Veeam Customer Support](https://www.veeam.com/support.html#Data_Cloud_Support) to enable shared keys on the storage vault.
4. Use shared keys to add the storage vault. For the storage vault to work as an external repository in Veeam Backup & Replication, use a repository of the Azure type.
5. Configure backup copy or restore jobs.

To learn more about restore limitations for backups in Veeam Data Cloud storage vaults, see the [Considerations and Limitations: Restore](https://helpcenter.veeam.com/docs/vbazure/guide/limitations.html?ver=8.1#restore) section in the Veeam Backup for Microsoft Azure User Guide.

