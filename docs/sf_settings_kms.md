---
title: "Managing AWS KMS Connections"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_settings_kms.html"
last_updated: "10/23/2025"
product_version: ""
---

# Managing AWS KMS Connections


To encrypt backed-up data using an AWS KMS master key, you must first connect to an AWS account that manages this key. To learn how to do that, follow the instructions provided in section [Adding AWS KMS Connections](sf_settings_kms_add.md). After you add a connection to AWS KMS, you can use the AWS master key to encrypt the backed-up data as described in the [Edit Encryption Settings](sf_backup_policies_edit_encryption.md) step of the Editing Backup Policies section.

The KMS connection that you add to Veeam Data Cloud will be available for all tenants in your Veeam Data Cloud organization that use the same Azure region.

Before you connect to an AWS account, check the following prerequisites:

* Make sure that the IAM user that will be used to perform data encryption has all the [required permissions](sf_permissions.md).
* Make sure that you have created the AWS KMS master key in the AWS account. For more information, see [AWS Documentation](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html).
* Make sure that you have created an access key ID and a secret access key that will be used to authenticate requests to the AWS account. Keep in mind that you can see and copy this ID and key only when creating an access key pair. For more information, see [AWS Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html).

In This Section

* [Adding AWS KMS Connections](sf_settings_kms_add.md)
* [Removing AWS KMS Connections](sf_settings_kms_remove.md)

