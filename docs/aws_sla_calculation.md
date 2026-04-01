---
title: "How Veeam Data Cloud for AWS Estimates SLA Compliance"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_sla_calculation.html"
last_updated: "2/26/2026"
product_version: ""
---

# How Veeam Data Cloud for AWS Estimates SLA Compliance


To estimate SLA compliance for an EC2 backup policy, Veeam Data Cloud for AWS performs the following steps:

1. Calculates the SLA compliance ratio individually for each EC2 instance added to the backup scope. The SLA compliance ratio equals a percentage of restore points successfully created for the EC2 instance out of the total number of restore points expected to be produced by the backup policy for this instance.

When calculating the SLA compliance ratio for daily, weekly and monthly restore points, Veeam Data Cloud for AWS takes into account the SLA template that is assigned to the backup policy.

1. Uses the ratios calculated at step 1 to determine the average SLA compliance ratio for the policy.
2. Compares the average SLA compliance ratio calculated at step 2 and the target SLA value configured for the policy. If the average SLA compliance ratio equals or is greater than the target SLA value, Veeam Data Cloud for AWS marks this policy as meeting SLA standards.

Impact of Backup Scope Changes on SLA Compliance Estimation

When calculating the SLA compliance ratio for each EC2 instance added to the backup scope of an backup policy, Veeam Data Cloud for AWS estimates the total number of restore points expected to be produced for this instance based on the number of policy sessions remaining at the time when the instance was added to the backup scope. This means that when a new EC2 instance is added to the backup scope (either manually or automatically) during the data protection window defined by the SLA template, Veeam Data Cloud for AWS considers all the preceding policy sessions as completed successfully for this instance.

Consider the following example. You configure an EC2 backup policy using the Silver SLA template, which provides the medium backup frequency and mid-range retention. Cloud-native snapshots are created every 8 hours and retained for 1 day, weekly image-level backups are created once per day and retained for 30 days, monthly image-level backups are created on the 1st of each month and retained for 12 months.

The daily cloud-native snapshots are scheduled every 8 hours for all EC2 instances included in the backup scope. After 1 snapshot has been successfully created, you add a new instance to the backup scope. The remaining number of snapshots expected to be produced equals 2. As soon as Veeam Data Cloud for AWS finalizes the snapshot window in all the protected AWS Regions, 1 snapshot that was produced during the first backup session will be considered as created successfully — and the SLA compliance ratio for the newly added instance will be calculated depending on the results of the last 2 sessions:

* If Veeam Data Cloud for AWS successfully creates both remaining snapshots, the SLA compliance ratio will equal (1 + 2) / 3 × 100% = 100% for the instance.
* If Veeam Data Cloud for AWS successfully creates only 1 of the remaining snapshots (meaning that 1 session fails), the SLA compliance ratio will equal (1 + 1) / 3 × 100% = 67% for the instance.

Impact of SLA Template Changes on SLA Compliance Estimation

Veeam Data Cloud for AWS estimates SLA compliance for each backup policy based on the schedule settings configured for the SLA template that is assigned to this policy. When you modify snapshot or backup settings for an SLA template or assign another template to a backup policy, this affects the SLA compliance ratio retrospectively — meaning that Veeam Data Cloud for AWS recalculates the SLA compliance ratio for all entries on the SLA Compliance Overview chart.

For example, if you select the Silver SLA template in the backup policy settings and the backup policy is configured to produce daily snapshots every 8 hours over a 24-hour period, and 3 snapshots are successfully created on time, this means that the SLA compliance ratio will be 100%. If you reconfigure the policy to use the Gold SLA template, which produces cloud-native snapshots every hour over a 24-hour period, and the policy successfully creates only 12 snapshots on time, this means that the SLA compliance ratio will change to 50% on the SLA Compliance Overview chart.

