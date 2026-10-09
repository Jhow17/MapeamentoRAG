---
title: "Access Scan Definitions using IAM Metadata Source"
slug: "access-intelligence-scans-using-access-scan-definitions-and-iam-metadata-sources"
updated: 2026-04-06T10:33:13Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/access-intelligence-scans-using-access-scan-definitions-and-iam-metadata-sources"
stale: true
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Access Scan Definitions using IAM Metadata Source

This section describes the configuration of the Access Intelligence Scans using the Access Scan Definitions and IAM Metadata Sources.

## IAM Metadata Sources

IAM Metadata Sources are the connections to the sources of IAM and RBAC metadata associated with a data system. An IAM metadata source provides authentication and connectivity to your data systems and policy or identity metadata systems like Apache Ranger in order to enable Access Intelligence to determine who has access to what data and how that access is created.

## Configuring Access Intelligence Scans for your data systems

This topic describes the prerequisites and steps to configure access intelligence scans for your data systems.

### Prerequisites

- You must have an active Data System Connector connected to your desired data system.
- You must complete a Discovery Scan of your data system. Access Intelligence will only build permissions relationships to data resources (Files, Databases, Tables, etc.) that you have scanned into the Securiti Platform.

### Configuration

Following are the configuration steps:

**1. Configure an IAM Metadata Source for your data system**

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(24).png)
2. Click **IAM Metadata Sources**. This opens the IAM Metadata Sources page.
3. Near the upper right corner of the page, click **+New IAM Metadata Source**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(40).png)
4. On the **New IAM Metadata Source** popup:
  1. Enter the **Connection Name**. For example, SharePoint Metadata Source.
  2. Select the Data System in **Source Type** for which you want to configure an IAM Metadata Source. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(27).png)
    1. If you want to create a metadata source for SharePoint (Self-Hosted), select **S****harePoint OnPrem**. Note that for SharePoint Onprem you must have a pod configured, before creating the metadata source. For more details on configuring the metadata source for SharePoint, see the [SharePoint Access Intelligence documentation](/v1/docs/microsoft-365-sharepoint-online).
    2. If you have selected Apache Ranger in Source Type, then you must provide following parameters:

| Setting | Description |
| --- | --- |
| Connection Name | Name of the connection |
| Source Type | Type of the source. By default, Apache Ranger is selected. |
| Apache Ranger Service Name | Apache Ranger Service Name. This is the Service Name of the configured Apache Ranger Service which controls the Starburst cluster. Securiti will download metadata from this service instance after connecting to the Ranger server. For instance, if the cluster is controlled by a 'STARBURST-ENTERPRISE' type service named 'starburst-enterprise-1', then enter starburst-enterprise-1. |
| URL | URL to Ranger Admin. For example, http://111.111.222.33 |
| Connection Time Out | Connection timeout in milliseconds |
| Authentication Type | Type of authentication necessary to connect to the Ranger Admin REST API endpoint. |
| Disable TLS verification | Mark this checkbox to disable TLS verification. Disabling TLS verification check enables you to reduce the strictness of the validation procedures applied when setting up an SSL/TLS connection. Note that this option should be used only in controlled environments when connecting to a trusted Ranger server. Turning off Transport Layer Security (TLS) verification doesn't impact the encryption of the session. |
| Username | Username of a Ranger account. The user must have authorization to connect to the Ranger Admin REST API endpoint. |
| Password | Password of Ranger account |
  3. If you have selected **Snowflake Cloud** as a **Source Type**, then you must provide the **Account ID** of your Snowflake account and **Warehouse** to query for metadata. For more details on configuring the metadata source for Snowflaket, see the [Snowflake Access Intelligence documentation](/v1/docs/data-access-governance-snowflake#access-intelligence).
  4. If you have selected **Starburst Activity Data - Web Integration UI** as a **Source Type**, then you must provide the Pod Name, URL, and Connection timeout etc. For more details on configuring the metadata source for Starburst Activity Data, see the Activity Analysis documentation.
  5. If you have selected the **Databricks Onprem**, then you must provide the Pod Name, Driver Path, Host, Port, etc. Note that for Databricks Onprem you must have a pod configured, before creating the metadata source. For more details on configuring the metadata source for Databricks Onprem, see the [Databricks Access Intelligence documentation](/v1/docs/databricks#access-intelligence1).
  6. In the **Authentication Details** area, select the **Authentication Type**, based on the source and authentication type selected, enter details. For more information, see data system specific access intelligence documentation. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(19).png)
  7. Click **Authenticate and Create** **New IAM Metadata source**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 4(11).png)

