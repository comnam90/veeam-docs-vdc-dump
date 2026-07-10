---
title: "Security"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/entra_id_security.html"
last_updated: "7/10/2026"
product_version: ""
---

# Security


This section lists the fundamental security features of Veeam Data Cloud for Microsoft Entra ID.

Certifications

Veeam holds numerous certifications, including ISO/IEC 27001, and continuously invests in, innovates, and enhances industry and regulatory credentials to help ensure your data is protected and secure. For more information, see [Veeam Trust Center](https://www.veeam.com/company/trust-center.html).

Data Sovereignty

Veeam Data Cloud stores backups of your Entra ID data in a dedicated database in the region of your choice. For details on supported Microsoft Azure regions, see [Backup Storage Regions](entra_id_regions.md).

Redundant Storage

Veeam Data Cloud for Microsoft Entra ID uses Azure geo-redundant storage to protect backups from planned and unplanned events.

Encryption

Veeam Data Cloud uses the following methods for data encryption:

* TLS version 1.2 or higher to encrypt data in transit.
* Storage service-side encryption (SSE) to encrypt data at rest in storage accounts.
* Service-managed keys to automatically and seamlessly encrypt data at rest in databases.

Immutability

Veeam Data Cloud for Microsoft Entra ID offers service-level immutability capabilities on Entra ID backups. Once the data is backed up, it cannot be altered, tampered with, or deleted by users, including administrators or attackers.

Multi-Factor Authentication (MFA)

Veeam Data Cloud leverages Microsoft Entra ID and Veeam My Account as identity providers (IdP). Customers are advised to configure multi-factor authentication in these supported identity providers. For details, see [Accessing Veeam Data Cloud](accessing_vdc.md#mfa).

Service Level Agreements (SLAs)

Veeam Data Cloud for Microsoft Entra ID offers a 99.9% uptime SLA, excluding planned outages. For details, see the [Veeam Data Cloud Service Agreement](https://www.veeam.com/legal/veeam-data-cloud-service-agreement.html).

