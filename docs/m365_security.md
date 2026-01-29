---
title: "Security"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/m365_security.html"
last_updated: "12/16/2025"
product_version: ""
---

# Security


This section lists fundamental security features of Veeam Data Cloud for Microsoft 365.

Certifications

Veeam holds numerous certifications, including ISO/IEC 27001, and is continuously investing, innovating, and adding to industry and regulatory credentials to help ensure your data is protected and secure. For more information, see [Veeam Trust Center](https://www.veeam.com/company/trust-center.html).

Data Sovereignty

* Veeam Data Cloud for Microsoft 365 Flex backup data is stored within one or more dedicated storage accounts in the regions of your choice.
* Veeam Data Cloud for Microsoft 365 Express backup data is stored within the region used within your Microsoft 365 environment.

Redundant Storage

* Veeam Data Cloud for Microsoft 365 Flex uses Local Redundant Storage (LRS) by default, where 3 copies of customer data are stored on 3 separate disks within the primary Azure region.
* Veeam Data Cloud for Microsoft 365 Express uses the native backup storage provided by the Microsoft 365 Backup Storage APIs.

Isolated Environment

* Veeam Data Cloud for Microsoft 365 Flex backup data is stored in a virtually air-gapped location, hosted by Veeam in Microsoft Azure. This environment is isolated and decoupled from both Microsoft 365 and customer infrastructure. Customers also benefit from the inherent data security provided by Microsoft Azure at the storage level.
* Veeam Data Cloud for Microsoft 365 Express backup data is stored within your Microsoft 365 tenant as an isolated copy of data. The data is only accessible through the Microsoft 365 Backup Storage APIs.

Encryption

Utilizes 256-bit encryption for all data in-transit and at-rest.

Immutability

Offers service-level immutability capabilities on both Veeam Data Cloud for Microsoft 365 Flex and Express backups. Once the data is backed up, it cannot be altered, tampered with, or deleted by users, including administrators or attackers.

Multi-Factor Authentication (MFA)

Utilizes Microsoft single sign-on with Multi-Factor Authentication.

Retention Period

* Veeam Data Cloud for Microsoft 365 Flex retention is set to 1 year by default, and can be customized to offer up to an unlimited time period. Restore points are generated daily by default.
* Veeam Data Cloud for Microsoft 365 Express retention is fixed at 52 weeks. Restore points are generated based on the protected Microsoft 365 service.

* For Microsoft Exchange Online, the restore points are created every 10 minutes. The retention period for these restore points is 52 weeks.
* For Microsoft OneDrive for Business and Microsoft SharePoint Online, the restore points are created every 10 minutes. The retention period for these restore points is 2 weeks. In addition, weekly restore points are created once a week. The retention period for these restore points is 50 weeks.

Pen-Tested

Regular penetration tests carried out by a 3rd-party specialist provider.

Service Level Agreements (SLAs)

Veeam Data Cloud for Microsoft 365 Flex offers a 99.9% uptime SLA, excluding planned outages. For details, see the [Veeam Data Cloud Service Agreement](https://www.veeam.com/legal/veeam-data-cloud-service-agreement.html).

