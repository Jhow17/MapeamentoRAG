---
title: "Using the Cookie Consent Management Legacy Dashboard"
slug: "using-the-cookie-consent-management-dashboard"
status: "update"
updated: 2026-09-22T09:51:01Z
published: 2026-09-22T09:51:28Z
canonical: "helpcenter.securiti.ai/using-the-cookie-consent-management-dashboard"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Cookie Consent Management Legacy Dashboard

**Scenario**

As a Data Protection Officer (DPO), you must manage multiple websites across departments. But without a central system to track ownership and privacy responsibilities, things become chaotic. With Securiti’s Cookie Consent Management module, you can add domains and assign owners directly. You ensure each website meets regulatory requirements from the start by establishing clear ownership.

> [!WARNING]
> Important
> 
> The new Cookie Consent Dashboard and Metrics experience is now available in the module. For more information on how to migrate your existing consent data to the new dashboard, see [Migrating consent records from Legacy to New Consent Dashboard Experience](/latest/docs/using-the-cookie-consent-management-dashboard#migrating-consent-records-from-legacy-to-new-consent-dashboard-experience).

The Cookie Consent Legacy Dashboard shows your cookie consent posture at a glance. To open the consent legacy dashboard, in Securiti, open **Cookie Consent Management** and choose **Legacy** **Cookie Consent Data**.

![Screenshot_2023-03-03_at_1_05_09_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1ea7e82f-fb3d-9500-99dc-cf348f68d46c.png)

- The Cookie Consent Legacy Dashboard is made up of several widgets. Each widget depicts certain statistics related to the consent rates. For instance, **Consent Rates** is a vertical widget on the left side of the dashboard that represents the following statistics, as shown below.

![Screenshot_2023-11-07_at_11_59_27_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-10f284fe-216d-109b-b815-4017fc10a947.png)

Table 1. Consent Rates Widget

| Consent Rate | Description |
| --- | --- |
| Action Rate | It shows statistics both in terms of percentage and the actual figure of **unique** data subjects who have interacted with the cookie banner and preference center of your website, and taken any of the following actions: - Granted consent to at least one or more non-essential cookie categories. - Declined or withdrawn consent. For instance, if two unique data subjects interact with your cookie banner and preference center on a given day by either granting or declining consent. In this case, the **Action Rate** parameter shows you 100% as a percentage, and 2 as the number of unique data subjects. You can consider the action rate as a sum of consent rate and decline rate. |
| Consent Rate | It shows statistics both in terms of percentage and the actual figure of how many **unique** data subjects have given their consent via the cookie banner and preference center of your website. For instance, if two unique data subjects interact with your cookie banner and preference center on a given day, and one gives consent while the other declines. In this case, the **Consent Rate** parameter shows you 50%, with one unique data subject granting consent out of the two. |
| Decline Rate | It represents statistics both in terms of percentage and the actual figure of how many **unique** data subjects have declined to give their consent via the cookie banner and preference center of your website. For instance, if two unique data subjects interact with your cookie banner and preference center on a given day, and one gives consent while the other declines. In this case, the **Decline Rate** parameter shows you 50%, with one unique data subject granting consent out of the two. |
| No Action Rate | It represents the number and percentage of unique data subjects who have yet to interact with the cookie banner and preference center of your website. For instance, it shows the percentage and number of unique data subjects who did not interact with your cookie banner and preference center over the selected date range. |
- The **Consent Rate Trendline** horizontal widget in the middle of the dashboard shows a seven days consent trendline. You can see the consent rate trendline of the last six days from the selected **To Date** (using the Custom Range filter) present under the **Date Created** filter in real-time through this widget as, shown below.

![Screenshot_2023-03-03_at_1_11_26_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-02e86a4f-9cfa-3d35-658a-38551ccb048c.png)

> [!NOTE]
> **Note**
> 
> If this feature is not available in your Securiti tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether it is included in your plan.

### Table 2. Consent Rate Trendline Widget

| Consent Rate | Description |
| --- | --- |
| Action | It shows the number of unique data subjects who encounter the cookie banner on the website and take any of the following actions: - Grant consent to at least one or more **non-essential** cookie categories. - Decline or withdraw consent. |
| Consent | It shows the total number of unique data subjects per day who **granted** consent for at least one non-essential cookie category. |
| Declined | It shows the total number of unique data subjects per day who **declined** consent for all non-essential cookie categories. |
| No Action | It shows the number of unique data subjects who encounter the cookie banner on the website, and do not interact with the banner on that same day. |
- You can also export the main dashboard widgets in a `PDF` document. Click **Export PDF** in the upper right corner of the cookie consent dashboard to export the widgets in the `PDF` document, as shown below.

![Screenshot_2023-03-03_at_12_21_58_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-78f40756-491e-6bbf-2332-338ec93e0b8c.png)

You must configure the following changes on the print page before saving the document.
  - Set the page size to **A4**
  - Set the margins field to **None**
  - Set the page layout to **Portrait**
  - Mark the **Background graphics** checkbox
  - Mark the **Print backgrounds** checkbox
  - Unmark the **Print headers and footers** checkbox
- Use the filters tools near the upper right corner of the page to filter the dashboard on various criteria. For more information, see [Filtering Securiti pages and dashboards](/v1/docs/filtering-securiti-pages-and-dashboards).
- There are a few filters that are strictly related to Cookie Consent module based on the consent data it possesses of a data subject.
  - You can use the **Subject Identity** filter by passing it the **Subject Identity** value from the Consent Records table, as shown below.

![Screenshot_2022-07-19_at_12_39_36_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52932179-b4b5-02b2-445c-37b7149d04b1.png)
  - Similarly, you can use the **Location Code** filter by passing it the value given in the **Location Code** column of the Consent Records table. Location Code is a URL of the website where the data subject gave their consent through the cookie banner.

![Screenshot_2022-07-19_at_12_41_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c7558fb3-9ba5-5c5f-afff-2293b28a9085.png)

![Screenshot_2022-07-19_at_12_42_22_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0c2ea484-6cc3-10bf-bbdc-098e9a845bd6.png)
- The Consent Overview widget near the upper left corner shows your consent granted metrics for the both cookie and form consent.
- The Consent Status graph along the top shows the trend line for the cookie. Hover over points on the graph for details.
- The Sankey chart correlates consent types and categories with their status for the selected consent type. Hover over columns or branches of the chart for details. Click on columns to filter the entire dashboard on that category or status. To clear filters, open the filters panel and click **Clear all filters**.
- The Consent by Residency map shows you Consent metrics by geographic location for cookie consent. Hover the mouse pointer over a country on the map to view consent metrics for it.
- The Consent Records table near the bottom of the page shows records of every event in which website visitors granted, declined, or withdrew consent of the selected type. Click **Details** near the upper right corner of the table as shown below, then click a record to view details for it. The table lists the following consent statuses:

| Status | Description |
| --- | --- |
| Granted | The data subject consented to cookies. |
| Declined | The data subject did not consent for the first time. |
| Withdrawn | The data subject withdrew their consent after earlier granting consent. This includes removing consent after an Implicit Consent. |
| No Action | The data subject took no action of accepting or declining cookies within a day. Securiti automatically omits No Action consents that are clearly caused by a bot, spider, or crawler visiting the page. > [!NOTE] > **Note** > > If this feature is not available in your tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. |

## Migrating consent records from Legacy to New Consent Dashboard Experience

To use the new Cookie Consent Dashboard and Metrics experience, you must migrate existing consent records from the legacy dashboard. The migration process moves historical consent data into the new analytics framework, enabling advanced filtering, improved performance, and access to the new consent metrics widgets.

> [!WARNING]
> Important
> 
> The data migration runs in the background and may take several hours depending on data volume. Once the migration starts, it cannot be paused or canceled.

### Procedure

1. In **Cookie Consent Management**, open the **Cookie Consent Legacy Dashboard**.
2. In the banner at the top of the page, click **Begin your consent data migration here**.
3. On the **Cookie Consent Configurations** page, below the **Cookie Consent Data Migration** section, select the time range of consent data to migrate from the **Data Migration Period** menu.
4. To initiate the consent data migration, click **Start Migration**.
5. (Optional) Review the **Migration Summary** displayed on the page to track migration progress. The summary shows the migration start time, estimated completion time, total and completed batches, and the number of consent records migrated. The progress status updates automatically at regular intervals while the migration runs in the background.

After the migration completes, you can view the detailed migration status on the **Module Configurations** page in the **Cookie Consent Data Migration** section. This section provides a complete migration summary, as shown below. You can also click **View New Dashboard** to navigate to the Cookie Consent Dashboard & Metrics experience.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Cookie-Consent-Data-Migration.png)

