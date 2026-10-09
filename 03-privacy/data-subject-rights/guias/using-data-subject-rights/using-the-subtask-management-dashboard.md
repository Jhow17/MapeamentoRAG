---
title: "Using the subtask management dashboard"
slug: "using-the-subtask-management-dashboard"
status: "update"
updated: 2026-04-25T13:43:18Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/using-the-subtask-management-dashboard"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Using the subtask management dashboard

The Subtask Management dashboard shows you the status of subtasks assigned to you. You can apply filters to sort subtasks and also search specific subtasks or view them in the dashboard.

1. On the Securiti Dashboard view, click Data Subject Rights.
2. In the left sidebar, select **Data Subject Rights > Subtask Management**.

When you land on this page, by default Securiti filters the subtasks list by email address you used to log in. At the top of the page, use the search bar to quickly locate subtasks by entering either the DSR id, subtask id, subtask name, the data subject's name, or their email address.

### Filtering the subtasks list

Using the list filters, you can specify the criteria by which you want to filter the subtasks.

- Clicking any of the filter options opens its respective menu, displaying a list of values that you can choose from. Once the filter is applied, the subtask stats and list update to show only records that meet the criteria.

![Filtering subtasks from the subtask management dashboard.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-20 at 7.49.58 PM.png)

> [!NOTE]
> **Note**
> 
> The subtasks list filters persist when you refresh the page or navigate elsewhere to maintain state within a session and across views. This means you do not have to repeatedly set the same filters each time you access the dashboard or navigate between different pages. Moreover, for users with user and guest roles, the subtask owner filter only works with the email address of the logged-in user and does not fetch subtasks for any other email addresses.

Use the following table to understand the filter options and and their effects:

| Filter | Description |
| --- | --- |
| Subtask status | Lets you filter subtasks by status. For instance, you can filter all subtasks that are in error state and you need to investigate further. |
| System | Lets you filter subtasks created against different data systems involved in DSR processing. |
| Subtask Owner | Lets you filter subtasks assigned to specific owners. |
| Attachment | Lets you filter subtasks with attachments manually uploaded by co-owners or added by Securiti through DSR Automation. |
| Request Type | Lets you filter subtasks based on the request types. > [!NOTE] > **Note** > > The filter menu displays labels listed on the [Request Types](/v1/docs/configuring-dsr-request-types) page in DSR settings. |
| Jurisdiction | Lets you filter subtasks by jurisdiction, displaying only those associated with the selected region. |
| Subtask Deadline | Lets you filter the subtasks based on the deadline you set in the subtask template. |
| Subtask Created Date | Lets you filter the subtasks based on the created date of subtasks. |
| Subtask Closed Date | Lets you filter subtasks based on the closed date. |
| DSR Status | Lets you filter subtasks based on DSR request status. |
| DSR Due Date | Lets you filter subtasks by DSR due date. For instance you can filter out all subtasks belonging to different requests due in next 30 days. |
| DSR Owner | Lets you filter subtasks by DSR owners |
- You can use pagination options to quickly navigate through DSR subtasks. At the bottom left corner, use the **Showing [number] per page** menu to choose the number of subtasks to display on the dashboard with options for 25, 50, 75, or 100 subtasks. From the bottom right corner of the dashboard, use the menu to jump directly to the specific page.

![Screenshot_2025-03-02_at_7_01_58_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6e7f83bd-2ec4-6223-d3bd-232d9bd4a492.png)

> [!NOTE]
> Note
> 
> The subtask management dashboard retains the selected value in the Showing [number] per page menu when you navigate across the application and across sessions.
- View detailed metadata of subtask, as shown below.

![Showing subtask's metadata card](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-20 at 8.05.00 PM.png)

You can open a subtask to process it in the subtask workbench. For more information, see [Opening a subtask in the subtask workbench.](/v1/docs/opening-a-subtask-in-the-subtask-workbench)

### Exporting subtasks in CSV

You can export all or selected subtasks in CSV format. Securiti compiles them into a password-protected zip file and emails you a download link along with the password. The link expires after seven days. Apply filters to narrow down the subtasks for export.

1. In the Data Subject Rights module, choose **Data Subject Rights > Subtasks Management**.
2. Do the following:

A popup appears showing the number of subtasks you have selected. To export all subtasks present in the selected organization, mark **Select all [total number of subtasks] subtasks** checkbox and click **Export**.
  - To export all or filtered subtasks, at the upper right corner click **Export**.
  - To export selective subtasks, on the subtasks list mark the checkbox next to the subtask you want to export.
3. On the next popup, choose the language you want to export subtasks in as shown below, then click **Export**.

![Screenshot_2025-03-02_at_8_45_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-411f9bbd-aec0-fd5a-6e29-362b5a4b2e28.png)

This sends you an email containing the link to the subtasks file and the password to access it. Clicking the Download File link in the email downloads the file on your device. The email includes the 32-character password to access the file.

> [!NOTE]
> **Note**
> 
> If you are a Windows user, you must use third-party tools like 7-Zip, WinRAR, and WinZip to access the exported subtasks report. If encryption is disabled, you can freely download the exported CSV file without the need for a passkey. For more information on encryption, see [Configuring DSR encryption standards](/v1/docs/configuring-dsr-encryption-standards).
