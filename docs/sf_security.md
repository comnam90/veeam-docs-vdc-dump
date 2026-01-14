---
title: "Security"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_security.html"
last_updated: "10/31/2025"
product_version: ""
---

# Security

In this article

This section lists the fundamental security features of Veeam Data Cloud for Salesforce.

Certifications

Veeam holds numerous certifications, including ISO/IEC 27001, and continuously invests in, innovates, and enhances industry and regulatory credentials to help ensure your data is protected and secure. For more information, see [Veeam Trust Center](https://www.veeam.com/company/trust-center.html).

Data Sovereignty

Veeam Data Cloud stores backups of your Salesforce data in a region of your choice. For details on supported Microsoft Azure regions, see [Backup Storage Regions](sf_regions.md).

Redundant Storage

Veeam Data Cloud for Salesforce uses locally redundant storage (LRS) to store primary backup data in the selected Azure region, and a paired Azure region for geo-redundant backup copies to protect from the loss of an Azure availability zone or region.

Encryption

Veeam Data Cloud uses the following methods for data encryption:

* TLS version 1.2 or higher to encrypt data in transit.
* Storage service-side encryption (SSE) to encrypt data at rest in storage accounts.
* Additional mandatory file-level encryption and optional database fields encryption with system data keys.
* Data keys enciphered with either a Veeam Data Cloud master key or an Amazon Web Services Key Management Service (AWS KMS) master key to encrypt all file types and the object fields that you select to encrypt. For details, see [Configuring Encryption Settings](sf_configuring_encryption.md).

Immutability

Veeam Data Cloud for Salesforce offers service-level immutability capabilities on Salesforce backups. Once the data is backed up, it cannot be altered, tampered with, or deleted by users, including administrators or attackers.

Multi-Factor Authentication (MFA)

Veeam Data Cloud leverages Microsoft Entra ID and Veeam as identity providers (IdP). Customers are advised to configure Multi-Factor Authentication in these supported identity providers.

Service Level Agreements (SLAs)

For information on service level agreements, see the [Veeam Data Cloud Service Agreement](https://www.veeam.com/legal/veeam-data-cloud-service-agreement.html).

Page updated 10/31/2025
