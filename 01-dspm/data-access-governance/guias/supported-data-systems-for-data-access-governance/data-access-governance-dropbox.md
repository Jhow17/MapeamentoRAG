---
title: "Dropbox"
slug: "data-access-governance-dropbox"
updated: 2025-11-03T07:19:25Z
published: 2025-11-03T07:19:25Z
canonical: "helpcenter.securiti.ai/data-access-governance-dropbox"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Dropbox

This section describes the Data Access Governance features supported for Dropbox and the steps to configure these functionalities.

#### Supported Data Access Governance Feature Sets

Following is the list of the features supported for Dropbox:

### Access Intelligence

- Privilege Analysis
  - File level permissions granularity
- Activity Analysis - Not Supported

#### Access Control

- Not Supported

#### Cross Border Transfer Policies

- Not Supported

### Example Supported Use Cases

The supported example use cases include:

#### Access Intelligence

- Identify and report on which Dropbox users have access to Files and what their permissions are on those Files
- Identify and report on which Dropbox users have access to Files containing sensitive data and what their permissions are on those Files
- Identify and report on External users that access to Files
- Identify and report on Groups that have access to Files

### Configuring Dropbox Data Access Governance

This section describes the configuration process of Data Access Governance features for Dropbox

### Configuring Access Intelligence Privilege Analysis using IAM Metadata Sources

To see the Dropbox Access Intelligence information you must:

#### Prerequisites

To see the Dropbox Access Intelligence information you must:

1. [Set up a Securiti pod or elastic pod.](/v1/docs/securiti-pods-and-elastic-pods)
2. [Configure and activate the connector](/v1/docs/activate-the-dropbox-connector-in-securiti). Note that the account you use to configure and activate the connector must have the **Team Admin** role assigned.
3. Perform a discovery scan on your Dropbox instance.
4. Login to Dropbox app console. Click **Create app** button.

![Create_app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7e14a924-7c74-1368-bc23-0a6f6db2564e.png)
  1. In the **Choose an API** area, select **Scoped access** option.
  2. In the **Choose the type of access you need** section, select **Full Dropbox - Access to all files and folders in a user's Dropbox**.

![Dropbox_API.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1b6558cb-45bb-6d8c-0e45-ea4bb59f8cb4.png)
  3. Provide the **Name** of your application.
  4. Click **Create app** button.
  5. In the **Settings** tab, copy the **App Key** and **App Secret** for later use while creating the IAM Metadata Source.

![O_auth_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8b6abb18-b71b-05d2-588f-b3efd796e2ca.png)
  6. In the OAuth 2 section, in the **Redirect URIs**, add **https://app.securiti.ai/static/activateMetadataSource.html** and **https://app.securiti.ai/static/activateConnector.html**. The redirect URl will change depending on where your Securiti tenant has hosted. Various endpoints have been listed below:

| Cloud Instance | URl |
| --- | --- |
| U.S. Cloud | app.securiti.ai |
| EU Cloud | app.eu.securiti.ai |
| U.S. GCP Cloud | app1.securiti.ai |
| Indonesia Cloud | app2.securiti.ai |
| Canada Cloud | app3.securiti.ai |
| Australia Cloud | app4.securiti.ai |
| UAE Cloud | app5.securiti.ai |
| Mumbai Cloud | app6.securiti.ai |
  7. In the **Permissions** tab, under the **Individual Scopes** area, you must select following scopes:
    - members.read
    - groups.read
    - team_data.member
    - team_data.content.read
    - files.metadata.read
    - sharing.read
    - team_info.read
  8. Click **Submit** button once you have finalized the scopes.

#### Configuring your Dropbox Access Scans for Access Intelligence

**1. Configure an IAM Metadata Source for your data system.**

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.

