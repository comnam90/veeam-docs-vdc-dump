---
title: "Creating Archival Policies"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/sf_archival_policies_create.html"
last_updated: "3/25/2025"
product_version: ""
---

# Creating Archival Policies

In this article

You can create one or multiple archival policies for each Salesforce tenant. An archival policy can archive records of one root object only. If you want to archive records of multiple root objects, create an archival policy for each object.

Before you run an archival policy, deactivate [Flows](https://help.salesforce.com/s/articleView?id=sf.flow_distribute_activate.htm&type=5), [Validation Rules](https://help.salesforce.com/s/articleView?id=sf.fields_activating_field_validation_rules.htm&type=5) and [Apex Triggers](https://help.salesforce.com/s/articleView?id=000385540&type=1) in Salesforce since business logic and automated rules configured in Salesforce can block Veeam Data Cloud archival operations and trigger undesirable side processes.

To create an archival policy, use the Add Archival Policy wizard:

1. [Launch the Add Archival Policy wizard](sf_archival_policies_create_launch.md).
2. [Specify a name and description for the archival policy](sf_archival_policies_create_name.md).
3. [Verify the Salesforce tenant](sf_archival_policies_create_organization.md).
4. [Choose data that will be archived](sf_archival_policies_create_data.md).
5. [Configure general archival settings](sf_archival_policies_create_options.md).
6. [Verify backup consistency](sf_archival_policies_create_verify.md).
7. [Finish working with the wizard](sf_archival_policies_create_summary.md).

Page updated 3/25/2025
