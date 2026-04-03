---
title: "How to Configure Endpoints in AWS"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/aws_configure_endpoints.html"
last_updated: "3/30/2026"
product_version: ""
---

# How to Configure Endpoints in AWS


If your Microsoft SQL Server and PostgreSQL DB instances operate in private environments (that is, connected to subnets with auto-assignment of public IPv4 addresses disabled), configure the following endpoints for services used by Veeam Data Cloud for AWS to perform backup and restore operations.

How to Configure Endpoints in AWS

| Operation | Interface Endpoints | S3 Gateway Endpoints |
| Creating RDS image-level backups | * com.amazonaws.<region>.ssmmessages * com.amazonaws.<region>.ssm * com.amazonaws.<region>.sqs | * com.amazonaws.<region>.s3 |
| Performing health check for RDS backups | * com.amazonaws.<region>.ssmmessages * com.amazonaws.<region>.ssm * com.amazonaws.<region>.sqs | * com.amazonaws.<region>.s3 |
| Restoring Microsoft SQL Server and PostgreSQL DB instances from image-level backups | * com.amazonaws.<region>.ssmmessages * com.amazonaws.<region>.ssm * com.amazonaws.<region>.sqs | * com.amazonaws.<region>.s3 |

To create these endpoints, use the specified endpoint names, where <region> is the name of an AWS Region in which Microsoft SQL Server or PostgreSQL DB instances reside.

Creating Interface Endpoints

|  |
| --- |
| Note |
| This section provides instructions on steps performed in a third-party application. Keep in mind that the instructions may become outdated. For up-to-date instructions, see AWS Documentation. |

To allow Veeam Data Cloud for AWS to create RDS image-level backups and to perform restore operations from these backups, configure interface VPC endpoints in AWS Regions where Microsoft SQL Server or PostgreSQL DB instances reside.

To create an interface VPC endpoint, do the following:

1. Log in to the AWS Management Console using credentials of an AWS account in which you want to create the endpoint.
2. In the AWS services section, navigate to All Services > Networking & Content Delivery and click VPC. The VPC console will open.
3. Navigate to Virtual Private Cloud > Endpoints and click Create Endpoint. The Create endpoint wizard will open.
4. Complete the Create endpoint wizard:

1. At the Endpoint settings step of the wizard, do the following:

1. [Optional] In the Name tag field, specify a name for the endpoint.
2. In the Service category section, select AWS services.

1. At the Services step of the wizard, use the following filter Type: Interface and select a service for which you want to create a VPC endpoint.
2. At the VPC step of the wizard, do the following:

1. From the VPC drop-down list, select a VPC that Veeam Data Cloud for AWS will use for network connectivity.
2. In the Additional settings section, select the Enable DNS name check box.

1. At the Subnets step of the wizard, select one subnet for each Availability Zone to be used by Veeam Data Cloud for AWS.
2. At the Security groups step of the wizard, select security groups that will be associated with the endpoint network interfaces.

Ensure that the security group that is associated with the endpoint network interface allows communication between the endpoint network interface and the resources in your VPC that communicate with the service. If the security group restricts inbound HTTPS traffic (port 443) from resources in the VPC, you will not be able to send traffic through the endpoint network interface.

1. At the Policy step of the wizard, select Full access to allow full access to the service. Alternatively, select Custom and attach a VPC endpoint policy that will control permissions on resources available over the VPC endpoint.
2. Click Create Endpoint.

For more information on interface VPC endpoints, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/privatelink/create-interface-endpoint.html?ad=in-text-link#create-interface-endpoint).

Creating S3 Gateway Endpoints

|  |
| --- |
| Note |
| This section provides instructions on steps performed in a third-party application. Keep in mind that the instructions may become outdated. For up-to-date instructions, see AWS Documentation. |

To allow Veeam Data Cloud for AWS to create RDS image-level backups and to perform restore operations from these backups, configure S3 gateway endpoints in AWS Regions where Microsoft SQL Server or PostgreSQL DB instances reside.

To create a gateway endpoint for a subnet, do the following:

1. Log in to the AWS Management Console using credentials of an AWS account in which you want to create the endpoint.
2. In the AWS services section, navigate to All Services > Networking & Content Delivery and click VPC. The VPC console will open.
3. Navigate to Virtual Private Cloud > Endpoints and click Create Endpoint. The Create endpoint wizard will open.
4. Complete the Create endpoint wizard:

1. At the Endpoint settings step of the wizard, do the following:

1. [Optional] In the Name tag field, specify a name for the endpoint.
2. In the Service category section, select AWS services.

1. At the Services step of the wizard, use the following filter Type: Gateway and select com.amazonaws.<region>.s3, where <region> is a name of an AWS Region in which Microsoft SQL Server or PostgreSQL DB instances reside.
2. At the VPC step of the wizard, select a VPC that Veeam Data Cloud for AWS will use for network connectivity.
3. At the Route tables step of the wizard, select the route tables to be used by the endpoint. AWS will automatically add a route that points traffic destined for the service to the endpoint network interface.
4. At the Policy step of the wizard, select Full access to allow full access to the service. Alternatively, select Custom and attach a VPC endpoint policy that will control permissions on resources available over the endpoint.
5. Click Create Endpoint.

For more information on gateway endpoints for Amazon S3, see [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html).

