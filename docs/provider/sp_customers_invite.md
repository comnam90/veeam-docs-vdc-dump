---
title: "Customer-Managed Onboarding"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/sp_customers_invite.html"
last_updated: "4/15/2026"
product_version: ""
---

# Customer-Managed Onboarding


You can invite customers to complete the onboarding process themselves. Customers will receive an email with an invitation link that allows them to sign up to Veeam Data Cloud and add a new tenant to the Veeam Data Cloud workload they were invited to. The customers that you want to invite must have an assigned subscription. For details, see [Requesting Subscriptions](sp_subscriptions_request.md).

After you invite a customer to add the first tenant to their Veeam Data Cloud organization, Veeam Data Cloud will automatically disable the Delegated management by partner option in the customer Veeam Data Cloud organization. If this option is disabled, you cannot manage Veeam Data Cloud tenants and users in the customer organization. However, you can still add tenants and invite the customer to add tenants to the Veeam Data Cloud organization of the customer. Customers can also enable the Delegated management by partner option again. For details, see the [Configuring Partner Access](https://helpcenter.veeam.com/docs/vdc/userguide/sp_partner_access.html) section of the Veeam Data Cloud User Guide.

To add a workload tenant and complete the onboarding process, the customer must accept and activate the invitation. For details, see [Activating Invitations](#activatinginvitation).

You can resend, edit and cancel the invitation you have sent to your customer. For details, see [Managing Invitations](sp_customers_invite_manage.md).

Inviting Customers

To invite a customer to complete self-service onboarding, follow these steps:

1. Log in to Veeam Data Cloud. For details, see [Accessing Veeam Data Cloud](accessing_vdc.md).
2. To open the list of tenants for a specific Veeam Data Cloud workload, click a workload name on the left.
3. Click Add Tenant.
4. On the Add Tenant page, from the Subscription drop-down list, select a subscription of the customer you want to invite.
5. Select Send an invite.
6. In the Email field, specify an email to which you want to send the invitation.
7. Click Send.
8. In the Send Invitation window, click Continue to confirm sending the invitation email.

[![Specifying Customer](images/sp_customers_invite.webp)](images/sp_customers_invite.webp "Specifying Customer")

Activating Invitations

After your customer receives the invitation, they must activate it to add a workload tenant and complete the onboarding.

To activate the invitation, the customer must follow these steps:

1. Log in to Veeam Data Cloud with the invitation link. For details, see [Accessing Veeam Data Cloud](accessing_vdc.md#logginginlink).
2. On the Veeam Data Cloud Overview page, select the workload that has the pending invitation.

Alternatively, select the required workload on the left.

1. On the workload page, click the menu icon in the Actions column of the invitation and select Activate Invitation.

Veeam Data Cloud will launch the Add Tenant wizard for the selected workload. The customer must complete the wizard to add the tenant and finish the onboarding process.

[![Specifying Customer](images/sp_customers_invite_activate.webp)](images/sp_customers_invite_activate.webp "Specifying Customer")

