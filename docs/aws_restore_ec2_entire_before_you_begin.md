---
title: "Before You Begin"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_restore_ec2_entire_before_you_begin.html"
last_updated: "3/25/2026"
product_version: ""
---

# Before You Begin


Before you restore EC2 instances, consider the following limitations:

* Veeam Data Cloud for AWS supports restoring EC2 instances only to the same AWS accounts to which the source instances belong.

* Veeam Data Cloud for AWS supports restoring EC2 instances from different types of restore points only to the original location.
* Veeam Data Cloud for AWS supports restoring EC2 instances from image-level backups only to the original location.
* If you restore multiple EC2 instances that have the same EBS volume attached, Veeam Data Cloud for AWS creates a separate volume for each instance and enables the Multi-Attach option for all volumes. After the restore operation completes, you can manually delete extra EBS volumes in the AWS Management Console and attach the necessary volume to the instances.

For more information on Amazon EBS Multi-Attach, see [AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volumes-multi.html).

* [Applies only if you plan to restore EC2 instances to a new location or with different settings] Veeam Data Cloud for AWS restores EC2 instances with a single network interface and assigns a new primary private IP address to each instance.
* [Applies only if you plan to restore EC2 instances to the original location] If [stop protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-stop-protection.html) or [termination protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination) is enabled on an EC2 instance, Veeam Data Cloud for AWS will not be able to restore the instance and will raise an error notifying that you must disable stop protection or termination protection on the source instance.
* [Applies only if you plan to restore EC2 instances to the original location] Veeam Data Cloud for AWS does not support restoring EC2 instances if the source instances with termination protection and stop protection enabled still exist in AWS.

* Veeam Data Cloud for AWS does not support restore of IPv6 addresses, tags of Elastic IP addresses or prefixes assigned to Amazon EC2 network interfaces attached to EC2 instances.

* [Applies only if you plan to restore EC2 instances to the original location] Veeam Data Cloud for AWS restores the instance and all network interfaces that were attached to the source EC2 instance. However, keep in mind the following:

* If the Elastic IP address that was assigned to the source EC2 instance is still assigned to this EC2 instance, the address will be reassigned to the restored instance.
* If the Elastic IP address is in use by any other EC2 instance, Veeam Data Cloud for AWS will raise a warning. If you decide to proceed with the restore operation, the address will not be associated with the restored instance. Note that Veeam Data Cloud for AWS will not allocate a new Elastic IP address to your AWS account.
* If the Elastic IP address that was assigned to the source EC2 instance has been removed from AWS, Veeam Data Cloud for AWS will attempt to restore this address using the native [AWS capabilities](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html#using-eip-recovering).
* If private IP addresses that were assigned to the source EC2 instance are in use by the source or any other EC2 instance, Veeam Data Cloud for AWS will raise a warning. If you decide to proceed with the restore operation, the restored EC2 instance will be assigned new private IP addresses.
* If the source instance still exists in AWS, Veeam Data Cloud for AWS will raise a warning. If you decide to proceed with the restore operation, the source EC2 instance, including all EBS volumes and all network interfaces attached to it, will be automatically deleted from AWS.

Note that EBS volumes excluded from the backup scope and volumes for which the DeleteOnTermination attribute is set to false will also be deleted from AWS.

