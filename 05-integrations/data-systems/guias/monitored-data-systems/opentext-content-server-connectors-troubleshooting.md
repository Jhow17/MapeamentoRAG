---
title: "Troubleshooting"
slug: "opentext-content-server-connectors-troubleshooting"
updated: 2025-10-31T07:20:42Z
published: 2025-11-03T07:45:20Z
canonical: "helpcenter.securiti.ai/opentext-content-server-connectors-troubleshooting"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting

In case you face the below errors:

- "Error applying query on Enterprise: Error applying query on Enterprise Search Manager: Failed to connect to Search Federator”
- Query has expired the time to live.

You might need to resume or start the below services. Wait a few minutes for changes to take effect:

- Enterprise Search Manager
- Enterprise Data Flow Manager

![otcs_newss_troubleshooting1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f64e8d7e-562f-1070-a856-526de1a03f3c.png)![otcs_newss_troubleshooting2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5d0dae58-29f2-7091-43fa-ef754cc05e77.png)

Follow the procedure below in your OpenText Content Server app to verify that the changes have been enabled.

> [!NOTE]
> **Note**
> 
> Once the search and index engines are up and running, you can verify if the search engines are working from the OpenText portal as well.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(647).png)

1. Expand **Enterprise Search Manager** to make sure that the **Enterprise Search Federator** exists and is enabled.

![otcs_engineverification_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aca54aba-fa20-e045-9ac0-904f43b37ab5.png)
2. Go to **Enterprise Search Manager > Select Search Federator** to verify that **Search Federator Engine** has started successfully. Wait till the status changes to "Running" state.

![otcs_engine_verification2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8356cab9-4f61-06cd-7fec-f1ea3f194a10.png)

![otcs_newss_runningstate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-96e08917-e621-4360-45b1-1c3aaa824af1.png)
3. Go to **Enterprise Data Flow Manager > Enterprise Update Distributor > Index Engines (Tab)** to verify that **Enterprise Data Flow Manager** has started without any issues.

![otcs_newss_flowmanager.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8646e1d8-d9e8-9889-5439-19ac379f5a11.png)

![otcs_newss_distributor.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d01ba895-e173-cff0-9a82-dfdf1c91382c.png)
4. Select **Index Engines** tab and verify that all the engines are in "Running" state.

![otcs_engineverification_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-838bdd52-b8c0-7851-31ef-77cf71ca7439.png)
