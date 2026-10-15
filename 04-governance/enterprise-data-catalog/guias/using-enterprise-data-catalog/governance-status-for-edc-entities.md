---
title: "Governance status for EDC entities"
slug: "governance-status-for-edc-entities"
updated: 2026-07-22T09:03:41Z
published: 2026-07-22T09:03:41Z
canonical: "helpcenter.securiti.ai/governance-status-for-edc-entities"
stale: true
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Governance status for EDC entities

**Scenario**

As a compliance officer, you need to track which data assets meet internal standards and regulatory requirements. Without clear governance labels, it is hard to verify data status during audits. Using governance statuses and flags, you can mark datasets as Draft, Under Review, or Certified, and flag assets with PII, CDE etc. This streamlines audits and strengthens compliance oversight.

You can update the governance status of the Enterprise Data Catalog entities. This data governance capability lets you manage risk regarding data and makes sure that data is properly sourced, stored, handled and consumed.

To perform actions on Governance Statuses, enable the corresponding permission(s) for the required operation. Only the permission(s) associated with the action you intend to perform are required. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

- Update Data Product Governance Status
- Update Dataset Governance Status
- Update Glossary Node Governance Status
- Update Glossary Term Governance Status

To update governance status:

1. Open **Enterprise Data Catalog**, then choose dataset/glossary term/glossary node/data product.

> [!NOTE]
> **Note**
> 
> Currently, you can update the governance status for the following entities.
> 
> - Datasets
> - Glossary terms
> - Glossary nodes
> - Data products
2. Click **Options** (three dots) > **Update Governance Status**.
3. On the **Update Governance Status** popup, select any one status.

![EDC_governance_status.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1a140b33-4263-d950-6491-79dbe90c8abd.png)

You can view and choose from the following governance statuses for the entities.

| Governance status | Description |
| --- | --- |
| Draft | The data entity is in the initial stages of creation or modification. |
| Under review | The data entity is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The data entity has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
| None | The data entity does not have a defined governance status. |

> [!NOTE]
> Note
> 
> Custom governance statuses are currently not supported. You can only use the predefined governance statuses available in EDC.

1. Click **Update**.

At the right side of the dataset, you can view the updated governance status. You can hover over the status to view its details.

![EDC_-_Gov_status_-_B.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ca60288f-3c05-473b-6e6b-4cdf1d34a917.png)

> [!NOTE]
> **Note**
> 
> Only admins and entity owners can view and update the governance status of the entity.

### Default governance status for metadata ingestion to EDC

You can set a default governance status for all metadata ingested during the Sensitive Data Intelligence scan process. This streamlines the governance workflow, saving valuable time and ensuring consistency across metadata management practices.

To set the default governance status:

1. Open **Enterprise Data Catalog**, then choose **Settings > Scan Definitions**.
2. Click **Create Discovery Scan** and fill in the details to suit.
3. Scroll down to the **Register data assets into the Data Catalog** section and enable it.
4. From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.

You can select any of the following governance statuses for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |

> [!NOTE]
> **Note**
> 
> You can also update the metadata governance status when ingesting datasets using the [streaming dashboard](/latest/docs/using-the-streaming-data-discovery-dashboard) or the [structured dashboard](/latest/docs/using-the-structured-data-discovery-classic-dashboard).

### Governance status insights in audit trails

You can view comprehensive insights about how an asset governance status has changed over time. This helps you make informed decisions and better manage your assets.

Currently, you can view governance status in audit trails for:

- Glossary terms
- Datasets

You can view the following audit trail details:

| Value | Description |
| --- | --- |
| Time | Time when each change occurred. |
| User | Name of the user responsible for the change. |
| Activity | Nature of the modification, for example, add. |
| Attribute | Specific aspect of the asset that changed. |
| New value | Updated governance status |
| Old value | Previous governance status. |
| Message | Additional context through accompanying messages. |

### Governance flags for EDC entities

You can set the governance flags of the Enterprise Data Catalog entities. This lets you quickly identify which assets are critical and which ones contain PII.

To perform actions on Governance Flags, enable the corresponding permission(s) for the required operation. Only the permission(s) associated with the action you intend to perform are required. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

- Edit Dataset Column Governance Flag
- Update Dataset Governance Flag
- Update Glossary Node Governance Flag
- Update Glossary Term Governance Flag

Currently, you can set the governance statuses for the following entities.

- Datasets
- Dataset schema field
- Glossary terms
- Glossary nodes

To set governance flags:

1. Open **Enterprise Data Catalog**, then choose dataset/glossary term/glossary node.
2. Click **Options** (three dots) > **Add Governance Flag**.

> [!NOTE]
> **Note**
> 
> To set the governance flag to the dataset schema field:
> 
> - Near the right corner of the dataset schema field, click **Options** (three dots) > **Add Governance Flag**.
3. On the **Add Governance Flag** popup, select the governance flag from the menu.
4. Click **Save**.

Currently, you can select the following governance flags for the entities:

| Governance flag | Description |
| --- | --- |
| CDE | This flag indicates that the asset is a critical data element. |
| PII | This flag indicates that the asset contains PII. |

> [!NOTE]
> **Note**
> 
> - You can also mark assets with both PII and CDE flags to enhance data governance efforts by providing a clear indication of which assets contain the most sensitive and critical information.
> - Custom governance flags are currently not supported. You can only use the predefined governance flags available in EDC.

#### Filtering assets flagged with PII and CDE

You can filter assets flagged with PII and CDE in the following two ways:

1. Search bar
  1. Enter PII and/or **CDE** in the search bar.
  2. Press enter to see the filtered assets with PII or/and CDE flags.
2. Filters sidebar
  1. On the left-hand side of search results, scroll down the filters sidebar to the **Governance Flag** and **Schema Governance Flag** options.
  2. Expand these options and mark the **PII** and/or **CDE** checkboxes to filter assets.

#### PII flags for dataset schema fields

Securiti automatically sets the PII flags to the datasets schema fields in EDC at the time of registration that have been classified with data elements containing personal data. This ensures that any data element classified as containing Personal Data is automatically recognized and appropriately flagged, significantly easing compliance burdens.

View PII flags for dataset schema fields:

1. In Enterprise Data Catalog, open **Datasets**.
2. Click on the data system folder and subfolders to open a table to see the detailed information.
3. Under the **Schema** tab, you can view the governance flag column updated with the PII flag.

## Related

- [Datasets](/datasets.md)
- [Glossary terms](/glossary-terms.md)
- [Data products](/data-products.md)
