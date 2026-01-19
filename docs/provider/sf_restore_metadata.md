---
title: "Restoring Metadata"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/sf_restore_metadata.html"
last_updated: "5/6/2025"
product_version: ""
---

# Restoring Metadata


You can restore metadata of objects deleted from Salesforce, including Apex classes, connected app configurations, reports, dashboards and so on. You can recover metadata to the same Salesforce tenant or to another tenant so that the object metadata in one Salesforce tenant matches the metadata in another one.

Before you restore a Salesforce metadata component, make sure that all components the metadata file depends on already exist on the target Salesforce tenant. To restore the components, create a separate metadata restore job. For example:

* If you want to restore flow definitions (FlowDefinition metadata file), restore the Flow metadata file first. For details on the FlowDefinition dependencies, see [Salesforce Documentation](https://developer.salesforce.com/docs/atlas.en-us.api_meta.meta/api_meta/meta_flowdefinition.htm).
* If you want to restore session settings (ProfileSessionSetting metadata file), restore the Profile metadata file first. For details on the ProfileSessionSetting dependencies, see [Salesforce Documentation](https://developer.salesforce.com/docs/atlas.en-us.api_meta.meta/api_meta/meta_profilesessionsetting.htm).
* If you want to restore password policies (ProfilePasswordPolicy metadata file), restore the Profile metadata file first. For details on the ProfilePasswordPolicy dependencies, see [Salesforce Documentation](https://developer.salesforce.com/docs/atlas.en-us.api_meta.meta/api_meta/meta_profilepasswordpolicy.htm).

|  |
| --- |
| Note |
| * Before you restore records, field values, or files of a deleted Salesforce object, you must restore the object metadata and then back up this object to make it available in the restore wizard.  * If you want to restore metadata of a [custom object](https://help.salesforce.com/s/articleView?id=platform.dev_objectedit.htm&type=5) that was deleted from Salesforce permanently, you must restore the following types of metadata first: CustomObject, CustomTab, Layout and Profile. Note that when restoring metadata of the Profile type, you must choose all profiles that have access to the custom object. * If you delete a metadata field from Salesforce and then create a new field using the same API name, Veeam Data Cloud will treat this field as the same item when restoring metadata and will populate it with the values of the deleted field. |

To restore Salesforce metadata, perform the following steps:

1. [Launch the Restore Metadata wizard](sf_restore_metadata_launch.md).
2. [Specify a name and description for the restore job](sf_restore_metadata_name.md).
3. [Select a target Salesforce tenant](sf_restore_metadata_organization.md).
4. [Select objects whose metadata will be restored](sf_restore_metadata_data.md).
5. [Review the restore list](sf_restore_metadata_restore_list.md).
6. [Finish working with the wizard](sf_restore_metadata_summary.md).

