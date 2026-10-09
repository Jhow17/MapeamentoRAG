---
title: "Using Data System Connectors Overview"
slug: "connectors-new-ui-template-1"
updated: 2026-03-10T06:58:45Z
published: 2026-03-10T06:58:45Z
canonical: "helpcenter.securiti.ai/connectors-new-ui-template-1"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Using Data System Connectors Overview

## 

The **Overview** page provides a centralized view of the connector’s health, including authentication status, background synchronization, and inventory sync progress. It also lets you update basic connector details and configuration, initiate scoping-based inventory sync, navigate to data inventory sync, access diagnostic reports, and create discovery scans.

## Viewing and editing data system instance details

This section displays the current authentication state of the data system instance and hosting location. Use the following table to understand the statuses of the data system instance.

| Status | Description |
| --- | --- |
| Authentication completed | - Indicates that the connector for this data system instance has successfully authenticated. - Once authentication is complete, background synchronization processes automatically begin. |
| Inactive | Indicates that the data system instance is created, but the connector has not successfully authenticated. |

- To edit the data system instance details:
  1. On the right side of the data system instance details, click **Edit** to update the basic information.

It redirects you to the **Basic Information** tab
  2. On the **Basic Information** page, update the Instance Name and Hosting location details if required.
- To migrate the data system instance to another organization:

> [!NOTE]
> Note
> 
> This option appears only if data system connector is authenticated
  1. On the right side of the data system instance details, click the **down arrow** icon.

It opens the Migrating data system popup. For more information, see Migrating a data system instance. For more information, see [Migrating data system instance](/latest/docs/data-system-migration-across-organizations-in-securiti). ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/connectors-new-ui-template-1-image-pduxoaet.png)

### 

## Reconfiguring pod and PCS

### Outpost information

This displays details about the Outpost used by the self-hosted connector.

| Status | Description |
| --- | --- |
| Outpost status | Indicates whether the pod is Active or Inactive. |
| Outpost name | Shows the name of the Outpost instance. |
| Version | Displays the current Outpost version (for example, 1.141.0-03rc). |

### Reconfigure outpost

- On the right side of the Outpost section, click **Reconfigure**. It takes you to the **Authentication** page, where you can change the Outpost.

## **PCS information and reconfiguration**

### PCS information

This displays details about the PCS used by the data system instance.

| Status | Description |
| --- | --- |
| Pcs Destination | Displays the selected PCS Destination for this data system instance |
| PCS source | Displays the PCS source, such as AWS. |

### Reconfigure PCS

- On the right side of the **Private Cloud Storage** section, click **Reconfigure**. It takes you to the **Authentication** page, where you can change the pod.

## **Authentication**

The Authentication section displays the authentication status of the data system connector and provides actions to manage and review authentication details.

### Reconfigure authentication

- On the right side of the Authentication section, click the **Reconfigure** to update or modify the authentication configuration. Use this option if authentication details need to be updated or revalidated. It takes you to the **Authentication** page, where you can update the authentication details.

### Deactivate, purge, and disconnect

When you have activated a Data system Connector, Securiti lets you deactivate the Connector and delete its data for troubleshooting and upgrading.

1. On the right side of the Authentication section, click down arrow icon. It opens a new menu.
2. From the menu, select one of the following options:
  - Disconnect
  - Deactivate
  - Purge For more information, see [Deactivate and Purge data system connector](https://helpcenter.securiti.ai/docs/deactivate-and-purge-data-in-data-system-connector).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/connectors-new-ui-template-1-image-7ikfksr6.png)

### View Diagnostic Reports

To view the diagnostic report for each Microsoft 365 application:

1. Under the **Authentication** section, click on the **View Diagnostic Report** link.
2. On the **Diagnostic Report** popup, view the diagnostic statuses of authentication activities.
3. In the top right corner of the **Diagnostic Report** popup, click **Download** to download the diagnostic report in JSON format. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/connectors-new-ui-template-1-image-2lcs9a9k.png)

## **Scoping Inventory Sync**

The Scoping Inventory Sync section displays the synchronization status of scoping inventory.

On the right side of the **Scoping Inventory Sync** section, click the Actions **(Down Arrow)** icon.

It gives you two options:

| **Option** | **Description** |
| --- | --- |
| Start Scan | Use this option to start the Scoping Inventory Sync immediately. |
| Scoping Schedule | Use this option to schedule the frequency of Scoping Inventory Sync. You have the following options: - Off - 3 days - 7 days - 30 days If you select Off, Scoping Inventory Sync never repeats. If you select 7 days, Scoping Inventory Sync repeats after 7 days. |

### ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/connectors-new-ui-template-1-image-73p7nmgc.png)

## **Data Inventory Sync**

The Data Inventory Sync section displays the data-level inventory synchronization status for each configured Microsoft 365 app. It helps you track when data inventory scans were last completed and provides quick access to related actions.

### View Data Inventory Sync Scopes

1. Under the **Data Inventory Sync** section, click the **View Scopes** link. It takes you to the **Inventory** page, where you can Data Inventory Sync Scopes. For more information, see Configure Data Inventory Sync.

### View Data Inventory Sync Stats

On the right side of the **Data Inventory Sync** section, click **View Stats**.

It takes you to the **Statistics** page, where you can see the Data Inventory Sync Stats. For more information, see the Scan Statistics. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/connectors-new-ui-template-1-image-eksg1r8v.png)

## Create Discovery Scan

This section shows the number of scans configured for the data system instance and lets you create a new discovery scan.

- On the right side of the Discovery scan section, click Create Discovery Scan. It takes you to the Create Discovery scan page. For more information, see Understanding Discovery Scans.
