---
title: "Hyperdrive Entitlement Scan for Microsoft Teams"
slug: "hyperdrive-entitlement-scan-for-microsoft-teams"
updated: 2026-07-20T13:08:57Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/hyperdrive-entitlement-scan-for-microsoft-teams"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive Entitlement Scan for Microsoft Teams

Hyperdrive Entitlement Scan for Microsoft Teams provides visibility into who, and what, can access files discovered in your Microsoft Teams environment.

By leveraging entitlement metadata collected during the scan, it enables organizations to identify which users and applications have control over discovered files, and what sensitive data those files contain. This helps security and governance teams validate access, reduce over-exposure, and scope Gencore AI pipelines with confidence.

### Prerequisites

Before configuring Entitlement Scan for Microsoft Teams, ensure the following requirements are completed:

#### Connector setup

Ensure the Microsoft Teams connector is configured and synced.

For detailed setup instructions of all the required steps, see:

- [Microsoft 365 (Hyperdrive)](/latest/docs/microsoft-365)
- [Configuring Data Inventory Sync for Microsoft Teams (Hyperdrive)](/latest/docs/activity-analysis-for-microsoft-teams)

#### Entitlement Scan requirements

Ensure the following prerequisites are also completed:

**Enable the entitlement scan**

In the connector's Inventory Sync section (or Inventory Sync Options for classic UI), check the Entitlement Scan option to sync entitlement metadata for discovered resources. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 4(17).png)

> [!WARNING]
> Important
> 
> - Entitlement data appears in Graph Explorer only after the entitlement scan runs successfully at least once.
> - If Entitlement Scan is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Using Entitlement Scan in Hyperdrive for Microsoft Teams

Below are example use cases to help you use Securiti's **Data Command Graph** to analyze file access and identify risks across your Microsoft Teams environment using Entitlement Scan.

When you apply filters in the **Access Graph Explorer**, all associated results update dynamically based on your selected criteria.

#### Identify and report on Microsoft Teams files readable by users

This query helps you identify which users can read files discovered in your Microsoft Teams environment. It enables you to validate whether file access aligns with intended permissions.

To identify Microsoft Teams files readable by users:

1. In Securiti, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click + to open the filter menu.
4. On the filter menu, select the **Files entity**.
5. Click the three dots next to the **Files entity**, select **Add Property**, choose **Data System Type**, and select Microsoft Teams.
6. Click the three dots next to the **Files entity**, select **Add Relationship**, and choose **Readable by** User Principal.
7. Click **Apply**, and then click **Run Query**.
8. Click on the **User Principal** node to view the list of users that can read the selected files.

![List of files with properties in Microsoft Teams, including file names and formats.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 4(16).png)

#### Identify and report on Microsoft Teams files writable by users

This query helps you identify which users can write to, or modify, files discovered in your Microsoft Teams environment. Users granted write access can create or modify file content, so monitoring this level of access helps you enforce least-privilege access and detect overprivileged users.

To identify Microsoft Teams files writable by users:

1. In Securiti, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click + to open the filter menu.
4. On the filter menu, select the **Files entity**.
5. Click the three dots next to the **Files entity**, select **Add Property**, choose **Data System Type**, and select Microsoft Teams.
6. Click the three dots next to the **Files entity**, select **Add Relationship**, and choose **Writable by User Principal**.
7. Click **Apply**, and then click **Run Query**.
8. Click on the **User Principal** node to view the list of users that can write to the selected files.

![Graph Explorer interface displaying files and user principal data for Microsoft Teams.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(22).png)

#### Identify and report on Microsoft Teams files controllable by AI agents

This helps you identify which AI agents have full control over files discovered in your Microsoft Teams environment. Full control access lets an AI agent manage permissions in addition to reading and modifying content, so monitoring this level of access helps you identify the highest-privilege, and highest-risk, agent access to your data.

To identify Microsoft Teams files controllable by AI agents:

1. In Securiti, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click + to open the filter menu.
4. On the filter menu, select the **Files entity**.
5. Click the three dots next to the **Files entity**, select **Add Property**, choose **Data System Type**, and select Microsoft Teams.
6. Click the three dots next to the **Files entity**, select **Add Relationship**, and choose **Controllable by AI Agent**.
7. Click **Apply**, and then click **Run Query**.
8. Click on the **AI Agent** node to view the list of agents that have full control over the selected files.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 11(2).png)

An individual user interacts with the data system and accesses data. User Principle represents a user account in a Data System or an Identity in an identity Provider (IDP) like Active Directory, Okta, or similar.
