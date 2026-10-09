---
title: "OneDrive"
slug: "data-access-governance-onedrive"
updated: 2026-09-23T05:38:47Z
published: 2026-09-23T05:38:47Z
canonical: "helpcenter.securiti.ai/data-access-governance-onedrive"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# OneDrive

This section describes the Data Access Governance features supported for OneDrive and the steps to configure these functionalities.

### Supported Data Access Governance Feature Sets

The following is the list of features supported for OneDrive:

#### Access Intelligence

- Privilege Analysis - Privilege Analysis is currently supported for OneDrive Self-Hosted connectors only.
  - File-level permissions granularity.
- Activity Analysis - Not Supported

#### Access Control

- Not Supported

#### Cross-Border Transfer Policies

- Not Supported

> [!NOTE]
> Note
> 
> If Data Access Governance features for OneDrive are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

#### Example Supported Use Cases

The supported example use cases include:

#### Access Intelligence

- Identify and report on which users and user groups have access to specific Files and their permissions on those Files [Identify and report on which users or user groups have access to specific Files]

### Configuring OneDrive Data Access Governance

This section describes the configuration process of Data Access Governance features for OneDrive

### Configuring Access Intelligence Privilege Analysis using IAM Metadata Sources

To see the OneDrive Access Intelligence information, you must:

#### Prerequisites

To see the OneDrive Access Intelligence information you must:

1. Need a valid Microsoft 365 account with access to OneDrive.You must register your application in Azure AD, configure appropriate permissions, and obtain client credentials.

**To register your application in Azure AD:**

**Configure API Permissions**

You must configure Microsoft Graph API permissions to allow Securiti to read the Identity and Access Management (IAM) related metadata. To configure Permissions:

