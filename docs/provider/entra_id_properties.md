---
title: "Supported Entra ID Item Properties"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/entra_id_properties.html"
last_updated: "1/14/2026"
product_version: ""
---

# Supported Entra ID Item Properties


Veeam Data Cloud for Microsoft Entra ID protects the following items:

* Entra ID objects with their properties
* Microsoft Intune policies with their properties
* Entra ID audit logs
* Entra ID sign-in logs

This article lists all supported properties for the items that Veeam Data Cloud for Microsoft Entra ID protects.

Users

Veeam Data Cloud for Microsoft Entra ID protects the following Entra ID user properties.

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

Veeam Data Cloud for Microsoft Entra ID protects the following Entra ID group properties.

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

Veeam Data Cloud for Microsoft Entra ID protects the following Entra ID administrative unit properties.

| Property | Comments |
| --- | --- |
| Description | — |
| Visibility | — |
| DisplayName | — |
| Extensions | Not supported for restore. |
| Members | Can be restored only for non-hidden administrative units. |
| ScopedRoleMembers | Limited to directory role membership, custom role membership is not supported. |

Roles

Veeam Data Cloud for Microsoft Entra ID protects the following Entra ID role properties.

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

Veeam Data Cloud for Microsoft Entra ID protects the following properties of Entra ID applications and service principals.

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

Veeam Data Cloud for Microsoft Entra ID protects the following properties of Entra ID conditional access policies.

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

Veeam Data Cloud for Microsoft Entra ID protects the following types of Microsoft Intune policies. For more information on supported properties for each policy type, see [Supported Microsoft Intune Policy Properties](entra_id_properties_intune.md).

| Policy Type | Comments |
| --- | --- |
| AndroidCompliancePolicy | For details on supported properties, see [AndroidCompliancePolicy](entra_id_properties_intune.md#androidcompliancepolicy). |
| AndroidCustomConfiguration | For details on supported properties, see [AndroidCustomConfiguration](entra_id_properties_intune.md#androidcustomconfiguration). |
| AndroidGeneralDeviceConfiguration | For details on supported properties, see [AndroidGeneralDeviceConfiguration](entra_id_properties_intune.md#androidgeneraldeviceconfiguration). |
| AndroidWorkProfileCompliancePolicy | For details on supported properties, see [AndroidWorkProfileCompliancePolicy](entra_id_properties_intune.md#androidworkprofilecompliancepolicy). |
| AndroidWorkProfileGeneralDeviceConfiguration | For details on supported properties, see [AndroidWorkProfileGeneralDeviceConfiguration](entra_id_properties_intune.md#androidworkprofilegeneraldeviceconfiguration). |
| IosCompliancePolicy | For details on supported properties, see [IosCompliancePolicy](entra_id_properties_intune.md#ioscompliancepolicy). |
| IosCustomConfiguration | For details on supported properties, see [IosCustomConfiguration](entra_id_properties_intune.md#ioscustomconfiguration). |
| IosDeviceFeaturesConfiguration | For details on supported properties, see [IosDeviceFeaturesConfiguration](entra_id_properties_intune.md#iosdevicefeaturesconfiguration). |
| IosGeneralDeviceConfiguration | For details on supported properties, see [IosGeneralDeviceConfiguration](entra_id_properties_intune.md#iosgeneraldeviceconfiguration). |
| IosUpdateConfiguration | For details on supported properties, see [IosUpdateConfiguration](entra_id_properties_intune.md#iosupdateconfiguration). |
| MacOSCompliancePolicy | For details on supported properties, see [MacOSCompliancePolicy](entra_id_properties_intune.md#macoscompliancepolicy). |
| MacOSCustomConfiguration | For details on supported properties, see [MacOSCustomConfiguration](entra_id_properties_intune.md#macoscustomconfiguration). |
| MacOSDeviceFeaturesConfiguration | For details on supported properties, see [MacOSDeviceFeaturesConfiguration](entra_id_properties_intune.md#macosdevicefeaturesconfiguration). |
| MacOSGeneralDeviceConfiguration | For details on supported properties, see [MacOSGeneralDeviceConfiguration](entra_id_properties_intune.md#macosgeneraldeviceconfiguration). |
| SharedPCConfiguration | For details on supported properties, see [SharedPCConfiguration](entra_id_properties_intune.md#sharedpcconfiguration). |
| Windows10CompliancePolicy | For details on supported properties, see [Windows10CompliancePolicy](entra_id_properties_intune.md#windows10compliancepolicy). |
| Windows10CustomConfiguration | For details on supported properties, see [Windows10CustomConfiguration](entra_id_properties_intune.md#windows10customconfiguration). |
| Windows10EndpointProtectionConfiguration | For details on supported properties, see [Windows10EndpointProtectionConfiguration](entra_id_properties_intune.md#windows10endpointprotectionconfiguration). |
| Windows10EnterpriseModernAppManagementConfiguration | For details on supported properties, see [Windows10EnterpriseModernAppManagementConfiguration](entra_id_properties_intune.md#windows10enterprisemodernappmanagementconfiguration). |
| Windows10GeneralConfiguration | For details on supported properties, see [Windows10GeneralConfiguration](entra_id_properties_intune.md#windows10generalconfiguration). |
| Windows10MobileCompliancePolicy | For details on supported properties, see [Windows10MobileCompliancePolicy](entra_id_properties_intune.md#windows10mobilecompliancepolicy). |
| Windows10SecureAssessmentConfiguration | For details on supported properties, see [Windows10SecureAssessmentConfiguration](entra_id_properties_intune.md#windows10secureassessmentconfiguration). |
| Windows10TeamGeneralConfiguration | For details on supported properties, see [Windows10TeamGeneralConfiguration](entra_id_properties_intune.md#windows10teamgeneralconfiguration). |
| Windows81CompliancePolicy | For details on supported properties, see [Windows81CompliancePolicy](entra_id_properties_intune.md#windows81compliancepolicy). |
| Windows81GeneralConfiguration | For details on supported properties, see [Windows81GeneralConfiguration](entra_id_properties_intune.md#windows81generalconfiguration). |
| WindowsDefenderAdvancedThreatProtectionConfiguration | For details on supported properties, see [WindowsDefenderAdvancedThreatProtectionConfiguration](entra_id_properties_intune.md#windowsdefenderadvancedthreatprotectionconfiguration). |
| WindowsPhone81CustomConfiguration | For details on supported properties, see [WindowsPhone81CustomConfiguration](entra_id_properties_intune.md#windowsphone81customconfiguration). |
| WindowsPhone81GeneralConfiguration | For details on supported properties, see [WindowsPhone81GeneralConfiguration](entra_id_properties_intune.md#windowsphone81generalconfiguration). |
| WindowsUpdateForBusinessConfiguration | For details on supported properties, see [WindowsUpdateForBusinessConfiguration](entra_id_properties_intune.md#windowsupdateforbusinessconfiguration). |

