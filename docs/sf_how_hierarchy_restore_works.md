---
title: "How Object Hierarchy Restore Works"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_how_hierarchy_restore_works.html"
last_updated: "7/24/2025"
product_version: ""
---

# How Object Hierarchy Restore Works


Consider the following example. You want to restore a record in the Contact object:

* This record refers to another record in the Account object. In this case, the Account object is the 1st level parent for the Contact object.
* The Case object is the 1st level child for the Contact object. There are 2 backed-up records in the Case object linked to the record you want to restore. If there are also records in the CaseMilestone object that are linked to these 2 records in the Case object, the CaseMilestone object will be the 2nd level child for the Contact object.

Parent Object Restore

By default, the product restores the 1st level parent records only (that is, the record in the Account object from our example). However, you can instruct Veeam Data Cloud to restore parent records of higher hierarchy levels as described in section [Restoring Records](sf_restore_records_hierarchy.md#advanced). While restoring a parent record, the product checks whether the record exists in Salesforce:

* If the parent record exists in Salesforce, the product skips the record and does not proceed to higher levels of the parent hierarchy for this record.
* If the parent record does not exist in Salesforce, the product creates the record in Salesforce using the backed-up data.

Child Object Restore

By default, the product restores child records 2 levels deep down the hierarchy only (that is, 2 records in the Case object and records in the CaseMilestone object in our example). However, you can instruct Veeam Data Cloud to restore child records of deeper hierarchy levels as described in section [Restoring Records](sf_restore_records_hierarchy.md#child_restore). While restoring a child record, the product checks whether the record exists in Salesforce and does either of the following:

* If a child record exists in Salesforce and has the same data as the backed-up record data, the product skips the record.
* If a child record exists in Salesforce, but the record data has changed, the product updates the record using the backed-up data.
* If a child record exists in Salesforce but it is in the Salesforce Recycle Bin, the product restores the record from the Recycle Bin.
* If a child record does not exist in Salesforce, the product creates the record in Salesforce using the backed-up data.

