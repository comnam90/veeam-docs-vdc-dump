---
title: "FSx Backup Retention"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_retention_backup_fsx.html"
last_updated: "3/30/2026"
product_version: ""
---

# FSx Backup Retention


For FSx file system backups, Veeam Data Cloud for AWS retains restore points in days, months and years. Restore points can be kept in a backup chain only for the period of time defined by an SLA template that you select in the backup policy settings. If Veeam Data Cloud for AWS detects that a restore point is older than the specified time limit, it removes this restore point from the backup chain.

