---
title: "How Restore Mapping Works"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_restore_mapping.html"
last_updated: "3/25/2025"
product_version: ""
---

# How Restore Mapping Works


When restoring a record, Veeam Data Cloud uses the following algorithm to search for the record in Salesforce and compare it with the backed-up record:

* If the record exists in Salesforce, the product uses the ID of the record saved in the backup and updates the record using the backed-up data without applying any mapping rules.
* If the record exists in Salesforce but it is in the Salesforce Recycle Bin, the product uses the ID of the record saved in the backup and restores the record from the Recycle Bin without applying any mapping rules.
* If the record does not exist in Salesforce, the product does the following:

1. Checks whether the [default object mapping rule](sf_restore_settings.md#mapping_rule) can be applied. If yes, it restores the record using this mapping rule. If you have removed the rule manually, the product proceeds to the next step.
2. Checks whether an [alternate key](sf_restore_settings.md#alternate_keys) can be applied. If yes, it restores the record using this key. If no alternate keys have been added, the product proceeds to the next step.
3. Creates a new record in Salesforce with a new ID.

|  |
| --- |
| Important |
| * If you [specify override values for specific fields](sf_restore_records_options.md#override) when restoring a record, Veeam Data Cloud applies these settings first and then uses the override values to search for alternate keys. * If you apply a [data masking template](sf_settings_templates.md) when restoring a record, Veeam Data Cloud first masks data and then uses the masked values to search for alternate keys. * If you [configure mapping by field](sf_restore_records_options.md#map_old_fields) when restoring a record, Veeam Data Cloud first applies an alternate key and then the configured field mapping rules. |

