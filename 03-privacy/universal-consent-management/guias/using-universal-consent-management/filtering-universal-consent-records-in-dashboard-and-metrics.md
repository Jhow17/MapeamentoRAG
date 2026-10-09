---
title: "Filtering universal consent records in the Dashboard and Metrics"
slug: "filtering-universal-consent-records-in-dashboard-and-metrics"
updated: 2026-04-28T09:58:44Z
published: 2026-04-28T09:58:44Z
canonical: "helpcenter.securiti.ai/filtering-universal-consent-records-in-dashboard-and-metrics"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Filtering universal consent records in the Dashboard and Metrics

The Universal Consent Dashboard & Metrics offers granular filters that let you refine and narrow down the consent data displayed. You can use these filters to quickly narrow your view to the most relevant records, identify patterns, and focus on key insights.

To use the top-level filters:

1. In Securiti, open Universal Consent Management and choose **Dashboard & Metrics**. The Dashboard tab opens by default.
2. Near the upper left corner of the **Dashboard** or **Metrics**, click **+** (plus icon), as shown below.

![Dashboard displaying universal consent data, including consent given dates and statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_filters_1.png)

> [!TIP]
> Tip
> 
> You can apply multiple filters at the same time to further refine the results.
3. From the filters panel, apply one or more filters using the following properties.

| Property | Description |
| --- | --- |
| Consent Given Date | Filters consent records by the date and time a data subject provides consent. You can filter consent records using the following operators: - **between** to select a date range - **in the last** to filter the predefined time durations such as 24 hours, 7 days, 30 days or 1 year. |
| Country | Filters consent records by country. You can apply the following operator to filter consent records: - **is one of** to select one or more countries from the provided country list or use the search option |
| IP Address | Filters consent records by the data subject’s IP address. You can filter consent records using the following operator: - **starts with** to match IP address prefixes |
| Consent Stored Date | Filters consent records by the date and time Securiti stores consent. You can filter consent records using the following operators: - **between** to select a date range - **in the last** to filter the predefined time durations such as 24 hours, 7 days, 30 days or 1 year. |
| Consent Purpose | Filters consent records based on the data subject’s consent purpose. You can filter consent records using the following operators: - **contains** to match specific keywords - **starts with** to match values that begin with a specific prefix For more information, see [Configuring processing purposes and consent purposes](/latest/docs/configuring-processing-purposes-and-consent-purposes). |
| Consent Status | Filters consent records by their current state, such as **Granted**, **Declined**, **Pending**, **Withdrawn**, or **No Consent**. You can apply the following operator to filter consent records by Consent Status: - **is one of** to select one or more consent states |
| Custom Parameter Key | Filters consent records by a custom parameter key (case-insensitive). You can filter consent records using the following operators: - **is equal to** - **contains** - **starts with** For more information, see [Configuring custom parameters](/latest/docs/configuring-custom-parameters). |
| External ID - CP | Filters consent records by the Consent Purpose External ID. You can filter consent records using the following operators: - **contains to** match specific keywords - **starts with** to match values that begin with a specific prefix |
| External ID - PP | Filters consent records by the Processing Purpose External ID. You can filter consent records using the following operators: - **contains** to match specific keywords - **starts with** to match values that begin with a specific prefix |
| Processing Purpose | Filters consent records based on the specific processing purpose for which a data subject provides consent. You can filter consent records using the following operators: - **contains** to match specific keywords - **starts with** to match purposes that begin with a specific prefix For more information, see [Configuring processing purposes and consent purposes](/latest/docs/configuring-processing-purposes-and-consent-purposes). |
| Processing Purpose Categories | Filters consent records by processing purpose category. You can filter consent records using the following operators: - **contains** to match specific keywords - **starts with** to match categories that begin with a specific value For more information, see [Processing purpose categories](/latest/docs/processing-purpose-categories). |
| Route | Filters consent records by the consent collection route, such as Forms, Bulk Upload, Preference Centers, Consent Narrow Path, Platform Integrations or Consent APIs. You can filter consent records using the following operator: - **is one of** to select one or more collection routes |
| Rules Matrix | Filters consent records based on the application of a rules matrix. You can use the following operators to include or exclude records based on the **Enable** or **Disable** status: - **is equal to** to include matching records - **is not equal to** to exclude matching records For more information, see [Using the Rules Matrix](/latest/docs/using-the-rules-matrix). |
| Source | Filters consent records by the consent capturing source, such as a preference center or consent form. You can filter consent records using the following operator: - **contains** to match specific source values |
| Subject Identifier Key | Filters consent records by the unique subject identifiers, such as `email`, `uuid`, `name` or `phone`, as shown below. ![Universal Consent Dashboard displaying consent records and filtering options for user identities.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/subject_identity_key.png) You can filter consent records using the following operators: - **is equal to** to match an exact key - **contains** to match partial key values - **starts with** to match keys that begin with a specific value For more information, see [Using unique Subject Identifier setting](/latest/docs/using-the-unique-subject-identifier-setting). |
| Subject Identity | Filter consent records using key-value pairs, where keys such as `uuid`, `phone`, or `email` correspond to values that identify the data subject. For instance, `email` is the key and `user@example.com` is the value, as shown below. ![Universal Consent Dashboard displaying consent records and subject identity search options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/subject_identity.png) You can filter consent records using the following operator: - **is equal to** to match specific key-value pairs > [!NOTE] > Note > > In key-value pairs, **keys are case-sensitive**, while values are not. |

