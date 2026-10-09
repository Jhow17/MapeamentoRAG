---
title: "Hyperdrive Entitlement Scan for Microsoft 365 Sharepoint Online"
slug: "hyperdrive-entitlement-scan-for-m-sharepoint-online"
updated: 2026-08-03T15:07:15Z
published: 2026-08-03T15:07:15Z
canonical: "helpcenter.securiti.ai/hyperdrive-entitlement-scan-for-m-sharepoint-online"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive Entitlement Scan for Microsoft 365 Sharepoint Online

Securiti's Entitlement Scan for Microsoft 365 SharePoint Online gives you visibility into how access and ownership of SharePoint data are structured across your tenant. Once an entitlement scan runs successfully on your SharePoint Online connector, you can use the Access Graph Explorer in Data command graph to trace the access paths between users, AI agents, applications, and files.

This article walks you through common queries you can run to identify:

- Users with write access to SharePoint files
- AI agents with control access to SharePoint files
- Applications with control access to SharePoint files

These queries help you enforce least-privilege access, detect overprivileged or unintended access, and reduce the risk of data exposure across your SharePoint Online environment.

### Prerequisites

Before configuring Entitlement Scan for Microsoft SharePoint Online, ensure the following requirements are completed.

#### Connector Setup

Ensure the Microsoft 365 SharePoint Online connector is configured and synced in Hyperdrive.

For detailed setup instructions of all the required steps, see:

