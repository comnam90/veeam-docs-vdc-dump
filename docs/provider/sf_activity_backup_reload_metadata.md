---
title: "Reloading Metadata"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/sf_activity_backup_reload_metadata.html"
last_updated: "10/17/2025"
product_version: ""
---

# Reloading Metadata


If you want to back up missing metadata items, you must reload the metadata. To reload metadata, Veeam Data Cloud starts a reload session and compare backed-up data in the product database with data currently stored in Salesforce. If Veeam Data Cloud detects that the same metadata item exists both in Salesforce and in the product database, the item is skipped from processing; otherwise, Veeam Data Cloud backs up the item.

To reload metadata, do the following:

1. On the Salesforce page, click the name of the tenant you want to manage.
2. To view the list of backup sessions, select Activity on the left.
3. Choose the latest metadata session and click Reload Metadata.

[![Reloading Metadata](images/sf_backup_policies_reload_metadata.webp)](images/sf_backup_policies_reload_metadata.webp "Reloading Metadata")

