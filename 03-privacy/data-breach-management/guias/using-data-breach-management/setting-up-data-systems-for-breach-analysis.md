---
title: "Setting up data systems for Breach Analysis"
slug: "setting-up-data-systems-for-breach-analysis"
updated: 2025-12-08T08:20:47Z
published: 2025-12-08T08:20:47Z
canonical: "helpcenter.securiti.ai/setting-up-data-systems-for-breach-analysis"
area: privacy
modulo: data-breach-management
tipo: guia
data_captura: 2026-10-08
---

# Setting up data systems for Breach Analysis

Breach analysis refers to advanced analysis of the reported incident through the integration of real-time data intelligence and People Data Graph(PDG) technology. This helps you automate the breach management process. Admin users can enable this feature while setting up the necessary discovery scan jobs for Monitored data systems, ensuring comprehensive and proactive breach analysis.

![Breach_GS_Configuring_data_systems_drawio__1_.svg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-39a00e36-d027-5dbd-31ed-da476f441cf3.svg)

### Breach analysis for unstructured data systems

- For self-hosted unstructured data systems, you must set up at least one discovery scan job for the respective data system.
- While creating a discovery scan, you must enable the “Breach Analysis” option. For more information, see [Discovery scans for unstructured data systems](/v1/docs/discovery-scans).

![Screenshot_2024-10-04_at_6_09_31_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b3969232-9170-ddb1-e437-265306af2d38.png)
- For cloud unstructured data systems, you must initiate data scan. Further, in the **Permissions** tab of data system configurations, mark “Unique Identity Analysis for Breach” checkbox. For more information, refer to the [configuration of the respective data system](/v1/docs/configuring-connectors-for-monitored-data-systems).

![Screenshot_2024-10-05_at_1_20_48_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ee64606-13a6-4c5c-b4be-bfe068b0e95d.png)

### Breach analysis for structured data systems

- For self-hosted structured data systems, you must set up at least one discovery scan job for the respective data system.
- While creating a discovery scan, you must enable the “Breach Analysis” option. For more information, see [Discovery scans for unstructured data systems](/v1/docs/discovery-scans).

![Screenshot_2024-10-05_at_3_12_01_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6d596244-06b1-bd6e-6a81-6f58c1a5c7e6.png)

> [!NOTE]
> **Note**
> 
> Securiti does not support breach analysis for cloud-structured data systems, Unmonitored data systems, or hashed data.

After completing the discovery scan job, it typically takes some time for all assets (data systems) to link and appear in the assets list in the Data Breach Workbench, depending on the volume of data. Securiti audit logs show linking completion status. To open the audit logs:

- In Securiti, from the menu at the bottom of the dashboard, click **Settings > Security > Audit Logs.**

![Screenshot_2024-10-05_at_3_04_42_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3944a20c-c9a2-85a0-19da-d51cd02ac042.png)

### Configuring unmonitored data systems for manually processing reported breach

If Securiti doesn’t support connectors for some of your data systems being breached, you can create new or use existing unmonitored data systems in the Data Mapping module and process the breach flow. For this purpose, you must subscribe to the Data Mapping module. For more information, see [Creating and editing data assets](/v1/docs/creating-and-editing-data-assets).

![Screenshot_2024-10-04_at_6_23_18_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-27f8c378-36e7-6c00-e4f7-62a3cf9a3e08.png)

Once you configure the required data systems, these assets will appear in the **Asset(s) Details** list in **Data Breach Workbench**.You can choose which data systems to include or exclude in the data breach processing.

![Screenshot_2024-10-13_at_12_32_42_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ec2b050-f08d-f1bf-9ed2-f095fe5f1f54.png)

A **People Data Graph** (PDG) is a comprehensive representation of individuals and their associated personal information across various structured and unstructured systems. This interconnected graph serves as a visual and relational map, linking individuals to their residences, contact information, and other relevant personal data stored in connected data systems. The PDG technology aims to organize and present this information in an intuitive manner.

A type of data system that you can connect via Securiti to perform discovery scans on data for enhanced breach analysis.

Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert incident owners to actively check them for unauthorized data access when a data breach incident is reported.
