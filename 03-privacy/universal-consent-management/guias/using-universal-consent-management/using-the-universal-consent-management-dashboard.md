---
title: "Using the Universal Consent Management Legacy Dashboard"
slug: "using-the-universal-consent-management-dashboard"
updated: 2026-07-08T08:59:07Z
published: 2026-07-08T08:59:07Z
canonical: "helpcenter.securiti.ai/using-the-universal-consent-management-dashboard"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Universal Consent Management Legacy Dashboard

**Scenario**

As a Data Privacy Officer, you need clear visibility into consent activity to identify gaps, regional differences, and low acceptance rates early, but scattered data makes this difficult. For example, you may notice that consent acceptance is high in one region but significantly lower in another, or that a specific purpose is often declined. The Legacy Universal Consent Management Dashboard gives you a centralized view of consent activity, helping you spot issues quickly, improve consent flows, optimize for different regions, and strengthen compliance and audit readiness.

The consent management dashboard shows your consent posture at a glance. To open the consent dashboard, in Securiti, open **Universal Consent Management**. The dashboard opens by default.

![UCM_Dashboard_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4f188c82-252d-79ba-6bac-9c8280ad7ac9.png)

- Use the filters tools near the upper right corner of the page to filter the dashboard on various criteria. See [Filtering universal consent](/v1/docs/filtering-universal-consent) for more information.
- The **Consent Overview** widget near the upper left corner shows your consent granted metrics for both cookie and form consent.
- The **Consent Status** graph along the top shows the trend line for form consent. Hover over points on the graph for details.
- The Sankey chart correlates consent types and categories with their status for form consent. Hover over columns or branches of the chart for details. Click on columns to filter the entire dashboard on that category or status. To clear filters, open the filters panel and click **Clear all filters**.
- The **Consent by Residency** map shows you consent metrics by geographic location for form consent. Hover the mouse pointer over a country on the map to view consent metrics for it.
- The **Consent Records** table near the bottom of the page shows records of every event in which website visitors granted, declined, or withdrew form consent. Click **Details** near the upper right corner of the table, then click a record to view details for it.

> [!NOTE]
> **Note**
> 
> When Securiti receives a universal consent call that does not contain a UUID, it now stores the consent record with an automatically-generated subject identifier. You can use the consent record information to identify and resolve the issue that caused the UUID absence.
- You can view the details of a particular consent record by clicking on the **Eye** icon on the top right of the consent records table and then clicking on the consent record as shown below.

![UCM_Dashboard_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8cf7ebd2-33e7-4116-b279-f129649107a2.png)
- Securiti displays the empty values in the **Geolocation** column with **-** (hyphens). If you are using the downloaded consent records in your systems, we recommend that you **recheck** the empty values of **Geolocation** column, and set them with hyphens.

### Deleting consent records from the dashboard

You can delete consent records from the Consent Records table near the bottom of the page. The delete icon only appears when there are records available in the dashboard. Securiti maintains audit logs for both successful and aborted consent records deletions. The respective admin of the tenant receives an email when records are deleted from the dashboard. Only the following roles have the permission to delete the consent records:

- Super Admin
- Organization Admin
- Module Owner

> [!NOTE]
> **Note**
> 
> This feature is available by subscription. Contact the Customer Success Manager or Account Representative to include in your plan.

To delete the consent records:

1. On the Universal Consent dashboard, from the upper right side of the consent records table, click **Delete** icon as shown below.

![UCM_Dashboard_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c34e912-b70d-7f61-6a7c-dbaf44b10d4f.png)
2. On the popup, write the appropriate reason to delete the consent records in the text field, then click **Delete Consent Records** to delete the consent records from the dashboard as shown below.

![UCM_Dashboard_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa9f982a-12c9-48d4-9cc6-45415f28e39c.png)

> [!NOTE]
> Note
> 
> Securiti supports deleting up to 5 million consent records per operation.
> 
> For stable and reliable performance, follow these guidelines:
> 
> - Filter and delete a limited number of UUIDs at a time.
> - Break large deletion requests into smaller batches.
> - Run deletion queries sequentially to ensure stable processing.
> - Use shorter deletion timeframes (1-2 months) for substantial data volumes.
3. Near the bottom of the popup, click **Cancel** to abort the deletion of consent records.

## Migrating consent records from legacy to new universal consent dashboard experience

To use the new **Universal Consent Dashboard & Metrics** experience, you must migrate your existing consent records from the legacy dashboard.

When you migrate, your historical consent data is moved into the new analytics framework, so you can take advantage of advanced filtering, improved performance, and the new consent metrics widgets.

> [!WARNING]
> Important
> 
> The data migration runs in the background and may take several hours depending on data volume. Once the migration starts, you cannot pause or cancel it.

To migrate the date from legacy to the new dashboard:

1. In **Universal Consent Management**, open the **Legacy Universal Consent Data**.
2. Near the top of the page, click **Begin your consent data migration here** in the banner.
3. Open Universal Consent **Module Configurations.** Below the **Universal Consent Data Migration** section, select the time range of consent data to migrate from the **Data Migration Period** menu.
4. To initiate the consent data migration, click **Start Migration**, as shown below.

![Universal Consent Management settings with options for data migration and consent configurations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/legacy_1.png)
5. (Optional) Review the **Migration Summary** to track migration progress. The summary shows the migration start time, estimated completion time, total and completed batches, and the number of consent records migrated.

The progress status updates automatically at regular intervals while the migration runs in the background.

After the migration completes, you can view the migration status on the **Module Configurations** page in the Universal Consent Data Migration section. This section provides a complete migration summary. You can also click View New Dashboard to navigate to the Universal Consent Dashboard & Metrics experience, as shown below.

![Summary of Universal Consent Data Migration with key details and completion status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/legacy_2.png)

You can also confirm that the migration has completed from the **Legacy Universal Consent Data** page. Near the top of the page, a notification banner appears indicating that your universal consent data has been completely migrated, as shown below.

![Notification about migration of universal consent data to a new dashboard experience.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/legacy_3.png)
6. Click **View it in the new** **Universal Consent Dashboard & Metrics** experience in the banner to open the new dashboard and metrics pages and begin reviewing migrated consent data.

Sankey chart or diagram is a visualization used to depict a flow from one set of values to another. The things being connected are called nodes, and the connections are called links.

Universally Unique Identifier (UUID) is an alphanumeric string that is used to identify information in computer systems. For instance, they are often used to identify rows of data within a database table, with each row assigned a specific UUID.

## Related

- [Downloading universal consent records from the Legacy Dashboard](/downloading-the-universal-consent-records.md)
- [Filtering universal consent records in the Legacy Dashboard](/filtering-universal-consent.md)
