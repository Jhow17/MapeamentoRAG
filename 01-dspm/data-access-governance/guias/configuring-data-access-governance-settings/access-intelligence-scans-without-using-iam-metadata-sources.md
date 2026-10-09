---
title: "Access Scan Definitions without using IAM Metadata Sources"
slug: "access-intelligence-scans-without-using-iam-metadata-sources"
updated: 2026-04-06T10:39:54Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/access-intelligence-scans-without-using-iam-metadata-sources"
stale: true
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Access Scan Definitions without using IAM Metadata Sources

This section describes the configuration of the Access Intelligence Scans without using the IAM Metadata Sources. Securiti can use connectors as the source of credentials and connections to data systems for Access Scan Definitions (ASDs).

Access Scan Definitions allow you to configure Data Access Intelligence Scans of your data systems enabling the gathering of Identity and Access Management (IAM) and Role Based Access Control (RBAC) metadata from your data system or Identity Provider.

Following are the supported data systems for which you can create Access Scan Definitions without using IAM MetaData Sources.

| Data System | Authentication Method |
| --- | --- |
| Snowflake (Securiti Cloud Connector) | Oauth 2.0 - using Client ID and Secret based authentication |
| SharePoint (Self-Hosted Connector) | Oauth 2.0 - using Client ID and Secret, + Certificate based authentication |
| Dropbox (Self-Hosted Connector) | Oauth 2.0 - using Client ID and Secret based authentication |
| OneDrive (Self-Hosted Connector) | Oauth 2.0 - using Client ID and Secret based authentication |
| Securiti for Box (Self-Hosted Connector) | Oauth 2.0 - using Enterprise ID |

## Configuring Access Intelligence Scans for your data systems

This topic describes the prerequisites and steps to configure access intelligence scans for your data systems.

### Prerequisites

- You must have an active Data System Connector connected to your desired data system
- You must complete a Discovery Scan of your data system. Access Intelligence will only build permissions relationships to data resources (Files, Databases, Tables, etc.) that you have scanned into the Securiti Platform

OR
- Perform Data Inventory Sync
- On the Data System Connector move to the required Data System and navigate **Permissions** tab of the Connector. Enable the Access Intelligence by linking the Access Scan Definition.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 8.png)

### Configuration

To configure Access Intelligence Scans, you must:

1. In Securiti, open **Data Access Governance,** from the left menu bar, Navigate to **Settings**.
2. Click **Access Scan Definitions**. This opens the Access Scan Definitions (ASDs) page. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(25).png)
3. Near the upper right corner of the page, click **+ New Access Scan Definition**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 5(7).png)
4. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select the **Data System** that you must scan for IAM related metadata. Please refer to the table above to see the supported systems for which you can configured ASDs without Metadata sources
  3. If you have selected any of the below mentioned Data System, then you must specify the ID in the **Account**.

Securiti will provide the list of all the relevant instances of the selected data systems configured using the provided Account ID in the **Data System Connector** menu.
    - Microsoft SharePoint Online OnPrem - Sharepoint Tenant ID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx
    - Snowflake (Securiti Cloud Connector) - account name for the Snowflake cloud account ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 6(8).png)
  4. In the **Source of Credentials and Connectivity for Access Intelligence Scans** area, you must select the **Data System Connector** tile.

![DAG_Connector_as_MDS_ASD.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b3c56dba-3bfe-1031-2e93-6ca917a8fb4a.png)
  5. In the **Data System Connector** menu, select the data system instance for which you must perform Access Scan.
  6. In the **Data Systems** menu, the instance you selected earlier in **Data System Connector** is selected by default. You can also select other instances related to provided Account ID if required.
  7. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information weekly. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 7(6).png)
  8. Mark the **Activity Analysis** checkbox if you want to see the user activity related data for selected data system. Note that the **Activity Analysis** is supported for SharePoint and Starburst, the option will be displayed only if you select SharePoint or Starburst in the **Data System** menu. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 8(4).png)
  9. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  10. Click **Add Definition**.
5. On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.
6. Click the three dots option, and select the **Scan Now** option. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 9(6).png)

### Filtering the Access Scan Definitions

The Access Scan Definitions page shows you the list of the access scan definitions that you configured. It shows you the Configuration status of the access scan, whether it is active or inactive as well as the Operational Status of the access scan. The Config Status column shows both the Operational Status, Config Status, and the Last Scan Status, once you hover the cursor over the icon adjacent to the Config Status value.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 10(2).png)

You can use the Column Selector on the right side to filter out the relevant access scan definitions. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 11.png)

You can include or exclude the relevant filters from the following items of the filter panel to view the relevant access scan definitions:

- Name
- Config Status
- Data system
- Active
- IAM Metadata Sources
- Connectors ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 12(2).png)

Expand one or more areas on the filter panel and use the tools there to choose or enter criteria on which to filter the access scan definitions.

Near the bottom of the filter panel, click Apply to apply your filters to the access scan definitions, eliminating those items or elements that do not meet the criteria. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 13(1).png)

Securiti recommends using the **Refresh** button near the top right side of the page to view the latest states of your Access Scan Definitions.

### Access Scan Definition (ASD) States

Access Scan Definitions can have following three states:

- Configuration State (Config State) - it lets you track the level of completeness of ASD related configurations.
- Operational State (Operational Status) - it lets you identify the current operational state of ASD.
- Last Scan Status - it shows the last scan operation performed.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 14(1).png)

#### Configuration States

The Config Status column on the ASD page shows the following Statuses:

- **Metadata Sources Config Incomplete** - This indicates that metadata source configuration is not complete. This is the Initial state when an ASD is created. The Metadata Sources Config incomplete state could be due to the Metadata source configuration validation failure. The Metadata Sources Config incomplete state could be due to the Metadata source configuration validation failure or if MdS is deleted.
- **Connector Config Incomplete** - This indicates that Metadata sources are successfully configured, however the relevant connector was not linked to the ASD. Note that you must link at least one connector to ASD.
- **Config Complete** - This indicates that All required configurations are complete. Both metadata sources and connectors are successfully configured. ASD is ready for activation.

#### Operational States

ASDs could have one of the following Operational States:

| ASD Operational State | Description |
| --- | --- |
| No Operation (Idle) ("-") | ASD is not performing any operation. |
| Scan Scheduled | Access scan is initiated, Pre-collection transitions to Batch Collection Scheduling. |
| Scan In Progress | Access scan batch is actively running. |
| Deletion In Progress | ASD deletion is initiated, and Purger is removing all associated data |
| Reset In Progress | Purging is in progress, graph data is being deleted. ASD Configuration remains intact |
| Deletion Ready | If purging was initiated, but was not successful, then you can only delete the ASD. |
| Reset Ready | Reset operation failed. ASD can now only be reset or deleted. |

#### Last Scan Status

ASDs could have one of the following Last Scan Statuses:

- Successful - The Scan was successfully executed
- Error - An error occurred during the execution of the scan
- Config Incomplete - Incomplete configuration

### Resetting the Access Scan Definition

To delete the graph data relevant to your access scan definition:

1. In Securiti, open **Data Access Governance**, then from the left menu bar choose **Settings>Access Scan Definitions**.
2. For the relevant, access scan definition, click three dots. Click the **Reset** option.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 15(1).png)
3. The Active/Inactive toggle gets disabled. The ASD retains the current active or inactive state and will start purging for graph data. The Status of the access scan would be changed temporarily to **Deletion in progress**. Once the deletion is complete, the state of the access scan definition would be set to active, and the last status of the access scan definition would be restored.
4. You can launch the access scan again if required.
