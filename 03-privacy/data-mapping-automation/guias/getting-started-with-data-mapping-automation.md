---
title: "Getting Started with Data Mapping Automation"
slug: "getting-started-with-data-mapping-automation"
updated: 2026-08-11T07:30:24Z
published: 2026-08-11T07:30:24Z
canonical: "helpcenter.securiti.ai/getting-started-with-data-mapping-automation"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Data Mapping Automation

### What is Data Mapping Automation

Securiti Data Mapping Automation lets you reduce risk by automating the data mapping process. Here’s how you can benefit:

- Identify the personal data held and used across your organization.
- Understand the regulations the data is subject to and the requirements for data protection.
- Maintain evergreen inventories of assets, processes, and vendors for records of processing (ROPA).

### Who uses Data Mapping Automation?

Companies wanting to:

- Streamline data discovery
- Flag risk and policy violations
- Automate privacy workflows

### Why use Data Mapping?

- By mapping data flows, organizations can identify potential vulnerabilities and areas where data might be at risk, whether due to unauthorized access, data breaches, or policy non-compliance.
- The DMA module clearly shows how data moves through the organization, where it is stored, and how it is used. This transparency is crucial for effective data governance.
- Customers are increasingly concerned about how their data is used. A data mapping module helps organizations provide clear information on data usage, enhancing customer trust. For example, if a data breach occurs, a data mapping module can quickly identify which data was affected, how it was accessed, and what processes and systems are involved, allowing for a faster and more effective response.

### Dig into specific features

#### Build and manage an inventory of data assets

Configure data assets by creating new or importing existing ones.

(Optional)You can maintain an inventory by synchronizing assets via CMDB data systems (ServiceNow, Okta).

[Learn more](/v1/docs/creating-and-editing-data-assets)

#### Map the data lifecycle by creating and enriching processes

Create new processes and enrich data process elements by associating them with existing Assessments

[Learn more](/v1/docs/creating-and-editing-processes)

#### Perform PIAs and DPIAs associated with data processing activities

Conduct data map assessments to identify risks associated with data catalog items. Any risks are revealed when the assessment is completed, for example, initiating an assessment for the asset that's linked to multiple processes or institutions/vendors.

[Learn more](/v1/docs/enriching-existing-data-mapping-objects-with-assessments)

#### Generate RoPA (Article 30) Reports

Customize fields and export a record of the processes to fulfill the requirements of GDPR Article 30 and similar regulations.

[Learn more](/v1/docs/creating-and-customizing-records-of-processing-activities-ropas)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/DMA-GS-Design.svg)

### 4 Steps to Getting Started with Data Mapping Automation

Below are five easy steps you to get started with Data Mapping Automation:

#### Step 1 - Understanding Data Maps Settings

| **Reference Lists and Catalog Definitions** Securiti provides System Catalog Definitions and the ability to import definitions. Similarly, Securiti offers both system-provided Reference Lists, and also, you can customize reference lists. [Learn more](/v1/docs/using-data-mapping-automation) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(176).png) ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(177).png) |
| --- | --- |
| [Embedded content](https://player.vimeo.com/video/836654232?title=0&amp;byline=0&amp;portrait=0&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479) | **Clone or import definitions and editing Reference Lists** Before proceeding, decide whether to proceed with Securiti's definitions or clone the system definitions to suit. Also, you can customize the Reference List items within those definitions. If you want to import catalog definitions, you can do so by importing a CSV file. Once you've done this, customize catalog definition templates to use for creating an entity. [Learn more](/latest/docs/creating-and-customizing-data-mapping-templates) |

#### Step 2 - Configure Data Maps entity

| **Data Mapping Automation dashboard** On the Assets page, you can create a new asset or edit an existing asset. Similarly, you can create new or import existing Processes, Vendors, or Institutions. Apply different settings to data maps entity by editing fields you previously configured in definition templates. [Learn more](/latest/docs/creating-and-editing-data-mapping-items) | [Embedded content](https://player.vimeo.com/video/828251152?title=0&amp;byline=0&amp;portrait=0&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479) |
| --- | --- |

#### Step 3 - Conduct Data Maps Assessment or Associate Data Mapping Item

| [Embedded content](https://player.vimeo.com/video/836099294?title=0&amp;byline=0&amp;portrait=0&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479)[Embedded content](https://player.vimeo.com/video/847258373?title=0&amp;byline=0&amp;portrait=0&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479) | **Initiate or enrich assessment** You may use a data mapping entity to initiate new assessments or associate a data catalog item to enrich an existing assessment. Also, you can link multiple processes, vendors, or institutions to an assessment. [Learn more](/latest/docs/creating-new-data-mapping-items-with-assessments) |
| --- | --- |

#### Step 4 - Reporting and Visualization

| **Understand risks and export RoPA** View revealed risks as part of the data maps assessment for a linked asset or process. You can export a RoPA report for reporting and visualization purposes. [Learn more](/v1/docs/monitoring-process-and-asset-risks) | [Embedded content](https://player.vimeo.com/video/833612098?title=0&amp;byline=0&amp;portrait=0&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479) |
| --- | --- |

### Data Mapping Automation API Documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The Data Mapping Automation API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-mapping-automation/apidocs/index.html#section/Getting-Started) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the postman** **collection** We also provide Postman collection for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that let you to quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-mapping-automation/apidocs/index.html#section/Getting-Started/Import-Postman-Collection) | ![API documentation showing data elements fetched successfully with various parameters listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-27 at 4.33.15 PM.png) |

Assessments answer different questions related to an entity, such as purpose, etc. Also, with each assessment, you can associate risks.

RoPA is a report that exports a process in report form defining its properties, relations, and so on.

Catalog Definitions define what sections and fields an entity uses to record the details.

A reference list is a set of options or settings that lets you configure questions in a risk assessment, such as Single or Multi-select.
