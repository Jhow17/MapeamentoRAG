---
title: "tracking DSR requests using DSR dashboard"
slug: "using-the-data-subject-rights-dashboard"
status: "update"
updated: 2026-09-25T02:41:44Z
published: 2026-09-25T02:41:44Z
canonical: "helpcenter.securiti.ai/using-the-data-subject-rights-dashboard"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Using the Data Subject Rights Dashboard

The Data Subject Rights Dashboard shows your data subject rights posture at a glance. You use the DSR dashboard page to list DSR requests and monitor your overall DSR status.

To open the DSR dashboard, in Securiti, open **Data Subject Rights**. The dashboard opens by default.

At the top of the DSR dashboard, a row of dashboard widgets shows you the current status of your DSRs at a glance.

- Use the calendar widget at the left end of the dashboard to see what DSR requests are due within the current month. You can also select any date on the calendar to filter DSR requests and widget data. The navigation button on the calendar helps you switch between months and view DSRs scheduled for each month. You can also hover over the dates highlighted in orange on the calendar to view the count of DSR requests due on those specific dates.

![ss1_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0f7e66a-ccaa-280a-8ea8-f3ee9018afe1.png)
- The **Average DSR Resolution Time** widget illustrates the average time taken for DSR resolution, as well as the potential time savings achievable through DSR Automation. Securiti calculates the average value for “DSR Automation Time Saved” as follows:

![ss2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3321567-d7bd-ef1b-7644-2d3b63321b28.png)
  - In processing DSR tasks for **monitored scanless data systems**, automation saves 100% of the time for each task.
  - For tasks against **hybrid data systems**, automation saves 75% of the time for each task.
  - For **monitored scanned** data systems, automation saves 50% of the time.
- The widget below displays the ratio of open to closed DSRs, along with a trendline that indicates DSR request status over a month, three months, or a year.

![ss3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-246cf215-f767-f9b0-1f89-018e2088f445.png)
- Use the residency widget at the right end of the dashboard to quickly filter DSR requests geographically. Click a shaded area of the map to filter the table at the bottom of the page on that country or state.

![Screenshot_2024-03-06_at_10_29_27_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2153f90a-4798-9545-f814-2a3da113c380.png)

At the bottom of the page is the DSR requests table. This table lists cards for all DSR requests. Each card shows:

- DSR request ID number
- DSR Request ID

This ID matches the one shown to data subjects in the Privacy Central.
- Appeal
- Data subject name
- Request type(s)

The **Request Type(s)** column shows two values stacked vertically. The upper value shows the label of the custom or system request type selected by the data subject during DSR request submission, and the lower value reflects the corresponding label configured on the Request Types page.

![Screenshot_2024-12-23_at_8_58_47_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-76b9c0b4-2b6d-7df5-5fd5-1f0e06143850.png)
- Progress in terms of tasks completed versus total tasks
- Deadline

The deadline column in the DSR dashboard actively tracks the processing timeline for each request. The statuses displayed in this column use color codes to instantly convey the status of each request.
  - **Extended:** This status appears in blue to indicate that the deadline for processing a DSR request has been extended. You can set the DSR extension deadline while configuring the DSR form. For more information, see [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms).
  - **Overdue:** This status in red indicates that the response deadline set during the configuration of the DSR form has passed without the request being completed. For more information, see [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms).
  - If the deadline column displays the status in green, it indicates that the DSR request has been processed or completed.
- Date Completed

The “Date Completed” column in the DSR Dashboard actively tracks the completion of DSR requests. This column displays the date when a DSR request is completed.
- Residency of the data subject
- Total subtasks
- Approved subtasks
- Declined subtasks
- Error subtasks
- Subtasks in Review
- Message Count
- DSR request owner(s)
- Organization in which DSR is created
- Request Clarification

The Request Clarification column displays the following statuses:
  - **Not Initiated**: Clarification has not been requested, either manually or automatically.
  - **Awaiting Response**: DSR owners are waiting for a response from the data subject.
  - **Responded**: The data subject has provided the required additional information.

Click the card for a DSR request to open it and view it in the DSR workbench.

For DSR requests with multiple types, Securiti shows the DSR request type as "Multiple." Hover over the type to see a popup listing all the request types as shown below.

![Screenshot_2024-03-06_at_10_25_45_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b91df501-3968-6175-b26c-3d5ec8b41b2a.png)

> [!NOTE]
> **Note**
> 
> The sequence of DSR requests in the grid can change due to several factors. Submitting multiple requests to different organizations may affect the order. A database restart can also temporarily alter the sequence as the system refreshes. Additionally, if some DSR requests are deleted, it may impact the sequence.

### Pagination on DSR Dashboard

On the DSR Dashboard, you can use pagination options to quickly navigate through DSR requests.

At the bottom left corner, use the **Showing [number] per page** menu to choose your preferred number of requests to display on the dashboard with options for 25, 50, 75, or 100 requests.

![select_page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e0553569-6a8c-37cb-e748-c8f20b014ed1.png)

Further, at the bottom right corner of the DSR Dashboard, enter the page number to jump directly to the specific page.

![enter_page_for_dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-21ed6be3-2981-3b01-473a-d0d6db60d5b9.png)

> [!NOTE]
> Note
> 
> The DSR Dashboard retains the selected value in the Showing [number] per page menu when you navigate across the application and across sessions.

### Sorting DSR requests

Securiti admins can sort the DSR requests in ascending or descending order to organize them in a particular order. By default, Securiti sorts the DSR requests list by DSR ID but you can further sort it by following columns:

- DSR ID
- Appeal
- DSR Subject
- Date Created
- Date Completed
- Residency
- Organization

1. In the Data Subject Rights module, choose **Data Subject Rights** **> DSR Dashboard**.
2. Click on any of the column headers listed above to sort the requests list.

![Sorting_by_coumn.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0d580c8a-87f8-2d82-9d41-51e00eb0d70f.png)