- [Microsoft 365 (Hyperdrive)](/latest/docs/microsoft-365)
- [Configuring Data Inventory Sync for SharePoint (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-sharepoint-hyperdrive)

#### Entitlement Scan Requirements

Ensure the following Entitlement Scan–specific prerequisites are completed, which includes certificate-based authentication and configuration of API permissions.

**Certificate-based authentication**

Entitlement Scan requires the SharePoint Online connector to be activated with a Private Key and Certificate Thumbprint, in addition to OAuth Client ID and Secret. For more information, see [Grant access and obtain credentials in SharePoint Online (Hyperdrive)](/latest/docs/create-an-entra-id-app-and-obtain-credentials-for-microsoft-365#obtain-authentication-credentials)

Important

- The Private Key and Certificate Thumbprint are mandatory for Data Inventory Sync and Entitlement Scan.
- If you're using Selective Site(s) Access, Certificate-based Credentials are required for both the Data Inventory Sync and Entitlement Scan. For more information, see Obtain credentials for SharePoint Online Selective Site(s) Access (Hyperdrive).

### Configure and Run Entitlement Scan

To configure and run Entitlement Scan for Microsoft SharePoint Online:

1. On the left sidebar, choose Inventory.
2. On the Inventory Sync page, mark the Enable Inventory Sync checkbox to sync the metadata for your data system.
3. Under Enable Inventory Sync, click Show More Options, and mark the Run Entitlement Scan checkbox.
4. Under the Inventory Scope, select the data system scoping items from the menu to include in the sync. You can select: All, Group(s), or User(s).
5. Once the Inventory scopes configuration is complete, click Execute, and then Save.

![Settings for inventory sync and user selection in a configuration interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory-scope.png)

> [!NOTE]
> Note
> 
> - It takes time to complete the Data Inventory Sync and Entitlement Scan. You can check the state in the Status and Ingestion Status message in the Inventory Sync section.
> - Scan statistics are available only after the scan is successfully completed.

> [!WARNING]
> Note
> 
> - Entitlement data is published in the Access Graph Explorer only for tenants with Hyperdrive mode enabled. If this update is not available in your tenant, contact your Customer Success Manager or Account Representative to determine if this feature is included in your subscription and whether your tenant meets the requirements to use this functionality.
> - You must have an Entitlement Scan configured and run successfully for your Microsoft 365 SharePoint Online connector. For more information, see [Configuring Data Inventory Sync for SharePoint (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-sharepoint-hyperdrive).

### Using Entitlement Scan in Hyperdrive for SharePoint Online

Below are example use cases to help you use Securiti's **Data Command Graph** to identify access and risk in your Microsoft SharePoint Online environment using Entitlement Scan.

When you apply filters in the **Access Graph Explorer**, all associated results update dynamically based on your selected criteria.

#### Identify users with write access to SharePoint files

This helps you identify user principals who have write access to files in Office 365 SharePoint Online. Users granted write access can create or modify file content. Monitoring this level of access helps you enforce least-privilege principles and detect overprivileged users across your SharePoint environment.

To identify users with write access to SharePoint files:

1. In Securiti, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click + to open the filter menu.
4. On the filter menu, select the **Files entity**.
5. Click the three dots next to the **Files entity**, select **Add Property**, choose **Data System Type**, and select Office 365 SharePoint Online.
6. Click the three dots next to the **Files entity**, select **Add Relationship**, and choose **Writable by User**, then select **User Principal** as the target entity.
7. Click **Run Query**.
8. Click on the **User Principal** node to view the list of users with write access to the filtered files.

![Graph Explorer interface displaying files and user principal data types.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (19)(1).png)

#### Identify AI agents with control access to SharePoint files

This helps you identify AI agents that have control access to files in Office 365 SharePoint Online. Agents granted control access can read, modify, and manage permissions on file content. Monitoring this level of access helps you detect unintended AI agent exposure to file data across your SharePoint environment.

To identify AI agents with control access to SharePoint files:

1. In Securiti, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click + to open the filter menu.
4. On the filter menu, select the **Files entity**.
5. Click the three dots next to the **Files entity**, select **Add Property**, choose **Data System Type**, and select Office 365 SharePoint Online.
6. Click the three dots next to the **Files entity**, select **Add Relationship**, and choose **Controllable by AI Agent**, then select **AI Agent** as the target entity.
7. Click **Run Query**.
8. Click on the **AI Agent** node to view the list of agents with control access to the filtered files.

![Graph Explorer interface displaying AI Agent details and asset information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (20).png)

#### Identify applications with control access to SharePoint files

This helps you identify M365 applications that have control access to files in Office 365 SharePoint Online. Applications granted control access can read, modify, and manage permissions on file content. Monitoring this level of access helps you detect overprivileged or unintended application access across your SharePoint environment.

To identify applications with control access to SharePoint files:

1. In Securiti, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click + to open the filter menu.
4. On the filter menu, select the **Files entity**.
5. Click the three dots next to the **Files entity**, select **Add Property**, choose **Data System Type**, and select Office 365 SharePoint Online.
6. Click the three dots next to the **Files entity**, select **Add Relationship**, and choose **Controllable by Application**, then select **M365 Application** as the target entity.
7. Click **Run Query**.
8. Click on the **M365 Application** node to view the list of applications with control access to the filtered files.

![Overview of M365 applications with unique IDs and service account names listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (21)(1).png)

#### Identify and report on external activities in SharePoint Online

This query helps you identify activities performed by external actors across your connected data systems. It provides visibility into interactions involving external users or systems, enabling you to monitor third-party access and detect potential risks associated with external data exposure. This use case is especially important for identifying how data is accessed or interacted with outside your organization.

To identify external activities:

1. In Securiti, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Is External**, and set it to **True**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select the data systems you want to include.
7. (Optional) Click the three dots next to the **Activity Log** entity to add additional filters such as **Activity Type**, or relationships like **User Principal** or **Application**, for deeper analysis.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

**Default columns displayed in the data grid**

By default, the data grid displays the following activity metadata:

- Display Name
- Activity ID
- Connector Type ID
- Data Asset ID
- Container ID
- Is External

**Note**

The **Is External = True** filter ensures that only activities involving external actors are displayed. You can further correlate these activities with users or applications to identify who initiated the action.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 8(10).png)

Entitlement scan identifies the privileges and permissions an entity, such as a user, application, or AI agent, holds for a specific data object such as file.

The Data Command Graph provides a graphical view of important information and the relationships between data systems after connecting to cloud accounts. It shows the discovered assets across your cloud accounts, covering both IaaS and SaaS platforms, and helps you understand how your data systems, assets, and resources are interconnected, supporting better visibility, governance, and risk management.

Type of scan focused on identifying metadata rather than content for files in a data system. Data Inventory sync includes identifying file attributes such as name, size, creation date etc and information such as access permissions, ownership, and entitlement for resources. Data Inventory scan includes inventory and entitlement scanning for Genstack, and is supported for monitored, self-hosted data systems only
