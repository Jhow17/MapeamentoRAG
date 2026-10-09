---
title: "Using the Data Subject Explorer tab"
slug: "using-the-data-subject-explorer-tab"
updated: 2025-10-30T19:13:18Z
published: 2025-11-03T07:39:28Z
canonical: "helpcenter.securiti.ai/using-the-data-subject-explorer-tab"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Using the Data Subject Explorer tab

The Data Subject Explorer also known as Single Identity Dashboard lets you visualize the personal data you have for the data subject, the nature of the data, and where it resides, and also the data subject’s compliance location.. In addition to the personal data records of the data subject, the Data Subject Explorer also shows ongoing and historical DSR requests initiated by the data subject. This is of immense value to an organization when they want a quick snapshot of the data subject as it relates to data processed by the organization along with the data subject’s interactions with the organization.

You can trigger the data subject explorer for a data subject in two ways:

- Near the bottom right corner, in the **Ask Copilot** enter the command “show me PD for <keyword>” The keyword could be email, CPF, or SSN.
- As soon as a DSR request is submitted using primary identifiers such as an email address, this automatically triggers the creation of a partial Data Subject explorer, excluding the DSR widget, in the **Data Subject Explorer** section of the **DSR Workbench**.

Near the top of the page, the widgets and world map shows metrics and data residency for the data subject, as shown below. On the map, hover over a data location to view a popup with more information.

![Screenshot_2025-08-05_at_2_51_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-465763c2-ed9e-56ac-79ae-370747e3871e.png)

> [!NOTE]
> **Note**
> 
> The Data Subject Explorer does not show results for scanless data systems as no data is submitted for discovery scan in the Sensitive Data Intelligence module. In case of scanless data systems, Securiti retrieves data by invoking the APIs provided by the scanless connectors.
> 
> Additionally, Widgets in the Data Subject Explorer populate only for DSR request types **Access** or **Port**, after Securiti scans and links the information to generate the Personal Data Graph (PDG) for the data subject.

Near the middle of the page, the Personal Data area shows charts and tables that describe what personal data records you hold for the data subject, as shown below. In most cases, specific identifiers are hashed to protect the identity of the data subject.

![Screenshot_2025-03-04_at_4_00_12_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-022a4c0c-99ee-7d7f-b8cb-4e171fff1b51.png)

Near the bottom of the page is a table that lists all personal data records for the subject that Securiti found in your monitored data systems. Some of the information, such as the subject’s user name, is obfuscated to protect their identity. The table shows 20 records per page. Click the forward or back buttons near the lower right corner to display additional records.

To effectively navigate the Data Subject Explorer for a request, you can apply filters to focus on specific personal data attributes, file types, and storage locations. These filters streamline your search and analysis process, ensuring access to relevant and accurate data of the data subject.
