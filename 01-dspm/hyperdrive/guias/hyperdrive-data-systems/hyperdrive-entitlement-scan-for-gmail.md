---
title: "Hyperdrive Entitlement Scan for Gmail"
slug: "hyperdrive-entitlement-scan-for-gmail"
updated: 2026-09-25T16:33:20Z
published: 2026-09-25T16:33:20Z
canonical: "helpcenter.securiti.ai/hyperdrive-entitlement-scan-for-gmail"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive Entitlement Scan for Gmail

Hyperdrive Entitlement Scan for Gmail (Google Workspace) provides visibility into who, and what, can access mail attachments discovered in your Gmail environment.

By leveraging entitlement metadata collected during the scan, it enables organizations to identify which users and AI agents have control over discovered mail files, and what sensitive data those files contain. This helps security and governance teams validate access and reduce over-exposure.

## Prerequisites

Before configuring Entitlement Scan for Gmail (Google Workspace), ensure the following requirements are completed:

### Connector setup

Ensure the Gmail (Google Workspace) connector is configured and synced.

For detailed setup instructions of all the required steps, see:

- [Gmail (Google Workspace)](/latest/docs/gmail-google-workspace-hyperdrive)
- [Data Inventory Sync and Entitlement Scan for data systems](/latest/docs/configure-data-inventory-sync-for-gmail-google-workspace-hyperdrive)

### Entitlement Scan requirements

Ensure the following prerequisites are also completed:

#### Enable the entitlement scan

In the connector's Inventory Sync section (or Inventory Sync Options for classic UI), check the **Entitlement Scan** option to sync entitlement metadata for discovered mail resources. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 4(13).png)

> [!NOTE]
> **Important**
> 
> - Entitlement data appears in Graph Explorer only after the entitlement scan runs successfully at least once.
> - If Entitlement Scan is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

## Using Entitlement Scan in Hyperdrive for Gmail

Below are example use cases to help you use Securiti's Data Command Graph to analyze mail file access and identify risks across your Gmail environment using Entitlement Scan.

When you apply filters in the Access Graph Explorer, all associated results update dynamically based on your selected criteria.

**Identify and report on Gmail files controllable by users**

This query helps you identify which users can access, or control, mail attachments discovered in your Gmail environment. It enables you to validate whether attachment access aligns with intended permissions.

To identify Gmail files controllable by users:

1. In Securiti, open Data Access Governance after clicking the top left jewel icon.
2. From the left navigation menu, click Data Command Graph, and choose Access Graph Explorer.
3. Near the upper left corner of the page, click + to open the filter menu.
4. On the filter menu, select the Files entity.
5. Click the three dots next to the Files entity, select Add Property, choose Data System Type, and select G Suite Gmail (Attachments).
6. Click the three dots next to the Files entity, select Add Relationship, and choose Controllable by User.
7. Click Apply, and then click Run Query.
8. Click on the User Principal node to view the list of users that can control the selected files.

![Graph Explorer interface displaying files and user principal data types in G Suite Gmail.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (23).png)

**Identify and report on Gmail files controllable by AI agents**

This helps you identify which AI agents can access, or control, mail attachments discovered in your Gmail environment, and what sensitive data those files contain. It provides visibility into non-human access patterns and helps you scope AI pipelines before finalizing access.

To identify Gmail files controllable by AI agents:

1. In Securiti, open Data Access Governance after clicking the top left jewel icon.
2. From the left navigation menu, click Data Command Graph, and choose Access Graph Explorer.
3. Near the upper left corner of the page, click + to open the filter menu.
4. On the filter menu, select the Files entity.
5. Click the three dots next to the Files entity, select Add Property, choose Data System Type, and select G Suite Gmail (Attachments).
6. Click the three dots next to the Files entity, select Add Relationship, and choose Controllable by AI Agent.
7. Click Apply, and then click Run Query.
8. Click on the AI Agent node to view the list of AI agents that can control the selected files.

![Graph Explorer interface displaying files and data system types for G Suite Gmail.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (24).png)
