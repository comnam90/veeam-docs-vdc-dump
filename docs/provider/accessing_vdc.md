---
title: "Accessing Veeam Data Cloud"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/accessing_vdc.html"
last_updated: "2026"
product_version: ""
---

# Accessing Veeam Data Cloud


Before you can start using Veeam Data Cloud, make sure you have a Veeam account and an active subscription. After your subscription is activated, you will receive an email invitation to your newly created Veeam Data Cloud organization. Follow the link in the invitation to log in to Veeam Data Cloud and start using the service.

Getting Access to Veeam Data Cloud

To obtain access to Veeam Data Cloud, follow these steps:

1. If you do not have a Veeam account, sign up at the Veeam My Account Portal and specify a user who will be the license administrator for your company. For details, see [this Veeam KB article](https://www.veeam.com/kb4034).

The license administrator will become the first user of your Veeam Data Cloud organization.

1. Request a subscription to a Veeam Data Cloud workload through one of the Veeam sales channels. For details, see [Veeam Data Cloud Purchasing Options](https://www.veeam.com/products/veeam-data-cloud/purchasing-options.html).

Once your subscription is activated, you will receive an email with an invitation link to your Veeam Data Cloud organization.

1. Accept the invitation and log in to Veeam Data Cloud. For the first login to Veeam Data Cloud, use the Veeam My Account credentials of the license administrator. For details, see [Logging in to Veeam Data Cloud](accessing_vdc.md#logginginlink).

As the first user of your Veeam Data Cloud organization, accept Veeam Data Cloud terms and conditions to start working with Veeam Data Cloud. The first user of your Veeam Data Cloud organization is automatically assigned the OrganizationAdmin role, which allows them to manage users and perform all configuration actions.

Enabling Multi-Factor Authentication

Veeam Data Cloud supports multi-factor authentication (MFA) through its identity providers. For more information on how to enable MFA for your Veeam My Account, see [this Veeam KB article](https://www.veeam.com/kb4716). For more information on how to enable MFA for sign-in with a Microsoft 365 account, see [Microsoft documentation](https://learn.microsoft.com/en-us/entra/identity/authentication/tutorial-enable-azure-mfa).

|  |
| --- |
| Important |
| Veeam Data Cloud requires multi-factor authentication for users who log in with Veeam My Account. |

Logging In to Veeam Data Cloud

To access Veeam Data Cloud, you can use the direct link to the Veeam Data Cloud portal that you received in your invitation email or go to the <https://cloud.veeam.com> webpage.

To log in to the Veeam Data Cloud portal, use your Veeam My Account credentials or your Microsoft 365 account.

|  |
| --- |
| Note |
| * Veeam Data Cloud supports the latest stable versions of Google Chrome, Microsoft Edge (Chromium only) and Mozilla Firefox browsers. * Veeam Data Cloud automatically logs you out after 30 minutes of inactivity and displays a notification two minutes before the session ends. |

Logging In with Invitation Link

To log in to Veeam Data Cloud using the link that you received in your invitation email, do the following:

1. In the invitation email that you received, click Accept Invitation.
2. On the Veeam Data Cloud portal, select your sign in method:

* Select Continue with Microsoft to log in with your Microsoft 365 account. You will be redirected to the Microsoft Entra authentication page.
* Select Continue with Veeam to log in with your Veeam My Account credentials. You will be redirected to the Sign in to Veeam authentication page.

1. Specify or select your credentials that you want to use to log in to Veeam Data Cloud.

If you log in to Veeam Data Cloud with your Microsoft account for the first time, you must accept permissions for the Veeam Data Cloud enterprise application. For details, see [Microsoft Entra Application Permissions](accessing_vdc.md#permissions).

1. If your account is a part of multiple Veeam Data Cloud organizations, on the Choose an Organization page, select an organization you want to manage.

[![Overview](images/accessing_vdc_login.webp)](images/accessing_vdc_login.webp "Overview")

Logging In with Portal URL

To log in to Veeam Data Cloud, do the following:

1. Open the <https://cloud.veeam.com> URL in your browser.
2. On the Veeam Data Cloud portal, select your sign in method:

* Select Continue with Microsoft to log in with your Microsoft 365 account. You will be redirected to the Microsoft Entra authentication page.
* Select Continue with Veeam to log in with your Veeam My Account credentials. You will be redirected to the Sign in to Veeam authentication page.

1. Specify or select your credentials that you want to use to log in to Veeam Data Cloud.

If you log in to Veeam Data Cloud with your Microsoft account for the first time, you must accept permissions for the Veeam Data Cloud enterprise application. For details, see [Microsoft Entra Application Permissions](accessing_vdc.md#permissions).

1. If your account is a part of multiple Veeam Data Cloud organizations, on the Choose an Organization page, select an organization you want to manage.

[![Overview](images/accessing_vdc_login.webp)](images/accessing_vdc_login.webp "Overview")

Logging Out

To log out, click the user name initials in the top-right corner of the Veeam Data Cloud page, and then click Sign Out.

[![Overview](images/sp_accessing_vdc_logout.webp)](images/sp_accessing_vdc_logout.webp "Overview")

Microsoft Entra Application Permissions

When you log in to Veeam Data Cloud with your Microsoft account for the first time, you must accept permissions for the Veeam Data Cloud enterprise application. If your Microsoft account is not authorized to accept the requested permissions, ask your Microsoft Entra ID administrator to grant the permissions on behalf of your organization or to approve the pending Veeam Data Cloud enterprise application in your Microsoft Entra ID tenant.

The Veeam Data Cloud enterprise application requires the following permissions.

Microsoft Entra Application Permissions

| Permission | Type | Description |
| Sign you in and read your profile | — | — |
| openid | Delegated | Allows users to sign in to the app with their work or school accounts and allows the app to see basic user profile information. |
| profile | Delegated | Allows the app to see the basic profile of the users (name, picture, user name, email address). |
| email | Delegated | Allows the app to read the primary email address of the users. |
| User.Read | Delegated | Allows users to sign-in to the app, and allows the app to read the profile of signed-in users. It also allows the app to read basic company information of signed-in users. |
| Maintain access to data you have given access to | — | — |
| offline\_access | Delegated | Allows the app to see and update the data you gave it access to, even when users are not currently using the app. This does not give the app any additional permissions. |

Page updated 2026-07-09
