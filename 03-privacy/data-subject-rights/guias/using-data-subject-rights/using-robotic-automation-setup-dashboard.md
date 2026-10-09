---
title: "Using Robotic Automation setup dashboard"
slug: "using-robotic-automation-setup-dashboard"
updated: 2026-01-14T09:37:05Z
published: 2026-01-14T09:37:05Z
canonical: "helpcenter.securiti.ai/using-robotic-automation-setup-dashboard"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Using Robotic Automation setup dashboard

The Robotic Automation Setup dashboard shows you data system readiness and setup progress in one place. track automation steps and set up data systems to serve DSR requests.

To open the dashboard, from the side navigation click **Settings > Robotic Automation Setup**.

- At the top, the dashboard shows total purchased licenses versus active licenses for scanned and scanless data systems. Scanned data systems include monitored-structured, unstructured and hybrid systems.

> [!NOTE]
> **Note**
> 
> The dashboard shows license counts at the tenant level. Webhook (user-defined) data systems are not included because they do not require licenses.

![Robotic Automation Setup dashboard with licenses detail.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-24 at 12.49.31 PM.png)
- Use the search bar to search for a particular instance by its name.
- Use filters to narrow results.

| Filter | Description |
| --- | --- |
| Included in DSR Workflow | Filter data system instances with “Include this instance in DSR workflow” checkbox enabled or disabled in **Permissions** tab. |
| Data System Category | Filter data system instances by their category such as monitored-structured, monitored-structured, unmonitored, scanless etc. |
| Data System Type | Filters data system instances by their type or name, such as specific connectors (for example, ActiveCampaign, Airtable, MySQL) along with hosting models (Securiti Cloud, Self-hosted). > [!NOTE] > **Note** > > For Webhooks, both Securiti cloud and self-hosted use the same ID (webhook_udc), so no extra label is shown in this filter with Webhook option. |
- Metrics cards show the following:

| Metric | Description |
| --- | --- |
| Data System Instances | Total number of data system instances created within the organization. |
| Monitored Unstructured | Total number of monitored unstructured data system instances within the organization, such as Google Drive or AWS S3, either self-hosted or cloud. |
| Monitored Structured | Total number of monitored structured data system instances within the organization, such as MySQL or Redshift, either self-hosted or cloud. |
| Monitored Hybrid | Total number of monitored hybrid data system instances within the organization, such as Workday. |
| Scanless | Total number of scanless data system instances within the organization, such as Segment. |
| User Defined | Total number of user-defined or webhook instances within the organization. |
| Unmonitored | Total number of unmonitored assets created within the organization from the Data Mapping module. |
- The grid contains instances details:

| Column title | Description |
| --- | --- |
| Instance Name | Shows the data system instance name |
| Data System Type | Shows the data system type (for instance, Google Drive). For unmonitored data systems, this column shows the technology type chosen when creating an asset in the Data Mapping module. |
| Data System Category | Shows the data system category: - Monitored - Structured - Monitored - Unstructured - Monitored - Hybrid - Monitored - Scanless - User Defined - Unmonitored |
| Securiti Hosted | Shows whether the instance is cloud or self-hosted. |
| Included in DSR Workflow | Indicates whether the “Include this instance in DSR workflow” checkbox is selected in the **Permissions** tab. |
| Robotic Automation Status | Shows the stage at which the instance is ready to serve a DSR request: - No Connection - Connection In Progress - Failed Connection - Active Connection - Included in DSR - Not Included in DSR - Table Training Complete - Table Training Not Complete - No Discovery Scan with DSR Setting - Discovery Scan with DSR Setting |
| Owners | Shows data system owners. |

At the upper corner of the page, click **Setup Wizard** to view steps to set up a data system instance for DSR Automation.

![Robotic Automation Setup dashboard with setup wizard.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-24 at 12.49.44 PM.png)![Screenshot_2025-09-27_at_8_00_00_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d37df3f8-d75d-f881-194c-5b72ea7c72d9.png)

### View data system instance details

You can view instance details such as DSR forms associated with an instance or location etc.

To view details:

- On the Robotic Automation Setup dashboard, near the right corner of the instance row click View **Metadata.**

![Clicking metadata card icon from Robotic Automation Setup dashboard](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-24 at 12.49.57 PM.png)
- From this metadata card you can do the following:
  - Click **Connector Detail Page** to view instance configurations.
  - Click number against DSR Forms label to view all forms associated with this instance.

![Associated forms with data system instance](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-24 at 12.50.11 PM.png)

![List of associated DSR forms.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-24 at 12.59.14 PM.png)
  - Click the discovery scan IDs to view scan jobs running against the instance.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(946).png)
  - Click the link to open the table training setup for a structured instance.

![Table training link from Robotic Automation dashboard](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-20 at 10.10.55 AM.png)

## Communicating with data system owners

You can send messages to data system owners and ask questions directly.

1. From the **Robotic Automation Setup** dashboard, choose the instance row. On the right side of the row, click **More Actions** (three dots) > **Message to Owners**.

![Message to owners from Robotic Automation setup](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-20 at 11.38.11 AM.png)
2. On the **Message to System Owners** popup, select the recipients, enter the subject and email content, and optionally insert bind variables such as the data system instance name or link. Click **Send**.

![Compose email for data instance owners.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-20 at 11.49.07 AM.png)

Securiti sends an email to the data system owners.

![Email inquiry regarding completion of discovery scan jobs](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-20 at 11.51.58 AM.png)

## Viewing automation setup status

You can view the automation setup status that shows where each data system instance is in the Robotic Automation setup, including completed and upcoming steps.

1. From the Robotic Automation Setup dashboard, choose the instance row. On the right side of the row, click **More Actions** (three dots) > **Automation Setup Status**.

![Automation setup status](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-20 at 12.19.45 PM.png)

The popup shows the automation steps for that instance, along with the responsible team, more details, and the current status.

![Overview of robotic automation setup with data system instances and setup status details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-20 at 12.21.11 PM.png)
