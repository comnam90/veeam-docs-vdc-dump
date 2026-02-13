---
title: "Editing Azure Service Accounts"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/azure_settings_accounts_service_edit.html"
last_updated: "2/12/2026"
product_version: ""
---

# Editing Azure Service Accounts


You can allow Veeam Data Cloud for Microsoft Azure to access additional subscriptions in your Azure tenant to protect their resources. To do this, perform the following steps:

1. On the Azure Service Accounts tab, select a service account and click Edit.

Veeam Data Cloud for Microsoft Azure will launch the Edit Account wizard.

[![Editing Azure Service Accounts](images/azure_settings_accounts_service_view_edit.webp)](images/azure_settings_accounts_service_view_edit.webp)

1. At the Connection step of the wizard, you must allow Veeam Data Cloud for Microsoft Azure to access your Azure tenant. To do this, click Authorize and log in to your Microsoft account.

Make sure to use the credentials of a user account that has the Application Administrator role. For more information about this role, see [Microsoft documentation](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference#application-administrator).

|  |
| --- |
| Important |
| To add a subscription to the Veeam Data Cloud protection scope, the account you use for authorization also must have the following permissions at the subscription level:   * Microsoft.Authorization/roleDefinitions/write * Microsoft.Authorization/roleAssignments/write * Microsoft.Resources/subscriptions/resourceGroups/read   For more information about permissions in Azure, see [Microsoft documentation](https://learn.microsoft.com/en-us/azure/role-based-access-control/resource-provider-operations). |

[![Editing Azure Service Accounts](images/azure_settings_accounts_service_view_edit_auth.webp)](images/azure_settings_accounts_service_view_edit_auth.webp)

1. At the Scope step of the wizard, to add a subscription whose resources Veeam Data Cloud for Microsoft Azure will protect, do the following:

1. In the Subscriptions to protect field, click the subscriptions link.
2. In the Subscriptions window, select the subscription that you would like to add to the protection scope, and click Apply.

[![Editing Azure Service Accounts](images/azure_settings_accounts_service_view_edit_sub.webp)](images/azure_settings_accounts_service_view_edit_sub.webp)

1. At the Permission Check step of the wizard, ensure that Veeam Data Cloud for Microsoft Azure has all necessary permissions to protect the subscription resources. To do this, perform the following steps:

1. Select the subscription for which you want to grant the missing permissions to Veeam Data Cloud, and click Grant.

[![Editing Azure Service Accounts](images/azure_settings_accounts_service_view_edit_grant.webp)](images/azure_settings_accounts_service_view_edit_grant.webp)

1. In the Grant Azure Subscription Permissions window, review the required permissions and click Apply.

[![Editing Azure Service Accounts](images/azure_settings_accounts_service_view_edit_apply.webp)](images/azure_settings_accounts_service_view_edit_apply.webp)

1. At the Summary step of the wizard, review the updated status of the tenant's subscriptions, and click Finish.

[![Editing Azure Service Accounts](images/azure_settings_accounts_service_view_edit_summary.webp)](images/azure_settings_accounts_service_view_edit_summary.webp)

