---
title: "Creating Private Endpoints"
product: "vdc"
doc_type: "provider"
source_url: "https://helpcenter.veeam.com/docs/vdc/provider/vault_private_endpoints_creation.html"
last_updated: "3/18/2026"
product_version: ""
---

# Creating Private Endpoints


Veeam Data Cloud Vault supports secure access to storage resources through Azure storage private endpoints. This configuration allows connections to a specific storage vault over an internal network of Microsoft Azure with private IP addresses. As a result, data traffic remains within the private network and does not use the internet.

Before creating a private endpoint connection, [check prerequisites](vault_private_endpoints_creation_before.md). Then use the Create Private Endpoint wizard to configure the private endpoint connection.

1. [Launch the Create Private Endpoint wizard](vault_private_endpoints_creation_launch.md).
2. [Copy the resource ID](vault_private_endpoints_creation_resource_id.md).
3. [Create a private endpoint resource](vault_private_endpoints_creation_endpoint.md).
4. [Validate the private endpoint connection](vault_private_endpoints_creation_connection.md).
5. [Finalize the private endpoint setup](vault_private_endpoints_creation_setup.md).

