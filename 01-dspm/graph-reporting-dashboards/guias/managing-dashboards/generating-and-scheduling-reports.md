---
title: "Generating and scheduling reports"
slug: "generating-and-scheduling-reports"
updated: 2026-06-15T09:04:12Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/generating-and-scheduling-reports"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Generating and scheduling reports

Securiti lets you generate reports for your dashboard and widgets. This lets you save your dashboard in the form of a report on your local machine or share it with others.

You can generate a report in the following formats.

- PDF
- PPTX

## Generating reports

To generate a report.

1. In **Dashboard**, open your system or custom dashboard.
2. Near the upper right corner of the page, click **Actions**.
3. Select **Generate Report** from the menu, as shown below.

![Dashboard displaying security findings, risk severity, and data posture scores overview.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/generatereport_option.png)
4. On the popup, configure the following settings for your report:

| Setting | Description |
| --- | --- |
| Choose format | Select the output format for your report, you can choose PDF or PPTX |
| Page size | Select the page size from the menu. You can select from the following supported page sizes: - A3 - A4 - A5 - Letter - Legal - Tabloid - B4 - B5 |
| Orientation | Select the page orientation for the report, you can choose between Portrait and Landscape. |
| (Optional) Share it with others | Mark the **Share it with others** checkbox to share the report with Securiti or external users. You can search and add users to share the reports with external recipients by entering a valid email address. |

![User interface for generating a security report with various options and settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/generatereport_modal.png)
5. Click **Generate and share report.**

A message for report generation is displayed on the UI and a download link is sent to your email.

> [!NOTE]
> **Note**
> 
> Reports are shared through an email link that expires in 7 days.

## Scheduling reports

Securiti's Reporting dashboard lets you schedule a report on a daily or weekly basis. With the scheduling option, you can generate and deliver an updated report as you work on your dashboard.

To schedule a report.

1. In **Dashboard**, open your system or custom dashboard.
2. Near the upper right corner of the page, click **Actions**.
3. Select **Schedule report** from the menu.
4. Provide the following information in the **Schedule Reports** page.

| Setting | Description |
| --- | --- |
| Name | Enter your report name under the **Basic Information** section. This field is automatically filled by default. |
| Select Dashboards | Mark checkboxes for the dashboards you want to include in your report. |
| Export Settings | Select the format you want to generate your report in. You can choose both or one of the PDF and PPTX options. |
| Page Size & Orientation | Select the page size for your report from the **Page Size** menu. You can select from the following supported page sizes: - A3 - A4 - A5 - Letter - Legal - Tabloid - B4 - B5 In the **Orientation** section, select the page orientation for the report, you can choose between Portrait and Landscape. |
| Scheduling | Specify schedule to generate and deliver reports. You can choose **Daily** or **Weekly** options and set the time and day (for weekly) for report generation. |
| Notifications | Turn on the toggle for at least one of the following options to receive notifications about report generation. - **Email Notifications**: To receive notification on your email. - **Messaging & Notifications Center**: To receive notifications in your messaging center. |

![Schedule reports for AWS Cloud data with selected dashboards and export options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/schedule_settings1.png)

![Settings for scheduling AWS Cloud data reports, including frequency and notification options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/schedule_settings2.png)
5. Click **Save Schedule**. A message for successful scheduling is displayed on the UI.

### Creating multiple report schedules

Securiti lets you create multiple report schedules, each with its own set of dashboards, export format, page settings, and delivery frequency. This lets you automate report delivery for different audiences or use cases from a single place.

To create a new schedule for your report:

1. In the **Schedule Reports** page, create and save a schedule for your report as described above.
2. In the left panel, from the upper right corner, click **+ New** to create a new schedule, as shown below.

![User interface for scheduling AWS Cloud data reports with dashboard selection options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/schedule_newbutton.png)
3. Configure the schedule settings as described above and click **Save Schedule.**

The newly created schedules appear in the list on the left panel of the page.

### Managing report schedules

To manage an existing schedule, click the options (three dots) next to any schedule in the list to perform the following actions:

- **Clone**: Select this action to duplicate the schedule as a starting point for a new one. The cloned schedule appears in the list with a **(Copy)** suffix in the report name.
- **Delete**: Select this action to permanently remove the schedule.

![Schedule reports interface showing AWS Cloud data report options and export settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/schedule_options.png)

## Accesing report downloads and logs

Securiti captures logs for report exports in the **Audit Logs**. You can view the report logs by applying the filter: `Object Type = reporting_dashboard`

The page displays metadata such as export time, module name, and activity messages, providing a complete trace of report export actions.

![reporting_auditlogs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-681a859f-99a0-9d44-ebe4-688512728587.png)

You can access the downloaded reports from the following pages.

> [!WARNING]
> **Important**
> 
> You must be logged in to Securiti to download the report.

- **Notifications** page for the Securiti tenant you are using.
- **My Downloads** page for the Securiti tenant you are using. You can view details of exported reports, including the export timestamp, expiration time, component name, and a direct download link.
- Your email inbox