You can also confirm that the migration has completed from the **Legacy Cookie Consent Data** page. A notification banner appears at the top of the page indicating that your cookie consent data has been migrated, as shown below. Click **View it in the new Cookie Consent Dashboard & Metrics experience** in the banner to open the new dashboard and metrics pages and begin reviewing migrated consent data.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Consent-Data-Migrated(1).png)

A key role within your organization responsible for overseeing and ensuring compliance with data protection laws and regulations, such as the General Data Protection Regulation (GDPR) in the European Union. The primary responsibility of the DPO is to monitor the organization's data processing activities, assess potential risks to data subjects' privacy rights, and implement measures to mitigate those risks.

Sankey chart or diagram is a visualization used to depict a flow from one set of values to another. The things being connected are called nodes, and the connections are called links.

Consent metrics contain important statistics related to the consent decisions and preferences of your website visitors and data subjects.

Implicit consent means a data subject’s continued interaction with a website, such as browsing pages, clicking links, or using site features, is understood as consent to the configured cookie categories, where permitted by applicable law. This consent type is not suitable for jurisdictions that require clear affirmative consent before non-essential cookies or trackers run.

## Related

- [Filtering cookie consent records from the Legacy dashboard](/filtering-cookie-consent.md)
- [Collecting cookie consent](/collecting-cookie-consent.md)
