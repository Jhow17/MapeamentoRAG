---
title: "Filtering the DSR Dashboard"
slug: "filtering-the-dsr-dashboard"
status: "update"
updated: 2026-09-22T08:33:30Z
published: 2026-09-22T08:33:34Z
canonical: "helpcenter.securiti.ai/filtering-the-dsr-dashboard"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Filtering the DSR Dashboard

You can use DSR filters to enhance the filtering experience, and significantly simplify the process of locating DSR requests. You can also save your search filters for later use and edit them as needed.

There are two tiers of search now: the top-level and the DSR requests list filter.

### Top-level filter

With the top-level filter, you can filter both the DSR requests list and data within widgets. This type of filtering lets you combine different properties such as DSR ID, Country of Residency, DSR Progress, etc. using both AND and OR operations. The top-level filters take precedence and dictate the behavior of everything beneath them, filtering all data from the top down, affecting both widgets and the grid view. In contrast, the DSR requests list filters exclusively filter data within the grid and do not impact widgets.

> [!NOTE]
> **Note**
> 
> The top-level filter persists when you refresh the page or navigate elsewhere to maintain state across different views or sessions. This means you do not have to repeatedly set the same filters each time you access the dashboard or navigate between different pages.

To apply the filter:

1. On the **DSR Dashboard**, click **+** (Add icon) near the upper left corner of the page to open the filters panel, as shown below.

![SS1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2aa238bb-d0e0-9c3e-b156-7bff9f3f3006.png)
2. Click on the DSR property like **DSR Owner, Country of Residency,** etc., and choose values from its respective expanded menu. Click **Apply** to filter widgets and the DSR Requests list, eliminating those items or elements that do not meet the criteria.

> [!NOTE]
> **Note**
> 
> To apply text-based filters (e.g., Data Subject Name, DSR Request ID) on the DSR Dashboard, type the text in the search bar, press Enter, and click **Apply**.
> 
> ![Screenshot_2024-08-01_at_7_17_58_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-514c24f5-ef03-3c60-6107-08296737f688.png)

You can filter both custom and system DSR requests using these top filters. The **Request Type** filter option displays the labels you defined on the [Request Types page in DSR settings](/v1/docs/configuring-dsr-request-types).

![Screenshot_2024-12-24_at_12_40_18_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cda885fa-b987-9cfe-e37b-c5db2f6186d9.png)

You can use the *subtask Response Status* filter to find requests with subtasks in “No Data” found status but only if those subtasks are retained.

> [!NOTE]
> **Note**
> 
> - If all “No Data” found subtasks for a request are suppressed by DSR Automation, Securiti applies a User not found tag to the request card in the DSR Dashboard. These requests cannot be filtered using the *subtask Response Status* filter
> - If the subtasks are retained, the tag is not shown, and the filter works as expected.
> 
> ![Screenshot_2025-04-24_at_4_02_24_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ed16bc15-38e4-2329-c0a6-ca4d3b81da61.png)
3. If you want to add another filter, click **option** (3 dots) next to the filter applied and click **Add Property**, and repeat step 2.

![s2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-61419609-4bd5-5868-bc8a-927e6ff72a67.png)

> [!NOTE]
> **Note**
> 
> When a top-level filter is applied, the corresponding filter at the requests list is grayed out or disabled. Similarly, when you apply the "Deadline" filter at a top-level, the calendar widget becomes fully disabled, meaning you cannot click on calendar dates.
> 
> ![Screenshot_2024-02-25_at_10_21_18_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f622fc56-43cd-e062-2e41-1281fa8fb265.png)

You can apply OR and AND filters on DSR request properties to filter and query DSR records as needed. The choice between using OR and AND filters depends on the specific requirements of the desired outcome of your query.

- OR filters are used when you want to retrieve records that meet at least one of the specified DSR filter conditions.
- AND filters are used when you want to retrieve records that meet all of the specified conditions simultaneously.

![S3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-48174c19-4a1e-3641-67ad-0d74d0d871b9.png)

> [!NOTE]
> **Note**
> 
> If appeal support is enabled for your tenant, you can also use the DSR filters for locating appeals associated with a particular DSR request. You can hover over the dates highlighted in orange on the calendar to view the count of appeal requests due on those specific dates. You can also click on the respective due date to filter out appeals.
> 
> ![S4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-301bb8d2-e554-218e-44d0-638103eef44e.png)

### DSR Requests list filter

Using the DSR requests list filter, you can select various filter options to specify the criteria by which you want to filter the requests list . Clicking any of the filter options opens its respective menu, displaying a list of values that you can choose from. Once the filter is applied, the DSR Requests list updates to display only the requests that meet the specified criteria. This filter doesn’t affect the data showcased in the widgets.

To apply the filter:

1. In the middle of the page, on the DSR Requests list, specify criteria by clicking a DSR property and selecting desired values from its respective menu.

![S5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9960899-9df9-2b3a-93c7-ed9a612db63a.png)
2. Once you apply the filter, it will update the DSR Requests list to display only the requests that meet the specified criteria.

> [!NOTE]
> **Note**
> 
> The DSR requests list filters persist when you refresh the page or navigate elsewhere to maintain state across different views or sessions. This means you do not have to repeatedly set the same filters each time you access the dashboard or navigate between different pages. Moreover, for users with user and guest roles, the DSR subtask owner filter on the DSR Dashboard only works with the email address of the logged-in user and does not fetch DSRs for any other email addresses.

### Searching DSR requests

You can use the search bar in the middle right side of the page to quickly locate DSR requests by entering either the DSR ID, the data subject's name, or their email address.

> [!NOTE]
> **Note**
> 
> Consider the following points when using this feature:
> 
> - Searching DSR requests with email addresses containing underscores (e.g., *john_doe@gmail.com*) may return unintended results. To ensure precise matches, simply prepend the underscore with a backslash in your query: *john\_doe@gmail.com*.
> - When searching DSR requests by a data subject's name, if the name contains more than two words, the last word is interpreted as the last name, and all preceding words are treated as the first name. For instance, in "John Michael Carter," the last name is "Carter," and the first name is "John Michael."

### DSR Metrics

You can also view a set of metrics on the DSR Dashboard giving you information about DSR requests. These stats dynamically change with each applied filter.

![S6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a6915a52-5304-a943-6a18-4536f361d1d0.png)

| DSR Metrics | Description |
| --- | --- |
| Active DSR Requests | Total count of active DSR requests. |
| Completed DSR Requests | Completed DSR Requests |
| Overdue DSR Requests | Total count of DSR requests that are overdue |
| Residencies | Total count of residencies of data subjects whose requests have been received. |
