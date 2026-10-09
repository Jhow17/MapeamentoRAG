---
title: "Using the connectors overview page"
slug: "new-ui-using-connectors-overview-page"
updated: 2026-09-01T05:19:08Z
published: 2026-09-01T05:19:08Z
canonical: "helpcenter.securiti.ai/new-ui-using-connectors-overview-page"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Using the connectors overview page

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

## Reconfiguring pod and PCS

### 

### Pod information

### This displays details about the Pod used by the self-hosted connector.

| Status | Description |
| --- | --- |
| Pod status | Indicates whether the pod is active or Inactive. |
| Pod name | Shows the name of the Pod instance. |
| Version | Displays the current Pod version (for example, 1.141.0-03rc). |

### Reconfigure Pod

- On the right side of the Pod section, click **Reconfigure**. It takes you to the **Authentication** page, where you can change the Pod.

> [!WARNING]
> Important
> 
> You cannot change the pod for a connector that has one or more discovery scans associated with it. To select a different pod, you must first delete all associated discovery scans. Deleting a discovery scan permanently removes previously scanned data and findings, and this action cannot be undone.
> 
> 
> 
> Securiti does not currently support moving a connector to a different pod while retaining existing scan data.

## PCS information and reconfiguration

## 

### PCS information

This displays details about the PCS used by the data system instance.

| Status | Description |
| --- | --- |
| PCS Destination | Displays the selected PCS Destination for this data system instance |
| PCS source | Displays the PCS source, such as AWS. |

### Reconfigure PCS

- On the right side of the **Private Cloud Storage** section, click **Reconfigure**. It takes you to the **Authentication** page, where you can change the pod.

## Authentication

## 

The Authentication section displays the authentication status of the data system connector and provides actions to manage and review authentication details.

### Reconfigure authentication

- On the right side of the Authentication section, click the **Reconfigure** to update or modify the authentication configuration. Use this option if authentication details need to be updated or revalidated. It takes you to the **Authentication** page, where you can update the authentication details.

### Deactivate, purge, and disconnect

When you have activated a Data system Connector, Securiti lets you deactivate the connector and delete its data for troubleshooting and upgrading.

1. On the right side of the Authentication section, click down arrow icon. It opens a new menu.
2. From the menu, select one of the following options:
  - Disconnect
  - Deactivate
  - Purge For more information, see [Deactivate and Purge data system connector](https://helpcenter.securiti.ai/docs/deactivate-and-purge-data-in-data-system-connector).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-27 at 3.29.43 PM.png)

### View Diagnostic Reports

To view the diagnostic report for each Microsoft 365 application:

1. Under the **Authentication** section, click on the **View Connector Diagnostics Report** link.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-27 at 3.27.04 PM.png)
2. On the **Connector Diagnostics Report** popup, view the diagnostic statuses of authentication activities.
3. In the top right corner of the **Connector Diagnostics Report** popup, click **Download** to download the diagnostic report in JSON format. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-06 at 10.29.10 AM.png)
4. To learn about what this Connector Diagnostics Report covers, click **Learn more**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-07 at 10.03.02 AM.png)
5. After clicking **Learn more**, you will see the **About This Report** screen, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-07 at 10.05.56 AM.png)

## 

## Scoping Inventory Sync

The Scoping Inventory Sync section displays the synchronization status of scoping inventory.

While a Scoping Inventory Sync is running, the section also displays the number of entities discovered so far, along with the sync status and elapsed time. The discovered entity counts update automatically as the sync progresses and remain available after the sync is completed. as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-27 at 3.17.04 PM.png)

On the right side of the **Scoping Inventory Sync** section, click the Actions **(Down Arrow)** icon. It gives you two options, as shown below.

| **Option** | **Description** |
| --- | --- |
| Start Scan | Use this option to start the Scoping Inventory Sync immediately. |
| Scoping Schedule | Use this option to schedule the frequency of Scoping Inventory Sync. You have the following options: - Off - 3 days - 7 days - 30 days If you select Off, Scoping Inventory Sync never repeats. If you select 7 days, Scoping Inventory Sync repeats after 7 days. |

### 

## 

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-27 at 3.20.54 PM.png)

For more information, see [Scoping Inventory Syncs for connectors](/latest/docs/scoping-metadata-syncs-for-connectors).

## Data Inventory Sync

The Data Inventory Sync section displays the data-level inventory synchronization status for each configured Microsoft 365 app. It helps you track when data inventory scans were last completed and provides quick access to related actions.

### View Data Inventory Sync scopes

Under the **Data Inventory Sync** section, click the Actions **(Down Arrow)** and select **View Selected Scope** tab.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-27 at 3.24.12 PM.png) It takes you to the **Inventory** page, where you can Data Inventory Sync Scopes. For more information, see [Configure Data Inventory Sync](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

### View Data Inventory Sync stats

On the right side of the **Data Inventory Sync** section, click **View Stats**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-27 at 3.25.42 PM.png)

It takes you to the **Statistics** page, where you can see the Data Inventory Sync Stats. For more information, see the [Scan Statistics](/latest/docs/viewing-data-inventory-sync-statistics).

## Creating Discovery Scan

This section shows the number of scans configured for the data system instance and lets you create a new discovery scan.

> [!NOTE]
> Note
> 
> Securiti lets you run only one active discovery scan at a time for structured and hybrid connectors. After a scan is created, the **Create Discovery Scan** becomes disabled.

- On the right side of the **Discovery scan** section, click **Create Discovery Scan**. It takes you to the Create Discovery scan page. For more information, see [Discovery Scan](/latest/docs/discovery-scans).
