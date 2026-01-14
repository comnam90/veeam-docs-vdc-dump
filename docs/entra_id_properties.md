---
title: "Supported Entra ID Item Properties"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/entra_id_properties.html"
last_updated: "12/19/2025"
product_version: ""
---

# Supported Entra ID Item Properties

In this article

Veeam Data Cloud protects the following Microsoft Entra ID items:

* Entra ID objects with their properties
* Entra ID audit logs
* Entra ID sign-in logs
* Microsoft Intune policies with their properties

Veeam Data Cloud supports the protection of the listed Entra ID objects and their properties:

Users

| Property | Comments |
| --- | --- |
| AccountEnabled | — |
| AgeGroup | — |
| AppRoleAssignments | — |
| AssignedLicenses | — |
| BusinessPhones | — |
| City | — |
| CompanyName | — |
| ConsentProvidedForMinor | — |
| Country | — |
| CreatedDateTime | Read-only property in Entra ID. |
| Department | — |
| DirectReports | — |
| DisplayName | — |
| EmployeeId | — |
| EmployeeType | — |
| FaxNumber | — |
| GivenName | — |
| Identities | — |
| JobTitle | — |
| Mail | — |
| MailNickname | — |
| Manager | — |
| MemberOf | — |
| MobilePhone | — |
| OfficeLocation | — |
| OnPremisesDistinguishedName | Read-only property in Entra ID. |
| OnPremisesDomainName | Read-only property in Entra ID. |
| OnPremisesExtensionAttributes | — |
| OnPremisesImmutableId | — |
| OtherMails | — |
| OwnedObjects | — |
| PasswordPolicies | — |
| PostalCode | — |
| PreferredDataLocation | — |
| State | — |
| StreetAddress | — |
| Surname | — |
| UsageLocation | — |
| UserPrincipalName | — |
| UserType | — |

|  |
| --- |
| Note |
| Besides the listed properties, Veeam Data Cloud also protects role assignments for the users. This role assignment protection is available for Microsoft Entra ID P2 and Governance tenant licenses. |

Groups

| Property | Comments |
| --- | --- |
| AppRoleAssignments | Not available for restore. |
| AssignedLabels | — |
| AssignedLicenses | — |
| Classification | — |
| CreatedDateTime | Read-only property in Entra ID. |
| Description | — |
| DisplayName | — |
| GroupTypes | — |
| IsAssignableToRole | Read-only property in Entra ID. |
| Mail | Read-only property in Entra ID. |
| MailEnabled | Read-only property in Entra ID. |
| MailNickname | — |
| MemberOf | — |
| Members | — |
| MembershipRule | — |
| MembershipRuleProcessingState | — |
| OnPremisesDomainName | Read-only property in Entra ID. |
| Owners | — |
| PreferredDataLocation | — |
| SecurityEnabled | — |
| Theme | — |
| Visibility | — |

Administrative Units

| Property | Comments |
| --- | --- |
| Description | — |
| Visibility | — |
| DisplayName | — |
| Extensions | Not supported for restore. |
| Members | Can be restored only for non-hidden administrative units. |
| ScopedRoleMembers | Limited to directory role membership, custom role membership is not supported. |

Roles

| Property | Comments |
| --- | --- |
| Description | — |
| DisplayName | — |
| InheritsPermissionsFrom | — |
| IsBuiltIn | Read-only property in Entra ID. |
| IsEnabled | — |
| ResourceScopes | — |
| RolePermissions | — |
| TemplateId | — |
| Version | — |

Applications and Service Principals

Applications

| Property | Comments |
| --- | --- |
| AddIns | — |
| Api | — |
| AppId | Read-only property in Entra ID. |
| ApplicationTemplateId | Read-only property in Entra ID. |
| AppRoles | — |
| Certification | Read-only property in Entra ID. |
| CreatedDateTime | Read-only property in Entra ID. |
| Description | — |
| DisabledByMicrosoftStatus | Read-only property in Entra ID. |
| DisplayName | — |
| ExtensionProperties | — |
| FederatedIdentityCredentials | — |
| GroupMembershipClaims | — |
| IdentifierUris | — |
| Info | — |
| IsDeviceOnlyAuthSupported | — |
| IsFallbackPublicClient | — |
| Notes | — |
| Oauth2RequirePostResponse | — |
| OptionalClaims | — |
| Owners | — |
| ParentalControlSettings | — |
| PublicClient | — |
| PublisherDomain | Read-only property in Entra ID. |
| RequestSignatureVerification | — |
| RequiredResourceAccess | — |
| SamlMetadataUrl | — |
| ServiceManagementReference | — |
| ServicePrincipalLockConfiguration | — |
| SignInAudience | — |
| Spa | — |
| Tags | — |
| TokenEncryptionKeyId | Read-only property in Entra ID. |
| VerifiedPublisher | Read-only property in Entra ID. |
| Web | — |

