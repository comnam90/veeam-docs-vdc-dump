---
title: "Unsupported Salesforce Objects"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/sf_unsupported_objects.html"
last_updated: "10/6/2025"
product_version: ""
---

# Unsupported Salesforce Objects


Veeam Data Cloud supports backup of objects available in API version 60 and earlier. However, most of the objects that cannot be restored are not collected. You can tell these objects in Salesforce by the following flags assigned: creatable = false, updatable = false. The only exception is that backup of the \*History objects is supported. For more information on backup and restore limitations, see [Considerations and Limitations](sf_limitations.md#limitations).

By default, Veeam Data Cloud can archive all objects and file types that can be restored. For the list of objects that cannot be archived, see the following table:

| Operation | Unsupported Objects |
| --- | --- |
| Backup | \*\_\_b, \*\_\_ViewStat, \*\_\_VoteStat, \*\_\_x, \*\_\_hd, \*\_\_ChangeEvent, \*\_\_VersionHistory, \*Event, \*EventStream, \*Feed, AccountUserTerritory2View, ActivityMetric, ActivityMetricRollup, AggregateResult, AnalyticsBotSession, AnlytDataAssetEventStore, ApexEmailNotification, ApexPageInfo, ApexTestQueueItem, ApexTestResult, ApexTestResultLimits, ApexTestRunResult, ApexTestSuite, AppTabMember, AuraDefinitionInfo, BackgroundOperationResult, BotAnalytics, BotEventLog, BulkApiResultEventStore, CleanDataService, CollaborationGroupRecord, ColorDefinition, ContentFolderItem, ContentFolderMember, ContentHubItem, DatacloudAddress, DatacloudCompany, DatacloudContact, DatacloudDandBCompany, DatacloudSocialHandle, DataEncryptionKey, DataStatistics, DataType, DcsnTblSourceObjectRecord, DcSocialProfile, DcSocialProfileHandle, DecisionTableDataset, DecisionTableRecordset, EmbeddedServiceLabel, EngagementHistory, EntityDefinition, EntityParticle, FieldDefinition, FieldHistoryArchive, FlexQueueItem, FlowDefinitionView, FlowVariableView, FlowVersionView, IconDefinition, Idea, IdeaComment, IdeaReputation, IdeaReputationLevel, IdeaTheme, InstalledPackage, InterfaceFieldMapping, ListViewChartInstance, ManagedCintentType, NetworkUserHistoryRecent, OauthToken, OmniRoutingEventStore, OutgoingEmail, OutgoingEmailRelation, OwnerChangeOptionInfo, PermissionSetEventS, PicklistValueInfo, PlatformAction, RecentlyViewed, RecordActionHistory, RecordRecommendation, RecordVisibility, Regular\_articles\_kav, RelationshipDomain, RelationshipInfo, SalesStore, SearchLayout, SiteDetail, SubscriberPackage, TenantUsageEntitlement, UserAppMenuItem, UserEmailCalendarSync, UserEntityAccess, UserFieldAccess, UserProfileFeed, UserRecordAccess, Vote  Note: Since Salesforce does not provide API to export and restore Session Settings of a Salesforce profile, as well as Object Permissions of the AiMetadata Sync Status, Archive Job Session, Rebate Payout Snapshot, User External Credential and Web Cart Document objects, backup of this type of data is not supported. |
| Restore | AccountPartner, ContentFolder, DigitalSignature, OpportunityPartner |
| Archive | \*History, \*Share, \*Tag, AccountPartner, ContentNote, ContentFolder, MailmergeTemplate, MobileApplicationDetail, OpportunityPartner, Organization, Profile, RecordType, SelfServiceUser, User, standard Salesforce objects that cannot be deleted through API. |