For instance, to filter consent records by **Route** (property), from the left pane of the filter panel select **Route**, then from the right pane mark the checkboxes next to the desired route names, as shown below.

![Universal Consent Dashboard displaying consent data and filtering options for user management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_filters_2.png)
4. Repeat the same step for other properties to suit your search needs. Once you apply all required properties, near the bottom of the filter panel, click **Apply**, as shown below.

![User interface showing consent management options and an 'Apply' button for filtering data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_filters_3.png)

Securiti builds a query based on your selected properties and displays the filtered results.
5. To clear the top-level filter, from the upper right corner, click **Clear Search**, as shown below.

![Dashboard displaying universal consent data with filters for consent date and processing purpose.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_filters_5.png)

## Saving Views

You can save the applied filter to reuse it later.

To save a view for your set filters and search results:

1. Near the upper right corner of the **Dashboard** or **Metrics**, click **Save View**, as shown below.

![Dashboard displaying universal consent data, including consent status and processing purposes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_filters_6.png)
2. On the **Save View** panel, enter a **Name** and **Description**, and select a **Group** of views or add a new one. Then, at the bottom of the panel, click **Save View** to save your view, as shown below.

![Universal Consent Dashboard displaying consent records and filters for email marketing purposes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_filters_7.png)

## Using Saved Views

You can access and apply your saved views at any time through the **Saved Views** panel.

To use the saved views:

1. Near the upper right corner of the **Dashboard** or **Metrics**, click **Saved Views**, as shown below.

![Dashboard displaying universal consent records with consent statuses and processing purposes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_filters_8.png)

Clicking **Saved Views** opens a panel for saved filters on the left side. The panel displays saved groups and views, as shown below.

![Dashboard displaying saved views and consent records for email marketing purposes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_filters_9.png)
2. Click any group to view the list of saved views for that group.
3. Click the view name, or next to the view name click **Options** (three dots), and choose **View** from the menu to apply the saved filter, as shown below.

![User interface displaying consent records with options to view, edit, or delete entries.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_filters_10.png)

## Managing the Saved Views

To update a saved filters, their group, or the names and descriptions associated with them:

1. Near the upper right corner of the **Dashboard** or **Metrics**, click **Saved Views**.
2. From the **Saved Views** panel, next to the group name in the **Custom Views** tab, click **Options** (three dots), and choose **Rename** or **Delete** from the menu to apply the desired action, as shown below.

![Dashboard showing saved views with options to rename or delete consent records.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_filters_12.png)
3. Similarly, click any group to view the list of saved views. Next to the view name, click **Options** (three dots), and choose **Edit** or **Delete** from the menu to perform the desired action, as shown below.

![Overview of saved views with options to view, edit, or delete consent records.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_filters_13.png)

## Related

- [Downloading the universal consent records from the Dashboard and Metrics](/downloading-universal-consent-records-from-dashboard-metrics.md)
