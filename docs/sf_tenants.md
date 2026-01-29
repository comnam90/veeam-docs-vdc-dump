---
title: "Managing Salesforce Tenants"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_tenants.html"
last_updated: "10/17/2025"
product_version: ""
---

# Managing Salesforce Tenants


To start protecting your Salesforce data, you must add a Salesforce tenant (production, sandbox or a developer organization) to Veeam Data Cloud. During the process, you connect Veeam Data Cloud to a Salesforce tenant (organization) and the basic tenant details and the OAuth authentication tokens of the Connected App are saved in Veeam Data Cloud. These features are available only for users assigned the Salesforce:Administrator and Salesforce:BackupOperator roles.

|  |
| --- |
| Note |
| Veeam Data Cloud does not have access to Salesforce user credentials. To authorize and access Salesforce data, Veeam Data Cloud uses OAuth tokens of the Connected App created during the initial configuration. |

In This Section

* [Adding Salesforce Tenants](sf_tenants_add.md)
* [Viewing Salesforce Tenants](sf_tenant_view.md)
* [Removing Salesforce Tenants](sf_tenants_remove.md)

