---
title: "Acquire credentials in Databricks using username and password"
slug: "acquire-credentials-in-databricks-using-username-and-password"
updated: 2026-07-21T05:30:19Z
published: 2026-07-21T05:30:19Z
canonical: "helpcenter.securiti.ai/acquire-credentials-in-databricks-using-username-and-password"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire credentials in Databricks using username and password

> [!NOTE]
> **Note**
> 
> We assume you have access to a running Databricks instance or you're an admin before proceeding with the connector activation.

1. Log in to Databricks.
2. Record the following parameters for later use:
  - **Host** - Database URL linked to your server.
  - **Port** - Port address of the server; default is 443.
  - **HTTP Path** - The compute cluster address path you need to connect with.
3. To obtain the Hostname, Port, and HTTP Path:
  1. On the Databricks server portal, in the left sidebar, select **Compute > <*your machine name*>**.

![compute_machine.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2a0daccb-4e7d-9b3f-9316-163971405d3b.png)
  2. On the **Configuration** tab of your compute machine, near the bottom of the page, expand the **Advanced Settings** section.
  3. In the **JDBC/ODBC** tab, record the Host, Port, and HTTP Path parameters for later use.

![HTTP_path.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0a14988d-c8e4-a266-2be6-56f0aa5f843f.png)
4. Proceed to [Connecting Databricks with Securiti](/latest/docs/new-ui-connecting-databricks-with-securiti).