Service Principals

| Property | Comments |
| --- | --- |
| AccountEnabled | — |
| AddIns | Read-only property. The property value is inherited from the associated application. |
| AlternativeNames | — |
| AppDescription | Read-only property. The property value is inherited from the associated application. |
| AppDisplayName | Read-only property. The property value is inherited from the associated application. |
| AppId | Read-only property in Entra ID. |
| ApplicationTemplateId | Read-only property in Entra ID. |
| AppManagementPolicies | Read-only property in Entra ID. |
| AppOwnerOrganizationId | Read-only property in Entra ID. |
| AppRoleAssignedTo | — |
| AppRoleAssignmentRequired | — |
| AppRoleAssignments | — |
| AppRole | Read-only property. The property value is inherited from the associated application. |
| Description | — |
| DisabledByMicrosoftStatus | Read-only property in Entra ID. |
| DisplayName | Read-only property. The property value is inherited from the associated application. |
| Endpoints | — |
| FederatedIdentityCredentials | Read-only property in Entra ID. |
| Homepage | Read-only property. The property value is inherited from the associated application. |
| Info | Read-only property. The property value is inherited from the associated application. |
| LoginUrl | — |
| LogoutUrl | Read-only property in Entra ID. |
| MemberOf | — |
| Notes | — |
| NotificationEmailAddresses | — |
| Oauth2PermissionGrants | — |
| Oauth2PermissionScopes | Read-only property. The property value is inherited from the associated application. |
| OwnedObjects | Read-only property in Entra ID. |
| Owners | — |
| PasswordCredentials | Read-only property in Entra ID. |
| PreferredSingleSignOnMode | — |
| ReplyUrls | Read-only property in Entra ID. |
| ResourceSpecificApplicationPermissions | Read-only property in Entra ID. |
| SamlSingleSignOnSettings | — |
| ServicePrincipalNames | Read-only property. The property value is inherited from the associated application. |
| ServicePrincipalType | Read-only property in Entra ID. |
| SignInAudience | Read-only property in Entra ID. |
| Tags | — |
| TokenEncryptionKeyId | Read-only property in Entra ID. |
| VerifiedPublisher | Read-only property in Entra ID. |

Conditional Access Policies

| Property | Comments |
| --- | --- |
| Conditions | — |
| CreatedDateTime | Read-only property in Entra ID. |
| DisplayName | — |
| GrantControls | — |
| ModifiedDateTime | Read-only property in Entra ID. |
| SessionControls | — |
| State | — |
| TemplateId | Read-only property in Entra ID. |

Microsoft Intune Policies

Microsoft Intune Policy Types

| Policy Type | Comments |
| --- | --- |
| AndroidCompliancePolicy | — |
| AndroidCustomConfiguration | — |
| AndroidGeneralDeviceConfiguration | — |
| AndroidWorkProfileCompliancePolicy | — |
| AndroidWorkProfileGeneralDeviceConfiguration | — |
| IosCompliancePolicy | — |
| IosCustomConfiguration | — |
| IosDeviceFeaturesConfiguration | — |
| IosGeneralDeviceConfiguration | — |
| IosUpdateConfiguration | — |
| MacOSCompliancePolicy | — |
| MacOSCustomConfiguration | — |
| MacOSDeviceFeaturesConfiguration | — |
| MacOSGeneralDeviceConfiguration | — |
| SharedPCConfiguration | — |
| Windows10CompliancePolicy | — |
| Windows10CustomConfiguration | — |
| Windows10EndpointProtectionConfiguration | — |
| Windows10EnterpriseModernAppManagementConfiguration | — |
| Windows10GeneralConfiguration | — |
| Windows10MobileCompliancePolicy | — |
| Windows10SecureAssessmentConfiguration | — |
| Windows10TeamGeneralConfiguration | — |
| Windows81CompliancePolicy | — |
| Windows81GeneralConfiguration | — |
| WindowsDefenderAdvancedThreatProtectionConfiguration | — |
| WindowsPhone81CustomConfiguration | — |
| WindowsPhone81GeneralConfiguration | — |
| WindowsUpdateForBusinessConfiguration | — |

Microsoft Intune Policy Properties

* [Supported Microsoft Intune Policy Properties A to B](entra_id_properties_intune_ab.md)
* [Supported Microsoft Intune Policy Properties C to E](entra_id_properties_intune_ce.md)
* [Supported Microsoft Intune Policy Properties F to L](entra_id_properties_intune_fl.md)
* [Supported Microsoft Intune Policy Properties M to P](entra_id_properties_intune_mp.md)
* [Supported Microsoft Intune Policy Properties Q to S](entra_id_properties_intune_qs.md)
* [Supported Microsoft Intune Policy Properties T to W](entra_id_properties_intune_tw.md)

Page updated 12/19/2025
