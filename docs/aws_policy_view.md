---
title: "Viewing Policy Details"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_policy_view.html"
last_updated: "3/30/2026"
product_version: ""
---

# Viewing Policy Details


[This section does not apply to RDS, DynamoDB, Redshift, EFS and FSx backup policies]

After you create an EC2 backup policy, Veeam Data Cloud for AWS displays this policy on the Policies page. Each policy is described with the following set of properties:

* Priority — the priority of the policy.
* Name — the name of the policy.
* State — the current state of the policy (enabled or disabled).
* Description — the reference information on the policy.
* Snapshot SLA — the most recent SLA compliance ratio calculated for all snapshots produced by the policy.
* Backup SLA — the most recent SLA compliance ratio calculated for all backups produced by the policy.

Each SLA compliance ratio on this page is calculated as an average for all EC2 instances that are added to the policy. To see how the SLA compliance ratio has been changing over a specific period (daily, monthly or weekly) for each EC2 instance protected by the policy, click the link in the Snapshot SLA or Backup SLA column. For more information, see [Monitoring Policy Performance](aws_sla_monitoring.md).

|  |
| --- |
| Tip |
| By default, Veeam Data Cloud for AWS applies the Daily filtering condition to the created EC2 backup policies. To switch between the filtering conditions, click Reporting SLA. |

SLA Status

The SLA compliance ratio can acquire the following statuses:

SLA Status

| Status | Icon | Description |
| Not configured | — | The SLA compliance ratio cannot be calculated as no corresponding backup schedule is configured in the SLA template applied to the EC2 backup policy. |
| Not available | — | The SLA compliance ratio has not been calculated yet. |
| SLA Met | ![Viewing Policy Details](images/checkmarkcircle.webp "Icon for databases") | The SLA compliance ratio equals or is greater than the target SLA value. |
| SLA Missed | ![Viewing Policy Details](images/error_circle.webp "Icon for databases") | The SLA compliance ratio is less than the target SLA value. |

To learn how the SLA compliance ratio is calculated, see [How Veeam Data Cloud for AWS Estimates SLA Compliance](aws_sla_calculation.md).