![Dropbox_Metadata_source.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d39dab3d-e584-8e10-4074-9730575d1f05.png)
2. Click **IAM Metadata Sources**. This opens the IAM Metadata Sources page.
3. Near the upper right corner of the page, click **+New IAM Metadata Source**.
4. On the **New IAM Metadata Source** popup:
  1. Enter the **Connection Name**. For example, Dropbox Metadata Source.
  2. Select **Dropbox Onprem** in **Source Type**.
  3. In the **Connection Information** area, select the Pod in the **Pod Name**.
  4. In the **Authentication Details** area, select **oAuth 2.0**,
  5. Provide **Client ID** and **Client Secret**.
  6. Click Create **New IAM Metadata source**.

**2. Configure an Access Scan Definition for your data system**

1. In Securiti, open **Data Access Governance**, then from the left menu bar choose **Settings>Access Scan Definitions**.
2. Near the upper right corner of the page, click **+ New Access Scan Definition**.
3. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select **Dropbox** in the **Data System**.
  3. In the **IAM Metadata Sources**, select the metadata sources that you have created for Dropbox. If you have not configured a metadata source, then you must click **+ Add New** to add a metadata source.
  4. In the **Associated Connectors** area, select the associated systems in the **Data Systems** for which access metadata is being scanned.
  5. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information daily.

![DAG_DropBOX_CN-ASD_link.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a9dfa1f1-e8cd-33c3-73fd-8d417c300d34.png)
  6. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  7. Click **Add Definition**.

**3. Enable the Access Scan**

If you have not selected the associated Connectors while configuring the Access Scan Definition, then you must:

- Enable the Access Intelligence Scan toggle on the Dropbox Connector Page. Navigate to the **Permissions** tab of the Connector. Enable the Access Intelligence Scan button to the ASD with the data system connector.

**4. Launching the Access Scan**

- On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.
- Click the three dots option, and select the **Scan Now** option.

### Configuring Access Intelligence Privilege Analysis without using IAM Metadata Sources

> [!NOTE]
> **Note**
> 
> Privilege Analysis for Dropbox is a private preview feature. Contact support@securiti.ai to enable it for your Securiti tenant.

To see the Dropbox Access Intelligence information you must:

#### Prerequisites

To see the Dropbox Access Intelligence information you must:

1. [Set up a Securiti pod or elastic pod.](/v1/docs/securiti-pods-and-elastic-pods)
2. [Configure and activate the connector](/v1/docs/activate-the-dropbox-connector-in-securiti). Note that the account you use to configure and activate the connector must have the **Team Admin** role assigned.
3. Perform a discovery scan on your Dropbox instance.
4. Enable the Access Intelligence Scan toggle on the Dropbox Connector Page. Navigate to the **Permissions** tab of the Connector. Enable the Access Intelligence Scan button to the ASD with the data system connector.
5. Login to Dropbox app console. Click **Create app** button.

![Create_app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7e14a924-7c74-1368-bc23-0a6f6db2564e.png)
  1. In the **Choose an API** area, select **Scoped access** option.
  2. In the **Choose the type of access you need** section, select **Full Dropbox - Access to all files and folders in a user's Dropbox**.

![Dropbox_API.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1b6558cb-45bb-6d8c-0e45-ea4bb59f8cb4.png)
  3. Provide the **Name** of your application.
  4. Click **Create app** button.
  5. In the **Settings** tab, copy the **App Key** and **App Secret** for later use while creating the IAM Metadata Source.

![O_auth_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8b6abb18-b71b-05d2-588f-b3efd796e2ca.png)
  6. In the OAuth 2 section, in the **Redirect URIs**, add **https://app.securiti.ai/static/activateConnector.html**. The redirect URl will change depending on where your Securiti tenant has hosted. Various endpoints have been listed below:

| Cloud Instance | URl |
| --- | --- |
| U.S. Cloud | app.securiti.ai |
| EU Cloud | app.eu.securiti.ai |
| U.S. GCP Cloud | app1.securiti.ai |
| Indonesia Cloud | app2.securiti.ai |
| Canada Cloud | app3.securiti.ai |
| Australia Cloud | app4.securiti.ai |
| UAE Cloud | app5.securiti.ai |
| Mumbai Cloud | app6.securiti.ai |
  7. In the **Permissions** tab, under the **Individual Scopes** area, you must select following scopes:
    - members.read
    - groups.read
    - team_data.member
    - team_data.content.read
    - files.metadata.read
    - sharing.read
    - team_info.read
  8. Click **Submit** button once you have finalized the scopes.

