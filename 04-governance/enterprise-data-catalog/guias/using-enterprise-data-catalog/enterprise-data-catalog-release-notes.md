---
title: "Enterprise Data Catalog release notes"
slug: "enterprise-data-catalog-release-notes"
updated: 2026-09-21T21:00:01Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/enterprise-data-catalog-release-notes"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Enterprise Data Catalog release notes

## 1.151

### Release updates - September 2026

#### Revamping the EDC Ingestion experience

Securiti has revamped the EDC Ingestion experience so you can set up and monitor a metadata ingestion source without writing a recipe by hand.

![Securiti dashboard showing integrations and data system types with highlighted EDC Sources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 4.31.09 PM(1).png)

The updated experience includes the following:

- A full-page setup form with grouped sections and helper text under each field, replacing the previous popup, so optional settings are easier to find.
- A split view that shows the form alongside the underlying configuration and keeps the two in sync as you work.
- Authentication through form fields rather than a `YAML` recipe.
- A connection test for some connectors that reports each connectivity check.
- A run history for each source, with filters and the option to roll back a run to remove the metadata it ingested.

![Overview of Databricks Unity Catalog with Ingestion History details displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ingestion history.png)

- Run details across tabs for ingested assets, statistics, logs, and the recipe used.
- Updated configurations for every supported source, each documented in the Securiti Help Center instead of referring you to third-party documentation.

> [!NOTE]
> Note
> 
> The classic EDC Ingestion flow is still available under **EDC > Settings**. The new experience is available only under **Integrations**.

For more information, see [EDC sources](/latest/docs/using-edc-sources).

---

## 1.150

### Patch 1 updates - September 2026

#### Resolved issue

- Fixed an issue where re-running a discovery scan reset a dataset's metadata to what the scan detected, removing metadata added through dataset import or EDC Ingestion. After re-running a discovery scan, re-run the dataset import and EDC Ingestion in their original order to restore the overwritten metadata (PRIV-257885).

### Release updates - August 2026

#### Viewing the change log for Domains

Securiti now lets you view the change log for domains in EDC, extending the existing change log functionality previously available only for datasets and glossary terms. The change log provides you a complete history of all changes made to a domain, including what was changed, who made the change, and when it occurred. This provides greater visibility into domain activity and helps you track modifications over time for governance and auditing purposes.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5J6BAZBZ.png)

For more information, see [Domains](/latest/docs/domains).

#### Populating web link for tags in Graph Explorer

Securiti now correctly populates the **Web Link** column for tags in Graph Explorer during ingestion in EDC. Previously, the **Web Link** column displayed a dash for all tag entities, even when a web link value was available from the source system. With this update, Securiti accurately maps and displays web link values ingested from the source in the **Web Link** column, giving you better traceability and navigation back to source-system tag definitions.

![Graph Explorer interface displaying tags and their corresponding data catalog URNs.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Tags - Graph Explorer .png)

For more information, see [Graph Explorer](/latest/docs/using-graph-explorer).

---

## 1.149

### Release updates - July 2026

#### Exporting the EDC Dashboard as a PDF

Securiti now lets you export the EDC Dashboard as a PDF. You can export the entire dashboard view, including the tile matrix and all charts, making it easier to share catalog insights and report on governance status across your organization. To export the dashboard, apply the desired filters, then click the **Options** (three dots) menu in the upper-right corner of the page and select **Generate PDF**. Securiti generates a PDF file containing the current dashboard view for you to download

The generated PDF reflects your selected UI language. Supported languages include English, Portuguese, French, Italian, Spanish, German, Japanese, Arabic, Norwegian Bokmål, and Indonesian.

![Overview of data catalog showing domains, platforms, and data quality scores.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Generate PDF(1).png)

For more information, see [EDC Dashboard](/latest/docs/edc-dashboard-new-experience).

#### Honoring RBAC permissions in EDC exports

Securiti now enforces RBAC permissions during exports in EDC. Previously, exports included all entities regardless of your permissions, meaning you could export data you were not authorized to view. With this update, the export file includes only the entities you have permission to view. Securiti automatically excludes entities outside your access from the export.

> [!NOTE]
> Note
> 
> This applies to all EDC export types, including dataset, data product, and glossary term exports.

For more information, see [Enterprise Data Catalog RBAC permissions and roles](/latest/docs/edc-rbac-permissions-and-roles).

#### Deleting child glossary terms when a glossary node is deleted

Securiti now automatically deletes all child glossary terms when their parent glossary node is deleted. Previously, deleting a glossary node promoted its child terms to the root level, leaving orphaned terms across your glossary structure.

For more information, see [Glossary terms](/latest/docs/glossary-terms).

### Resolved issue

- Fixed an issue where structured properties were missing from data product export files in Enterprise Data Catalog (PRIV-190407).

---

## 1.148

### Patch 1 updates - June 2026

#### Granular permissions for glossary term, node, and data product read-only status

