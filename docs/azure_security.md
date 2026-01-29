---
title: "Security"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_security.html"
last_updated: "12/30/2025"
product_version: ""
---

# Security


This section lists fundamental security features of Veeam Data Cloud for Microsoft Azure.

Certifications

Veeam holds numerous certifications, including ISO/IEC 27001, and is continuously investing, innovating, and adding to industry and regulatory credentials to help ensure your data is protected and secure. For more information, see [Veeam Trust Center](https://www.veeam.com/company/trust-center.html).

Data Sovereignty

Data is stored in a dedicated repository in an Azure region whose resources are protected by the backup policy.

Redundant Storage

By default, Veeam Data Cloud utilizes Zone-redundant Storage (ZRS) whenever available and replicates data across three availability zones within the same Azure region. If ZRS is not supported in a region, Veeam Data Cloud uses Local Redundant Storage (LRS) and stores three copies of data on separate disks within the same Azure region.

To learn about backup regions supported by Veeam Data Cloud for Microsoft Azure, see [Backup Storage Regions](azure_regions.md).

To learn about Azure regions where ZRS is supported, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/reliability/regions-list).

Isolated Environment

Backup data is stored in a virtually air-gapped location, hosted by Veeam in Microsoft Azure. This environment is isolated and decoupled from both Microsoft Azure and customer infrastructure. Customers also benefit from the inherent data security provided by Microsoft Azure at the storage level.

Encryption

Utilizes 256-bit encryption for all data in-transit and at-rest.

Immutability

Veeam Data Cloud for Microsoft Azure offers service-level immutability capabilities on backups of Azure resources. Once the data is backed up, it cannot be altered, tampered with, or deleted by users, including administrators or attackers.

Multi-Factor Authentication (MFA)

Utilizes Microsoft single sign-on with Multi-Factor Authentication.

Pen-tested

Regular penetration tests carried out by a 3rd party specialist provider.

Service Level Agreements (SLAs)

99.9% uptime — excluding planned outages.

