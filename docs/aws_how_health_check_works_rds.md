---
title: "How Health Check Works"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_how_health_check_works_rds.html"
last_updated: "3/17/2026"
product_version: ""
---

# How Health Check Works


When Veeam Data Cloud for AWS saves a new backup restore point to a backup repository, it calculates CRC values for metadata in the backup chain and saves these values to the chain metadata, together with the instance data. When performing a health check, Veeam Data Cloud for AWS verifies the availability of data blocks and uses the saved values to ensure that the restore points being verified are consistent.

Veeam Data Cloud for AWS performs the following operations on the last day of each month to run a health check:

1. As soon as a backup policy session completes successfully, Veeam Data Cloud for AWS starts the health check as a new session. For each restore point in the standard backup chain, Veeam Data Cloud for AWS calculates CRC values for backup metadata and compares them with the CRC values that were previously saved to the restore point. Veeam Data Cloud for AWS also checks whether data blocks that are required to rebuild the restore point are available.
2. If Veeam Data Cloud for AWS does not detect data inconsistency, the health check session completes successfully. Otherwise, the session completes with an error.

Depending on the detected data inconsistency, Veeam Data Cloud for AWS performs the following operations:

* If the health check detects corrupted metadata in a full or an incremental restore point, Veeam Data Cloud for AWS marks the backup chain as corrupted in the configuration database. During the next backup policy session, Veeam Data Cloud for AWS copies the full instance image, creates a full restore point in the backup repository and starts a new backup chain in the backup repository.

|  |
| --- |
| Note |
| Veeam Data Cloud for AWS does not support metadata check for encrypted backup chains. |

* If the health check detects corrupted disk blocks in a full or an incremental restore point, Veeam Data Cloud for AWS marks the restore point that includes the corrupted data blocks and all subsequent affected incremental restore points as incomplete in the configuration database. During the next backup policy session, Veeam Data Cloud for AWS reads whole data blocks and copies those data blocks that have changed since the previous backup session with corrupted data blocks, and saves these data blocks to the latest restore point that has been created during the current session.

All restore points marked as incomplete will be deleted according to the retention policy settings.