Securiti now uses separate permissions to control who can mark glossary terms, glossary nodes, and data products as read-only. Previously, one permission, Edit Dataset Read-Only Status, controlled this for all four entity types. Three new permissions now handle this independently:

- Edit Data Product Read-Only Status
- Edit Glossary Node Read-Only Status
- Edit Glossary Term Read-Only Status

Edit Dataset Read-Only Status now applies to datasets only. You need the permission matching an entity's type to use Mark as Read Only / Mark as Editable on it; otherwise the option is disabled.

> [!NOTE]
> Note
> 
> Roles that only had Edit Dataset Read-Only Status need the new permissions added to retain control over the other entity types.

For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

### Release updates - June 2026

#### Marking glossary terms, nodes, and data products as read-only

Securiti now lets you mark glossary terms, glossary nodes, and data products as read-only, extending the existing read-only functionality previously available only for datasets. You can mark an entity as read-only from its details page by selecting **Mark as Read Only** from the **Options (three dots)**. Once marked as read-only, none of the entity's attributes can be edited, helping you maintain data integrity and ensure consistent governance across your data catalog. To make a read-only entity editable again, select Mark as Editable from the same path.

> [!NOTE]
> Note
> 
> - To use this feature, your role requires the **Edit Dataset Read Only Status** permission. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).
> - Read-only status is not inherited. If you mark a term group as read-only, the glossary terms within that group are not automatically marked as read-only. You must mark each term individually.

For more information, see [Glossary terms](/latest/docs/glossary-terms) and [Data products](/latest/docs/data-products).

#### Preventing duplicate glossary node names

Securiti now validates glossary node names upon creation in Enterprise Data Catalog to ensure each node has a unique name. If you attempt to create a glossary node with a name that already exists, Securiti displays an error message indicating that the name must be unique. This helps you maintain a well-organized and unambiguous glossary structure across your data catalog.

For more information, see [Glossary nodes](/latest/docs/glossary-terms).

#### Filtering the EDC Dashboard by domain and owner

Securiti now lets you filter the EDC Dashboard by **D****omain** and **Owner**, as shown below. Both filters support search, making it easier to locate specific domains or owners within large datasets. When a filter is applied, it updates all sections of the dashboard, including the tile matrix and all charts, giving you a focused view of your data catalog based on the criteria you select.

![Dashboard displaying data catalog metrics, including domains, platforms, and data quality scores.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Final - Domain (1).png)

![Data catalog interface showing owner selection and total domains and platforms statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Owners(1).png)

For more information, see [EDC dashboard](/latest/docs/edc-dashboard-new-experience).

#### Expanding Azure Blob Storage file type support

Securiti has expanded file type ingestion support for Azure Blob Storage. Previously, only CSV and JSON files were supported for metadata ingestion via the discovery scan. With this update, Azure Blob Storage now supports ingestion of all file types, consistent with the existing behavior for Amazon S3 and OneDrive data systems.

For more information, see [Metadata registration in EDC](/latest/docs/registering-metadata-into-the-enterprise-data-catalog).

#### Renaming EDC permissions to ownership types

Securiti now identifies the **EDC Permissions** section and page as **Ownership Types**, accurately reflecting that this section configures ownership types rather than general permissions.

For more information, see [Ownership types](/latest/docs/edcownership).

#### Introducing dedicated execute permissions for Data Quality Checkpoints and Inferred Lineage

Securiti now provides dedicated execute permissions for **Data Quality Checkpoints** and **Inferred Lineage** in EDC.

The newly added permissions are as follows:

| Permission | Description |
| --- | --- |
| Execute data quality checkpoint | Lets you execute data quality checkpoints. |
| Execute inferred lineage | Lets you execute inferred lineage. |

Previously, roles with create access could also trigger execution, even when that was not intended. With this update, execution is controlled by separate, dedicated permissions, giving you more precise control over what each role can do.

> [!NOTE]
> Note
> 
> This change affects existing role configurations. You must update any roles that previously used create permissions for execution to include the new dedicated execute permissions.

For more information, see [Data quality checkpoints](/latest/docs/dqcheckpoints) and [Inferred lineage](/latest/docs/inferred-lineage).

#### Resolved issues

- Fixed an issue where exporting datasets or glossary terms in Enterprise Data Catalog failed to complete and the export email was not delivered (PRIV-243591, PRIV-244881).
- Fixed an issue where the dataset profile and schema tabs in Enterprise Data Catalog rendered as a blank page when the UI language was set to Portuguese (PRIV-246318).
- Fixed an issue where glossary terms imported via the import feature were not showing in the Related Terms tab in Enterprise Data Catalog (PRIV-246619).
- Fixed an issue where the glossary term count in the Enterprise Data Catalog export did not match the count shown in Graph Explorer, resulting in some glossary terms being missing from the export (PRIV-246980).

---

## 1.147

### Release updates - June 2026

No updates.
