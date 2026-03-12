---
title: "Security"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/vault_security_details.html"
last_updated: "3/11/2026"
product_version: ""
---

# Security


This section describes the security details of the operation and use of Veeam Data Cloud Vault.

Access Control

Veeam Data Cloud Vault implements several access control elements. These empower you to configure access to storage vaults on an as-needed basis. You can grant users permissions while keeping the data safe with the following mechanisms:

* User Authentication. Veeam Data Cloud integrates with several authentication mechanisms, for example Microsoft Entra ID.
* Permissions Model. Veeam Data Cloud access control is managed using fine-grained Role-Based Access Control (RBAC).
* Workload Access. A vault can be accessed by supported Veeam products, for example Veeam Backup & Replication, for read and write operations using API-based interactions.

Encryption

Encrypt data to protect it from unauthorized access. Veeam Data Cloud Vault applies the following security measures:

* Data at rest is encrypted with the AES-256 standard.
* Data in transit is secured with the TLS 1.2/1.3 protocol.

An additional layer of encryption is applied by the source product, such as Veeam Backup & Replication or Veeam Kasten.

API Security

Veeam Data Cloud Vault uses the following API protection mechanisms:

* Veeam Data Cloud Vault exposes APIs for integration with supported Veeam products, such as Veeam Backup & Replication, other Veeam systems and compliance monitoring.
* Authentication with API tokens with strict permission-based access.
* IP whitelisting and multi-factor authentication (MFA) enforcement for API usage.

Logs

To monitor user activity and system interactions, Veeam Data Cloud Vault collects the following logs to support security of your data:

* User login attempts logs. Veeam Data Cloud collects logs of both successful and failed user login attempts.
* API interaction logs. For API logs, Veeam Data Cloud Vault collects the calls made, their corresponding responses, and the associated timestamps.
* Data access logs. These logs maintain information of what data was accessed, detailing the user, the time of access, and the duration of the session.
* Backup and restore operation logs.

Networking

To prevent unauthorized access to your data, you can configure firewall rules to restrict unauthorized traffic.

Certifications

Veeam Data Cloud Vault meets industry standards for ISO 27001, SOC 2, GDPR, and HIPAA.

Data Sovereignty

You can ensure data sovereignty with adjustable geolocation-based access policies.

Immutability and Ransomware Protection

Immutability ensures that backup data cannot be modified, deleted or encrypted by ransomware or accidental actions within a predefined retention period. It allows you to prevent editing or removal of data before its retention period expires. As a result, Veeam Data Cloud Vault protects backups from ransomware and insider threats, helps meet regulatory compliance (for example, SEC 17a-4(f), GDPR or HIPAA), and provides long-term retention for audits, legal hold, and business continuity.

Veeam Data Cloud Vault provides the following immutability features:

* Object Lock. This feature ensures that backups remain unchangeable for a set retention period.
* Time-Based Retention Policies. The retention policy defines specific time-frames during which data cannot be altered.
* Compliance Mode. This prevents even root-level and admin-level users from modifying data.
* Ransomware Recovery. This feature ensures a clean recovery point to restore operations in case of a cyberattack.

Veeam Data Cloud Vault applies the following Azure Blob Storage immutability settings on storage vaults:

* Version-level write once, read many (WORM) policy.
* Blob storage versioning, which maintains previous versions of objects marked with timestamps.
* Time-based retention policy.
* Legal hold policy.
* Immutable logging that prevents unauthorized modifications.

Retention Period

The default retention period is 30 days to ensure compliance with regulatory requirements. Organizations can configure extended retention based on their policies in the Veeam Backup & Replication console.

