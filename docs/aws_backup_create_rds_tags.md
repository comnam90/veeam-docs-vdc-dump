---
title: "Step 7. Enable AWS Tags Assignment"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_backup_create_rds_tags.html"
last_updated: "3/20/2026"
product_version: ""
---

# Step 7. Enable AWS Tags Assignment


[This step applies only if you have enabled advanced settings at the Summary step of the wizard]

At the Tags step of the wizard, you can choose whether you want to assign to cloud-native snapshots of the selected RDS resources already existing tags and your own custom tags.

If you set the Add custom tags to created snapshots toggle to On, you must also specify the tags explicitly. To do that, use the Key and Value fields to specify a key and a value for the new custom AWS tag, and then click Add. Note that you cannot add more than 5 custom tags.

[![Enable AWS Tags Assignment ](images/aws_backup_create_rds_tags.webp)](images/aws_backup_create_rds_tags.webp "Enable AWS Tags Assignment ")