> [!NOTE]
> **Note**
> 
> If you have used application permissions for existing applications, you need to re-authenticate the Metadata Source (MDS) in Securiti and Grant Admin Consent. If the applications in OneDrive were created without application permissions, either create a new application with the required permissions and onboard it, or add application permissions to the existing app and then re-authenticate the MDS on the Securiti platform.
  1. Login to the [Azure Portal](https://portal.azure.com).
  2. From the left menu bar, click Identity>Applications>App registrations.
  3. Click **+New registration**.

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(12).png)
  4. Add the following details:
    - Enter the **Name of your application**.
    - Choose **Accounts in this organizational directory only** in **Supported account types**
    - In the Redirect URl (optional) area, select Web, and enter the URI for your Securiti tenant.
      - US cloud:
        - `https://app.securiti.ai/static/activateMetadataSource.html`
        - `https://app.securiti.ai/static/activateConnector.html`
      - US1 cloud:
        - `https://app1.securiti.ai/static/activateMetadataSource.html`
        - `https://app1.securiti.ai/static/activateConnector.html`
      - Canada cloud:
        - `https://app3.securiti.ai/static/activateMetadataSource.html`
        - `https://app3.securiti.ai/static/activateConnector.html`
      - EU cloud:
        - `https://app.eu.securiti.ai/static/activateMetadataSource.html`
        - `https://app.eu.securiti.ai/static/activateConnector.html`
      - Indonesia cloud:
        - `https://app2.securiti.ai/static/activateMetadataSource.html`
        - `https://app2.securiti.ai/static/activateConnector.html`
      - Australia cloud:
        - `https://app4.securiti.ai/static/activateMetadataSource.html`
        - `https://app4.securiti.ai/static/activateConnector.html`
      - UAE cloud:
        - `https://app5.securiti.ai/static/activateMetadataSource.html`
        - `https://app5.securiti.ai/static/activateConnector.html`
      - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateMetadataSource.html`
  5. Click **Register**.

![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d(11).png)
  1. Click **Add a permission>Microsoft Graph>Application permissions**. Select the following permissions

Delegated Permission of type **User.Read** is added by Microsoft by default once the application is registered in Microsoft Entra. You must not disable the permission added by default.
    - Directory.Read.All
    - Files.Read.All
  2. Click **Add permissions**.
  3. Click on **Grant admin consent** for the permissions.
2. [Set up a Securiti pod or elastic pod.](/v1/docs/securiti-pods-and-elastic-pods)
3. [Configure and activate the connector](/v1/docs/activate-the-smb-connector-in-securiti).
4. For your OneDrive instance, perform
  - [Discovery scan](/v1/docs/configure-discovery-scans-in-microsoft-365-onedrive)

OR
  - [Data Inventory Sync](/v1/docs/configuring-data-inventory-sync-for-onedrive-self-hosted)

#### Configuring your OneDrive Access Scans for Access Intelligence

**1. Configure an IAM Metadata Source for Microsoft Office**

1. In Securiti, select the jewel icon from the left menu bar, hover over **Data Access Governance**, then go to **Settings > IAM Metadata Source**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CVEQVS1R.png)
2. Click **IAM Metadata Sources**. This opens the IAM Metadata Sources page.
3. Near the upper right corner of the page, click **+New IAM Metadata Source**.
4. On the **New IAM Metadata Source** popup:
  1. Enter the **Connection Name**. For example, Microsoft 365 Metadata Source.
  2. Select **Microsoft 365** in **Source Type**.
  3. In the **Connection Information** area, enter the **Domain Name or (Account ID)**
  4. Select the Pod in the **Pod Name**.
  5. In the **Authentication Details** area, select **oAuth 2.0**,
  6. Provide **Client ID** and **Client Secret**.
  7. Click Create **New IAM Metadata source**.

**2. Configure an Access Scan Definition for OneDrive**

1. In Securiti, select the jewel icon from the left menu bar, hover over **Data Access Governance**, then go to **Settings > Access Scan Definitions**.
2. Near the upper right corner of the page, click **+ New Access Scan Definition**.
3. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select **OneDrive** in the **Data System**.
  3. In the **IAM Metadata Sources**, select the metadata sources that you have created for Microsoft 365. If you have not configured a metadata source, then you must click **+ Add New** to add a metadata source.
  4. In the **Associated Connectors** area, select the associated systems in the **Data Systems** for which access metadata is being scanned.
  5. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information daily.

![Access scan definition settings for OneDrive with IAM metadata source selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-23 at 5.21.24 PM.png)
  6. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  7. Click **Add Definition**.

**3. Enable the Access Scan**

If you have not selected the associated Connectors while configuring the Access Scan Definition, then you must:

- Enable the Access Intelligence Scan toggle on the OneDrive Connector Page. Navigate to the **Permissions** tab of the Connector. Enable the Access Intelligence Scan button to the ASD with the data system connector.

**4. Launching the Access Scan**

- On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.
- Click the three dots option, and select the **Scan Now** option.

#### Using Access Intelligence with OneDrive

Below are example use cases to familiarize you with how to leverage Securiti's Data Command Graph to identify access and risk in your OneDrive tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identify and report on which users and user groups have access to specific File and their permissions on specific Files

To identify users that have access to specific Files and their permissions:

1. In Securiti, open **Data Access Governance** and choose **Data Command Graph** to access the Command Graph.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer** .
3. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **User Group Principal** Entity. Click three dots with the **User Group Principal** Entity, and select **+ Add Property**. Choose the **Provider Type** property. Select **Office365**. Click **Apply**.
4. Click three dots with the **User Group Principal** Entity, and select **Add Relationship**. Select **User Principle**.

![Access Graph Explorer displaying user principals and resource access details for Office365.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/onedrive 1.png)
5. Click three dots with the **User Principal** Entity, and select **Add Relationship**. Select **Resource Access**. Click three dots with the **Resource Access** Entity, and select **Add Relationship**. Select **Files**. Add **File Name** Property for Files Entity.
6. Select the **Files** for which you want to identify the users that have access to. You can also write the File Name in the search box.
7. Click **Apply**.
8. Click on the **User Principal** node to see the users in the data grid.
9. Click on the **Resource Access** node to see the **Privilege** and **Privilege Category**.

#### Identify and report on which users have access to Files and have Write permissions

To identify users who have access to Files and have Write permissions:

1. In Securiti, open **Data Access Governance** and choose **Data Command Graph** to access the Command Graph.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer** .
3. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **User Principal** Entity. Click three dots with the **User Principal** Entity, and select **+ Add Property**. Choose the **Provider Type** property. Select **Office365**. Click **Apply**.

![Access Graph Explorer displaying user principal and resource access details for OneDrive permissions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/onedrive 2.png)
4. Click three dots with the **User Principal** Entity, and select **Add Relationship**. Select **Resource Access**. Click three dots with the **Resource Access** Entity, and select **+Add Property**. Select **Privilege Bundle**. Choose **write** Property. Click **Apply**.
5. Click three dots with the **Privilege Bundle** Entity. Select **Add Relationship**. Choose **Files** Entity.
6. Click on the **User Principal** node to see the users in the data grid.

#### Identify and report on which users have access to Files containing sensitive data elements

To identify users that have access to Files containing sensitive data elements:

1. In Securiti, open **Data Access Governance** and choose **Data Command Graph** to access the Command Graph.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer** .
3. Near the left right corner of the page, click **+** to open the filter menu. On the filter menu, select the **User Principal** Entity. Click three dots with the **User Principal** Entity, and select **+ Add Property**. Choose **Provider Type** property. Select **Office365**. Click **Apply**.

![Access Graph Explorer displaying user principals, resource access, and data elements for Office365.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/onedrive 3.png)
4. Click three dots with the **User Principal** Entity, and select **Add Relationship**. Select **Resource Access**. Click three dots with the **Resource Access** Entity, and select **Add Relationship**. Select **Files**.
5. Click three dots with the **Files** Entity, and select **Add Relationship**. Select **Data Element** Entity.
6. Click three dots with the **Data Element** Entity. Select **+Add Property**. Choose **Personal Data**. Select **equals** operator, and set value to **True**.
7. Click on the **User Principal** node to see the users in the data grid.
8. Click on the **Data Element** node to see the sensitive data elements that users have access to.

#### To identify service accounts that are members or owners of user groups:

This query helps you identify service accounts that are associated with user groups and understand whether the service account is a **member or an owner** of those groups. In Microsoft 365, service account group relationships are represented through **partitioned groups**, which distinguish the role of the account (member or owner). Service accounts are linked **directly to partitioned groups**, not to container (parent) groups.

1. In **Securiti**, open **Data Access Governance** and choose **Data Command Graph** to access the Command Graph.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Service Account** entity.
5. Click the three dots next to the **Service Account** entity, select **Add Property**, choose **Provider Type**, and select **Office365**.
6. Click the three dots next to the **Service Account** entity, select **Add Relationship**, and choose **MSFT 365 User Group Partition**.
7. Select the **Is Member Of** relationship.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Service Account** node to view service accounts in the data grid.
10. Click on the **MSFT 365 User Group Partition** node to view the associated user groups and the service account’s role (member or owner).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 4-20260202-111209.png)

**Default columns displayed for Service Accounts**

The data grid displays the following columns for each service account by default:

- Service Account Name
- Provider Type
- Provider Account ID
- Service Account Unique ID

**Additional columns available for Service Accounts**

You can customize the data grid to include the following additional attributes:

- Description
- Display Name
- Organization
- Service Principal Type

### Configuring Access Intelligence Privilege Analysis without using IAM Metadata Sources

> [!NOTE]
> **Note**
> 
> Privilege Analysis for OneDrive is a private preview feature. Contact support@securiti.ai to enable it for your Securiti tenant.

#### Prerequisites

To see the OneDrive Access Intelligence information you must:

1. Need a valid Microsoft 365 account with access to OneDrive.You must register your application in Azure AD, configure appropriate permissions, and obtain client credentials.

**To register your application in Azure AD:**

**Configure API Permissions**

You must configure Microsoft Graph API permissions to allow Securiti to read the Identity and Access Management (IAM) related metadata. To configure Permissions:

> [!NOTE]
> **Note**
> 
> If you have used application permissions for existing applications, you need to re-authenticate the Metadata Source (MDS) in Securiti and Grant Admin Consent. If the applications in OneDrive were created without application permissions, either create a new application with the required permissions and onboard it, or add application permissions to the existing app and then re-authenticate the MDS on the Securiti platform.
  1. Login to the [Azure Portal](https://portal.azure.com).
  2. From the left menu bar, click Identity>Applications>App registrations.
  3. Click **+New registration**.

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(12).png)
  4. Add the following details:
    - Enter the **Name of your application**.
    - Choose **Accounts in this organizational directory only** in **Supported account types**
    - In the Redirect URl (optional) area, select Web, and enter the URI for your Securiti tenant.
      - US cloud:
        - `https://app.securiti.ai/static/activateConnector.html`
      - US1 cloud:
        - `https://app1.securiti.ai/static/activateConnector.html`
      - Canada cloud:
        - `https://app3.securiti.ai/static/activateConnector.html`
      - EU cloud:
        - `https://app.eu.securiti.ai/static/activateConnector.html`
      - Indonesia cloud:
        - `https://app2.securiti.ai/static/activateConnector.html`
      - Australia cloud:
        - `https://app4.securiti.ai/static/activateConnector.html`
      - UAE cloud:
        - `https://app5.securiti.ai/static/activateConnector.html`
      - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html`
  5. Click **Register**.

![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d(11).png)
  1. Click **Add a permission>Microsoft Graph>Application permissions**. Select the following permissions

Delegated Permission of type **User.Read** is added by Microsoft by default once the application is registered in Microsoft Entra. You must not disable the permission added by default.
    - Directory.Read.All
    - Files.Read.All
  2. Click **Add permissions**.
  3. Click on **Grant admin consent** for the permissions.
2. [Set up a Securiti pod or elastic pod.](/v1/docs/securiti-pods-and-elastic-pods)
3. [Configure and activate the connector](/v1/docs/activate-the-smb-connector-in-securiti).
4. For your OneDrive instance, perform:
  - [Discovery scan](/v1/docs/configure-discovery-scans-in-microsoft-365-onedrive)

OR
  - [Data Inventory Sync](/v1/docs/configuring-data-inventory-sync-for-onedrive-self-hosted)
5. Enable the Access Intelligence Scan toggle on the OneDrive Connector Page. Navigate to the **Permissions** tab of the Connector. Enable the Access Intelligence Scan button to the ASD with the data system connector.

#### Configuring your OneDrive Access Scans for Access Intelligence

To configure Access Intelligence Scans, you must:

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.
2. Click **Access Scan Definitions**. This opens the Access Scan Definitions (ASDs) page.
3. Near the upper right corner of the page, click **+ New Access Scan Definition**.
4. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select **OneDrive** in the **Data System** menu. For more information about supported systems, see [Configuring Access Intelligence Scans without using IAM Metadata Sources](/v1/docs/configuring-access-intelligence-scans-without-using-iam-metadata-sources).
  3. In the **Source of Credentials and Connectivity for Access Intelligence Scans** area, you must select the **Data System Connector** tile.

![DAG_OneDrive_Connector_as_MDS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ca41520d-a9ba-71d3-d908-94f982cf2022.png)
  4. In the **Data System Connector** menu, select the data system instance for which you must perform Access Scan.
  5. In the **Data Systems** menu, the instance you selected earlier in **Data System Connector** is selected by default.
  6. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information weekly.
  7. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  8. Click **Add Definition**.
5. On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.
6. Click the three dots option, and select the **Scan Now** option.

Privilege Analysis is a feature set of DAG Access Intelligence which ingests the Identity and Access Management (IAM) and Role Based Access Control (RBAC) metadata within your data systems and presents the data through a normalized knowledge graph allowing you to quickly identify who can access sensitive data, how that access is created, and who can administer that access within a data system.
