---
title: "Box"
slug: "data-access-governance-box"
updated: 2026-09-23T05:34:14Z
published: 2026-09-23T05:34:14Z
canonical: "helpcenter.securiti.ai/data-access-governance-box"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Box

This section describes the Data Access Governance features supported for Box and the steps to configure these functionalities.

#### Supported Data Access Governance Feature Sets

Following is the list of the features supported for Box:

### Access Intelligence

- Privilege Analysis - File level Permissions Granularity. Note that the Privilege Analysis is supported for Securiti for Box (Self-hosted) connectors.
- Activity Analysis - Not Supported

#### Access Control

- Not supported

#### Cross Border Transfer Policies

- Not Supported

> [!NOTE]
> Note
> 
> If Data Access Governance features for Box are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Example Supported Use Cases

The supported example use cases include:

#### Access Intelligence

- Identify and report on which Box users have access to files and what their permissions are on those Files.
- Identify and report on which Box groups have edit access to Files.
- Identify and report on which Box users have access to files containing sensitive data and what their permissions are on those Files.
- Identify and report on whether a User’s access to a particular File comes as a result of direct permissions assignment or through their group membership.

### Configuring Box Data Access Governance

This section describes the process for configuring the Box Data Access Governance feature set.

#### Configuring Access Intelligence Privilege Analysis using IAM Metadata Sources

To configure the privilege analysis for Box, there are some prerequisites

#### Prerequisites

To see the Box access intelligence data on the dashboard you must:

1. [Configure and activate the connector](/v1/docs/securiti-for-box-connector).
  - Access Intelligence supports customer self-hosted connectors.
2. [Perform discovery scan for your Databricks instance](/v1/docs/configure-discovery-scans-in-securiti-for-box).

#### Configuring your Box Access Scans for Access Intelligence

**1. Configure an IAM Metadata Source for Box**

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.

![Box_Metadata_Source.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-04d9a5ac-f829-78de-ac66-b829884b1913.png)
2. Click **IAM Metadata Sources**. This opens the IAM Metadata Sources page.
3. Near the upper right corner of the page, click **+New IAM Metadata Source**.
4. On the **New IAM Metadata Source** popup:
  1. Enter the **Connection Name**. For example, Metadata source for Box.
  2. Select **Box App Center** in **Source Type**.
  3. In the **Connection Information** area, provide following details:
    1. Select the Pod in the **Pod Name**.
    2. Provide the **Enterprise Id** of your Box account.
  4. Click Create **Authenticate & New IAM Metadata source**.

**2. Configure an Access Scan Definition for Box**

1. In Securiti, open **Data Access Governance**, then from the left menu bar choose **Settings>Access Scan Definitions**.
2. Near the upper right corner of the page, click **+ New Access Scan Definition**.
3. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select Box in **Data System** to scan for IAM related metadata.
  3. In the **IAM Metadata Sources**, select the metadata sources that you have created for a particular data system. If you have not configured a metadata source, then you must click **+ Add New** to add a metadata source.

![DAG_BOX_CN-ASD_link.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-00aa26a4-8782-9595-ddc8-5c0a4d0d03a4.png)
  4. In the **Associated Connectors** area, select the associated systems in the **Data Systems** for which access metadata is being scanned.
  5. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information weekly.
  6. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  7. Click **Add Definition**.

**3. Enable Access Intelligence Scans**

If you have not selected the Associated Connectors while configuring the Access Scan Definition, then you must:

- Enable the Access Intelligence Scan on the Securiti for Box Connector Page. Navigate to the **Permissions** tab of the Connector. Enable the Access Intelligence Scan button to link the ASD with the data system connector.

![ASD_for_box_linking.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2a89cc42-0d0d-be19-da11-b5705f66c5ee.png)

**4. Launching the Access Scan**

On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.

#### Configuring Access Intelligence Privilege Analysis without using IAM Metadata Sources

To configure the privilege analysis for Box, there are some prerequisites

#### Prerequisites

To see the Box access intelligence data on the dashboard you must:

1. [Configure and activate the connector](/v1/docs/securiti-for-box-connector).
  - Access Intelligence supports customer self-hosted connectors.
2. [Perform discovery scan for your Box instance](/v1/docs/configure-discovery-scans-in-securiti-for-box).
3. Enable the Access Intelligence Scan on the Securiti for Box Connector Page. Navigate to the **Permissions** tab of the Connector. Enable the Access Intelligence Scan button to link the ASD with the data system connector.

#### Configuring your Box Access Scans for Access Intelligence

To configure Access Intelligence Scans, you must:

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.
2. Click **Access Scan Definitions**. This opens the Access Scan Definitions (ASDs) page.
3. Near the upper right corner of the page, click **+ New Access Scan Definition**.
4. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select **Box** in the **Data System** menu. For more information about supported systems, see [Configuring Access Intelligence Scans without using IAM Metadata Sources](/v1/docs/configuring-access-intelligence-scans-without-using-iam-metadata-sources).
  3. In the **Source of Credentials and Connectivity for Access Intelligence Scans** area, you must select the **Data System Connector** tile.

![Box_Connector_as_MDS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-324a0cc3-cafa-4cc7-1365-c2137b3a9edb.png)
  4. In the **Data System Connector** menu, select the data system instance for which you must perform Access Scan.
  5. In the **Data Systems** menu, the instance you selected earlier in **Data System Connector** is selected by default.
  6. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information weekly.
  7. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  8. Click **Add Definition**.
5. On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.
6. Click the three dots option, and select the **Scan Now** option.

#### Using Access Intelligence with Box

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify access and risk in your Box tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identify and report on which Box users have access to files and what their permissions are on those Files. via Data Governance Command Grpah

To identify the users that have access to specific files:

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set **Entity** to **Files**. Set the **Attribute** to the **File Name**. Set the operator to the **Equals**.

![Box_Users_with_Permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-57f5ce9e-1ccb-4df4-13df-79f8daceb93f.png)
3. Select the **File** for which you want to identify the users that have access to the Site.
4. Click **Apply**.
5. Click on the **User Principal** node to see the users in the data grid.

![Box_Users_with_Access_to_Files_Permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5f02fd06-32c0-5bd3-d758-16944dd9d3b3.png)
6. Click on the **Policy Element** node to see the permissions.

#### Identify and report on which Box users have access to files containing sensitive data and what their permissions are on those Files via Data Command Graph

To identify the users that have access to Files containing sensitive data:

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set **Entity** to **Files**. Set the **Attribute** to the **Data System Type**. Set the operator to the **Equals**.

![Box_Access_to_Files_Containing_sensitive_data.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-10d83c7d-665f-6c2f-70ac-d6d3d68b95e4.png)
3. Select **Securiti for Box**.
4. Click **Apply**.
5. Add another Entity for Data Element. On the filter menu, set **Entity** to **Data Element**. Set the **Attribute** to the **Personal**. Set the operator to the **Equals**. Select **True**. Apply the filters.
6. Click on the **Files** node the list of Files in your Box tenant that contain sensitive data.
7. Click on the File for which want to see the permissions and user access. Click **Explore** button. You can see the sensitive data elements in the file.
8. Click on the **User Principal** node to see the users in the data grid.
9. Click on the **Policy Element** node to see the permissions.

#### Identify and Report Box Groups with Editor access to Box files

To identify the Groups with Access to a Table(s) containing sensitive data:

1. In Securiti, open **Data Access Governance** and choose **Access Graph Explorer** from the left menubar.
2. Navigate to the **Saved Views** panel on the left side of the page.
3. On the **Popular Views** tab, navigate to the **Box Queries** area. You can see the queries that help you perform privilege analysis for your Box instances.
4. Click on the query **Box groups with editor access to Box files**. Click on the User Group Principal node to see the users in the data grid.

![Box_Groups_Edit_Access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0174f939-d3c8-d6f6-c700-bba73515791c.png)

#### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).