#### Configuring your Dropbox Access Scans for Access Intelligence

To configure Access Intelligence Scans, you must:

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.
2. Click **Access Scan Definitions**. This opens the Access Scan Definitions (ASDs) page.
3. Near the upper right corner of the page, click **+ New Access Scan Definition**.
4. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select **Dropbox** in the **Data System** menu. For more information about supported systems, see [Configuring Access Intelligence Scans without using IAM Metadata Sources](/v1/docs/configuring-access-intelligence-scans-without-using-iam-metadata-sources).
  3. In the **Source of Credentials and Connectivity for Access Intelligence Scans** area, you must select the **Data System Connector** tile.

![DAG_Connctor_as_MDS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dd07143d-58e1-344e-9b0c-3b61a2b47149.png)
  4. In the **Data System Connector** menu, select the data system instance for which you must perform Access Scan.
  5. In the **Data Systems** menu, the instance you selected earlier in **Data System Connector** is selected by default.
  6. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information weekly.
  7. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  8. Click **Add Definition**.
5. On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.
6. Click the three dots option, and select the **Scan Now** option.

### Using Access Intelligence with Dropbox

Below are example use cases to familiarize you with how to leverage Securiti's Data Command Graph to identify access and risk in your Dropbox tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identifying Dropbox Users that have access to specific Files and what their permissions are on those Files.

To identify users that have access to specific Files and their permissions:

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set **Entity** to **Files**. Set the **Attribute** to the **File Name**. Set the operator to the **Equals**.
3. Select the **Files** for which you want to identify the users that have access to.
4. Click **Apply**.
5. Click on the **User Principal** node to see the users in the data grid.
6. Click on any user for which you want to see the permissions and privileges.
7. Click on the **Policy Element** node to see the **Privilege** and **Privilege Category**.

> [!NOTE]
> **Note**
> 
> Dropbox teams can be set up using one of two configurations: Team Folders or Team Space, determined by the **has_team_shared_dropbox** configuration flag.
> 
> - In Team Space, all user folders and accessible team folders are organized under a unified root directory.
> - In Team Folder configuration, team folders are mounted directly within each member's individual folder.
> 
> Currently, only the **Team Space configuration** is supported.

#### Identifying Dropbox Users that have access to Files containing sensitive data and permissions are on those Files.

To identify the users that have access to Files containing sensitive data :

1. In Securiti, open **Data Access Governance** and choose **Identity Graph Explorer** from the left menubar.
2. Click the **+** sign in the upper left corner of the upper row of the Identity Explorer Command Graph.
3. On the filter menu, select **Files** Entity. Set the Attribute to the **Data System Type**. Select **Dropbox**.
4. On the filter menu, set the **Entity** to **Data Element**. Set the Attribute to the **Non-Personal Data**. Select **True**.
5. Click **Apply**.
6. Click on the **Files** node to see the Files that have contain sensitive data.
7. Click on the **User Principal** node to see the users that have access to these tables.
8. Click on any user for which you want to see the permissions.
9. Click on the **Policy Element** node to see the list of permissions.

#### Identifying External Users with access to Files

To identify the users that have access to Files containing sensitive data :

1. In Securiti, open **Data Access Governance** and choose **Identity Graph Explorer** from the left menubar.
2. Navigate to the **Saved Views** panel on the left side of the page.
3. On the **Popular Views** tab, navigate to the **Dropbox Queries** area. You can see the queries that help you perform privilege analysis for your Snowflake instances.
4. Click on the query **External Users with Access to Files**. Click on the **User Principal** node to see the users in the data grid.

#### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).
