---
title: "Setting Policy Priority"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_policy_priority.html"
last_updated: "3/19/2026"
product_version: ""
---

# Setting Policy Priority


By default, Veeam Data Cloud for AWS runs backup policies in the order you create them. However, you can set the backup policy priority manually:

1. On the tenant administration page, navigate to Policies.

1. Switch to the necessary tab and click Policy Priority.
2. In the Priority Order window, do the following:

1. Select a backup policy in the list of existing policies.
2. To move the policy up or down the list, use the Up and Down arrows.
3. To save changes made to the priority order, click Apply.

|  |
| --- |
| Note |
| If a resource is included into multiple backup policies, it will be processed only by the backup policy that has the highest priority. |

[![Setting Policy Priority](images/aws_policy_priority.webp)](images/aws_policy_priority.webp "Setting Policy Priority")

