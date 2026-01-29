---
title: "Considerations and Limitations"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/entra_id_limitations.html"
last_updated: "9/25/2025"
product_version: ""
---

# Considerations and Limitations


When you plan to protect your Microsoft Entra ID tenant with Veeam Data Cloud, keep in mind the following limitations and considerations.

Tenant Backup and Restore

* Veeam Data Cloud does not support backup of Microsoft Entra ID tenants in the Government and China regions.
* Veeam Data Cloud does not support the Azure Active Directory B2C and Microsoft Entra External ID tenants.
* Veeam Data Cloud backs up your Entra ID tenant automatically every day. You cannot start a backup session manually.
* The built-in Entra ID roles are read only and cannot be restored.
* The Entra ID distribution groups and mail-enabled security groups cannot be restored.

Log Backup and Restore

You cannot back up sign-in logs with Microsoft Entra ID free license. With this license, you can back up only audit logs.

