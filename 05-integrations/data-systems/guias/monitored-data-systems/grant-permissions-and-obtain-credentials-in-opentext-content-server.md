---
title: "Grant permissions and obtain credentials in OpenText Content Server"
slug: "grant-permissions-and-obtain-credentials-in-opentext-content-server"
updated: 2026-07-31T07:40:08Z
published: 2026-07-31T07:40:08Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-opentext-content-server"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in OpenText Content Server

OpenText Content Server data systems require minimum Permissions and Activation parameters for successful Connector Authentication in Securiti.

> [!NOTE]
> **Note**
> 
> We recommend that you either have an OpenText Content Server Instance up and running, or you have administrative access to obtain the necessary *read* Permissions for the files needed to create user Credentials to activate the Connector.

## Prerequisites for OpenText Content Server connector activation

- The search engines must be in running state. For more information on viewing status for **Enterprise Search Manager** and **Enterprise Search Federator**, see [Troubleshooting](/latest/docs/opentext-content-server-connectors-troubleshooting).

#### Obtaining credentials in OpenText Content Server

1. Record the following for later use.
  - Content Server URL
  - Username
  - Password
2. Navigate to **Enterprise > User > Groups > Search User > Edit** and add the following Permissions to run the Discovery scan for your OpenText Content Server Data system successfully.

![otcs_ediscoverypermission_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-11c3468e-fe85-a7e0-8445-5e9b6cf13b65.png)

![Permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-56c1ee14-5744-bbff-a051-1c1e7d6a743b.png)
  - **eDiscovery Rights**
  - **System administration rights**
3. Proceed to [Connect OpenText Content Server connector with Securiti](/latest/docs/connecting-opentext-content-server-connector-with-securiti).
