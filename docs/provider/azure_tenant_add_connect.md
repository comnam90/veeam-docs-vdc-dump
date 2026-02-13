---
title: "Step 2. Connect to Azure Tenant"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/azure_tenant_add_connect.html"
last_updated: "2/9/2026"
product_version: ""
---

# Step 2. Connect to Azure Tenant


At the Connection step of the wizard, log in to your Microsoft account to authorize Veeam Data Cloud to access your Azure tenant.

After authorization, Veeam Data Cloud will create a service principal in your Azure tenant. This service principal allows Veeam Data Cloud to back up and restore your Azure resources.

To authorize the access, click Authorize and log in to your Microsoft account. Make sure to log in with a user account that has the Application Administrator role. For more information about this role, see [Microsoft documentation](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference#application-administrator).

[![Step 2. Connect to Azure Tenant](images/azure_tenant_add_connect.webp)](images/azure_tenant_add_connect.webp)

