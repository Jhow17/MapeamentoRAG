---
title: "Enable blob inventory in your Azure account"
slug: "enable-blob-inventory-in-your-azure-account"
updated: 2025-10-30T19:21:30Z
published: 2025-11-03T06:13:51Z
canonical: "helpcenter.securiti.ai/enable-blob-inventory-in-your-azure-account"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Enable blob inventory in your Azure account

You must enable blob inventory in your Microsoft Azure account to run the data inventory sync using native inventory method.

1. Log in to your Microsoft Azure account.
2. On the left sidebar, click **Storage accounts**.

![sidebar-storage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f843bd43-d5d3-fe11-44fe-25fb1cd2289f.png)

It opens the list of storage accounts that you have in your Microsoft Azure account.
3. Select the storage account in which you want to create the blob inventory.
4. On your storage account sidebar, search for **Blob inventory**. Then choose **Blob inventory** > **Add your first inventory rule**.

![search-blob.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-63e241c1-adb8-ae06-7410-92e5b7846806.png)

> [!NOTE]
> **Note**
> 
> If you already have an inventory rule configured in your Azure account, you can skip the next step below and proceed directly to [step 6](/v1/docs/enable-blob-inventory-in-your-azure-account) to view the inventory rule details.
5. On **Add a rule** popup, apply the following settings:

| **Setting** | **Description** |
| --- | --- |
| Rule name | Add a convenient rule name. See the example below. *test-rule-name*. Record this rule name to use it later for native inventory credentials in Securiti connector activation. |
| Inventory policy container | Select a container from the menu where you want to store the inventory reports. Record this container to use it later for native inventory credentials in Securiti connector activation. |
| Object type to inventory | Select the object type you want to include in inventory sync. Inventory rule applies to either: - Blob - Container |
| (Optional) Blob types | Mark the checkboxes for the blob types you want to include for the inventory rule. |
| (Optional) Blob subtypes | Mark the checkboxes for blob subtypes you want to include for the inventory rule. > [!NOTE] > **Important** > > To include all versions of blobs in the data inventory sync, be sure to select the following blob subtypes: > > - Include blob versions > - Include deleted blobs |
| Blob inventory fields | Select the blob inventory fields that you would like to include in your inventory reports |
| Inventory frequency | Select the inventory frequency: - Daily or - Weekly. > [!NOTE] > **Note** > > Securiti fetches the latest inventory report. You must set the frequency accordingly. |
| Export format | Mark the radio buttons for: - CSV |

Click **Save**.

![rule-popup-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ca0b68a-1b65-11d7-0ddd-554daba1daa2.png)

![rule-popup-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad47448c-3ee6-0eee-1191-3b074b4080a1.png)

It takes you to the inventory rules list page.
6. On the inventory rules page under the **List view** tab, click on the inventory rule link to see the details.

![inventory-rules-list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-92948a58-126d-2ee1-cf78-2e620b9cba61.png)
7. On the inventory rule details page, record the following to use later for native inventory credentials while activating the connector.
  - Inventory Container
  - Inventory Rule Name
8. Proceed to [Using Storage Account authentication](/v1/docs/using-storage-account-authentication) or [Using Service Principal authentication](/v1/docs/using-service-principal-authentication).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

## Related

- [Configuring Data Inventory Sync for Azure Blob Storage (Self-hosted)](/configuring-data-inventory-sync-for-azure-blob-storage-self-hosted.md)
- [Data Inventory Sync and Entitlement Scan for data systems](/data-inventory-sync-for-self-hosted-connectors.md)
