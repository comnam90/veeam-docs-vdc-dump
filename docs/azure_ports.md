---
title: "Ports"
product: "vdc"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/vdc/userguide/azure_ports.html"
last_updated: "5/19/2026"
product_version: ""
---

# Ports


Veeam Data Cloud for Microsoft Azure connects to your Microsoft Azure subscription to back up and restore Azure resources. The ports listed in the following table must be open in your network security groups (NSGs), Azure Firewall and resource-level firewalls.

|  |
| --- |
| tip |
| To allow access to an Azure service, you can use the IP address, DNS name or virtual network service tag of the service. If you want to use an IP address, you can download a JSON file with the full list of Azure IP ranges and service tags from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/confirmation.aspx?id=56519). |

Ports

| From | To | Protocol | Port | Description |
| Azure VMs | Azure Storage service (service tag: Storage) | TCP/HTTPS | 443 | [Applies to Windows-based Azure VMs only] Required for VSS application-aware processing during backup, and for File-Level Recovery (FLR) write-back during restore. |
| Any IPv4 address (0.0.0.0/0) | Azure SQL Managed Instances (DNS name or IP address) | TCP | 3342 | Required to connect to Azure SQL Managed Instances using public endpoints. The managed instance NSG must permit inbound TCP 3342 from the Internet service tag. |

Connectivity to Azure SQL Servers and to Azure SQL Managed Instances using private endpoints does not require additional NSG port rules. Access is governed by the SQL Server's network access settings (Public network access and Allow Azure services and resources to access this server) or by the private endpoint configuration. For details, see [Considerations and Limitations](azure_limitations.md).