**2. Configure an Access Scan Definition for your data system**

1. In Securiti, open **Data Access Governance**, then from the left menu bar choose **Settings>Access Scan Definitions**.
2. Near the upper right corner of the page, click **+ New Access Scan Definition**.
3. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select the **Data System** that you must scan for IAM related metadata.
  3. If you have selected any of the below mentioned Data System, then you must specify the Account ID in the **Account**.
    - Microsoft SharePoint Online
    - Microsoft SharePoint Online OnPrem
    - Snowflake
  4. If you have selected **Databricks** or **Starburst**, then you must specify the **Host** and **Port**.
  5. In the **IAM Metadata Sources**, select the metadata sources that you have created for a particular data system. If you have not configured a metadata source, then you must click **+ Add New** to add a metadata source.
  6. In the **Associated Connectors** area, select the associated systems in the **Data Systems** for which access metadata is being scanned.

![Connector_ASD_linking.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2cfdbbdd-6e01-da12-e990-e295308b7f32.png)
  7. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information daily.
  8. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  9. Click **Add Definition**.

**3. Enable the Access Intelligence Scan**

If you have not selected the Associated Connectors while configuring the Access Scan Definition, then you must:

- On the Data System Connector move to the required Data System and navigate **Permissions** tab of the Connector. Enable the Access Intelligence by linking the Access Scan Definition.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 8.png)

**4. Launching the Access Scan**

1. On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 7.png)
2. Click the three dots option, and select the **Scan Now** option.

### Filtering the Access Scan Definitions

The Access Scan Definitions page shows you the list of the access scan definitions that you configured. It shows you the Configuration status of the access scan, whether it is active or inactive as well as the Operational Status of the access scan. The Config Status column shows both the Operational Status, Config Status, and the Last Scan Status, once you hover the cursor over the icon adjacent to the Config Status value.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 9(1).png)You can use the filter panel on the top right side of the page to filter out the relevant access scan definitions.

You can include or exclude the relevant filters from the following items of the filter panel to view the relevant access scan definitions:

- Name
- Config Status
- Data system
- Active
- IAM Metadata Sources
- Connectors

Expand one or more areas on the filter panel and use the tools there to choose or enter criteria on which to filter the access scan definitions.

Near the bottom of the filter panel, click Apply to apply your filters to the access scan definitions, eliminating those items or elements that do not meet the criteria.

Securiti recommends using the **Refresh** button near the top right side of the page to view the latest states of your Access Scan Definitions.

### Access Scan Definition (ASD) States

Access Scan Definitions can have following three states:

- Configuration State (Config State) - it lets you track the level of completeness of ASD related configurations.
- Operational State (Operational Status) - it lets you identify the current operational state of ASD.
- Last Scan Status - it shows the last scan operation performed.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 9(2).png)

#### Configuration States

The Config Status column on the ASD page shows the following Statuses:

- **Metadata Sources Config Incomplete** - This indicates that metadata source configuration is not complete. This is the Initial state when an ASD is created. The Metadata Sources Config incomplete state could be due to the Metadata source configuration validation failure.
- **Connector Config Incomplete** - This indicates that Metadata sources are successfully configured, however the relevant connector was not linked to the ASD. Note that at you must link least one connector to ASD.
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

#### Resetting the Access Scan Definition

To delete the graph data relevant to your access scan definition:

1. In Securiti, open **Data Access Governance**, then from the left menu bar choose **Settings>Access Scan Definitions**.
2. For the relevant, access scan definition, click three dots. Click the **Reset** option.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 10.png)
3. The Active/Inactive toggle gets disabled. The ASD retains the current active or inactive state and will start purging for graph data. The Status of the access scan would be changed temporarily to **Deletion in progress**. Once the deletion is complete, the state of the access scan definition would be set to active, and the last status of the access scan definition would be restored.
4. You can launch the access scan again if required.

### Access Scan Definition for multiple organizations

You can use access intelligence and perform privilege analysis across multiple organizations within your Securiti tenant to visualize and manage IAM related information specific to these organizations. These organizations can be created based on the departments or business units within your company. The access intelligence configurations can be enabled for particular data systems within an organization and an Access Scan Definition can be linked to that data system. The same Access Scan Definition can be linked with the same data systems in another organization.

To visualize the IAM related data within multiple organizations, there are two types of nodes that you should consider:

- Resource Sensitive IAM Nodes
- Resource Agnostic IAM Nodes

Resource Sensitive Nodes are the IAM nodes that are associated with the data sources. These include:

- Identity Source
- Role
- User Principal
- User Group Principal
- Service Principal

The resource sensitive IAM nodes will show data and the details if:

- An IAM metadata source for a particular data system/ provider account was created in an organization.
- An Access Scan Definition utilizing the defined IAM metadata sources was created in that organization.
- The Access Scan Definition was successfully linked to the particular data system connector in that organization.
- The Status of the Access Scan was Successful.
- The nodes link to data resources that belong to that organization, and are identified during the discovery and access scan definition execution.

The resource agnostic IAM nodes will show data and details if:

- An IAM metadata source for a particular data system account was created in an organization.
- An Access Scan Definition utilizing the defined IAM metadata sources was created in that organization.
- The Access Scan Definition was successfully linked to the particular data system connector in that organization.

The IAM nodes will show the data specific to the particular organization, while the nodes that are associated with the data resources will show the data related to multiple organizations.

#### Example

To understand the multi-org related changes on the data displayed for various nodes, for example, consider this scenario, If you have activated the Snowflake connector in Organization **Finance** within your tenant and created an IAM Metadata source and configured an Access Scan Definition. Now you have activated the Snowflake connector in Organization **Human Resources** and created an IAM Metadata source. The Access Scan Definition you configured could be linked to the Snowflake Connectors in both the organizations. Upon successful completion of the discovery as well as the access scan definition, the Database **Salaries** was discovered along with the IAM related metadata in Organization **Finance** and **Employees** Database was discovered in Organization **Human Resources**. Now:

- The users in the Organization **Human Resources** would be able to see the policy nodes linked to the **Employees Only**.
- The users in the Organization **Finance** would be able to see the policy nodes linked to the **Salaries** Only.
- The users in both Organizations will be able to see the Snowflake users and Snowflake roles in their organizations.

### Migration from Access Scans to Access Scan Definitions

Securiti will migrate the existing access scan based configurations for your data systems to the new process automatically. If you have:

- Data system connectors configured for existing Access Scans on your tenant, Securiti will automatically create equivalent IAM Metadata sources for those systems.
- Existing Access scans on your tenant, Securiti will auto-generate names and other details to covert them into valid Access Scan Definitions.
- Securiti will automatically link the data system connectors to the relevant access scan definitions.

These migrated Access Scan Definitions will be evaluated to see if the configuration details are complete and are valid for data-systems, before setting their state to **Active**. If configuration is invalid, or there are no data-systems, these Access Scan Definitions’s will have a **config-incomplete** or **inactive** state.

The access scan logs after the migration will be available in the relevant auto generated access scan definition.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 12.png)

> [!NOTE]
> Note
> 
> For Snowflake, IAM Metadata sources created via migration, you have to update the IAM Metadata source to provide the oAuth credentials (Client ID and Secret) with Metadata Source redirect URI.
