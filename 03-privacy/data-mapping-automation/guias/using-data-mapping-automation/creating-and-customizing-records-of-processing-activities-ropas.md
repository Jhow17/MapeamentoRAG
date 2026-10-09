---
title: "Creating and customizing records of processing activities (RoPAs)"
slug: "creating-and-customizing-records-of-processing-activities-ropas"
updated: 2026-08-17T10:14:02Z
published: 2026-08-17T10:14:02Z
canonical: "helpcenter.securiti.ai/creating-and-customizing-records-of-processing-activities-ropas"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating and customizing records of processing activities (RoPAs)

**Scenario**

As a Data Compliance Officer on the legal team, you're asked to demonstrate processing activity records during a regulatory audit. Manually compiling details is slow and risks omissions. With automated RoPA report generation, you pull accurate, up-to-date records in minutes. This supports a smooth audit experience and clearly shows your organization’s compliance with GDPR Article 30.

#### Prerequisites

In order to create and customize a RoPA, you must have one or more of the following roles and have access to the current organization:

- Super Admin
- Org Admin
- Operator
- Module Owner
- DPO

After you create your catalog of data assets and construct a data flow process, you can create a record of the process and export it as a report that fulfils the requirements of GDPR Article 30 and similar regulations. You can also enrich the report with custom sections.

> [!NOTE]
> **Important**
> 
> Process retention duration is the maximum of all assets. The retention reason is inherited from the asset with the highest duration. If multiple assets have the same highest duration, the reason of the first asset is assigned. For example, a process with assets of 1, 2, and 3-year durations has a retention period of 3 years.

### Creating a record of processing activities

1. In Securiti, open **Data Mapping Automation** and choose **Dashboard & Reports > Records of Processing Activities**.
2. On the Article 30 page, near the upper right corner click **+ Generate New Report**.
3. On the Export Records of Processing Activities popup, choose the output format, choose the process, and enter a name for the report as shown below. For PDF reports, also enter the report title that appears on the cover page.

![Screenshot_2025-06-16_at_1_28_15_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c495b8f7-f420-d94b-18d5-52601c6e0432.png)
4. Click **Export**.

> [!NOTE]
> **Note**
> 
> The RoPA CSV export is limited to 2,000 processes per export. For larger datasets, consider exporting multiple files.
5. Wait for a minute while Securiti prepares the report, then refresh the Records of Processing Activities page in your browser.

The new report appears on the list on the Records of Processing Activities page.
6. Use the tools at the right end of the report entry to preview and download the report. In the report, the Managing Organization field appears as "Managing Department."

> [!NOTE]
> **Note**
> 
> For trial accounts, the reports show the Securiti logo on the front page and on the page footers. For Premium customers, the Securiti logo is omitted from the front page. And if you have configured an organization logo on System Settings > Organizational > General, the report shows that logo on the page footers instead of the Securiti logo.

### Adding custom sections to records of processing activities

You can enrich a Report of Processing Activities (RoPA) by adding custom sections and custom fields to its template. When you publish a RoPA that uses the template, it includes the new section and its contents.

1. In Securiti, open **Data Mapping Automation**, then choose **Settings >** Definitions.
2. On the Catalog Definitions page, click the Process template, or any clone of it.
3. Click the tile for **Add New Section**, and edit the new section to suit.
4. Use the **Include in RoPA Report** toggle to include or exclude the new section in the RoPA as shown below.

![Screenshot_2025-06-16_at_1_31_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c0b4b05d-3d3b-115b-2229-c0c5242addaa.png)
5. When you are done, save the report.

RoPA is a report that exports a process in report form defining its properties, relations, and so on.

Catalog Definitions define what sections and fields an entity uses to record the details.

A process defines the flow of data between entities and processes.
