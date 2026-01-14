---
title: "Adding AWS KMS Connections"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_settings_kms_add.html"
last_updated: "10/17/2025"
product_version: ""
---

# Adding AWS KMS Connections

In this article

To encrypt backed-up data using an AWS KMS master key, you must first add an AWS KMS connection. The added KMS connection will be available for all tenants in your Veeam Data Cloud organization that use the same Azure region.

To add a connection to the AWS Key Management service, do the following:

1. On the Salesforce page, click the name of the tenant you want to manage.
2. Select Settings.
3. Select the AWS KMS Connection tab.
4. In the Connect to Key Management Service window, specify an access key pair. Veeam Data Cloud will use it to authenticate requests to the AWS Key Management service.
5. Click Save.

[![Adding AWS KMS Connections](images/sf_settings_kms_add.png)](images/sf_settings_kms_add.png "Adding AWS KMS Connections")

Page updated 10/17/2025
