---
title: "Configuring Encryption Settings"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_configuring_encryption.html"
last_updated: "10/24/2025"
product_version: ""
---

# Configuring Encryption Settings

In this article

Veeam Data Cloud allows you to encrypt backed-up fields and files using data key that is enciphered with either a Veeam Data Cloud master key or an Amazon Web Services Key Management Service (AWS KMS) master key. The Veeam Data Cloud master key is configured as a default option to encrypt all file types and the object fields that you select to encrypt. For more information on how to connect to an AWS account that manages AWS KMS master key and enable it for encryption in Veeam Data Cloud for Salesforce, see [Managing AWS KMS Connections](sf_settings_kms.md).

To learn more about how to configure encryption for backed-up fields and what the encryption limitations are, see the [Edit Encryption Settings](sf_backup_policies_edit_encryption.md) step of the Editing Backup Policies section.

|  |
| --- |
| Important |
| * Shared AWS KMS keys are not supported in Veeam Data Cloud. * If an AWS KMS key is used to encrypt backed-up data, DO NOT delete this key from the AWS KMS account. Otherwise, you will not be able to decrypt the encrypted data. |

Page updated 10/24/2025
