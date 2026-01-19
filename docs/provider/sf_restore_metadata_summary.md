---
title: "Step 6. Finish Working with Wizard"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/sf_restore_metadata_summary.html"
last_updated: "8/22/2025"
product_version: ""
---

# Step 6. Finish Working with Wizard


At the Summary step of the wizard, review configured settings and click Finish.

If you want Veeam Data Cloud to start restore automatically after you complete the wizard, select the Start the session after clicking the Finish button check box. Otherwise, the session draft will be created, and you will have to manually run the session as described in section [Starting and Stopping Restore Jobs](sf_restore_start_stop.md).

|  |
| --- |
| Tip |
| To view all objects added to the restore job, click the link in the Object field. |

As soon as you start the restore job, you can see the status of the session both in Veeam Data Cloud and Salesforce. Consider that if you have any other running deploy sessions in Salesforce, the restore job may fail with an error indicating that another deploy is in progress. Wait until other sessions complete, and start the restore job again.

[![Finishing Work with Wizard](images/sf_restore_metadata_summary.webp)](images/sf_restore_metadata_summary.webp "Finishing Work with Wizard")

