---
title: "Getting Started with Graph Reporting Dashboards"
slug: "getting-started-with-graph-reporting-dashboards"
updated: 2026-06-30T12:30:33Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/getting-started-with-graph-reporting-dashboards"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Getting Started with Graph Reporting Dashboards

Graph Reporting Dashboards provide system and custom reporting for your data in the form of widgets. It lets you visualize and manage insights from various data sources across the platform. You can choose from system or custom dashboards, analyze widgets, and generate comprehensive reports in multiple formats. With these capabilities, Graph Reporting Dashboards let you effectively monitor and analyze key data.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Reporting%20Dashboard-Design-1.drawio(1).svg)

### Prerequisite

While system dashboards have predefined widgets, you must create widgets from graph modules to analyze them in the Graph Reporting Dashboards. You can choose and develop dashboards during the widget creation process from the following graph modules.

For more information, see [Graph Explorer](/v1/docs/creating-widgets-in-graph-explorer) documentation.

#### Step 1 - Choose a system or a custom dashboard to analyze

Graph Reporting Dashboards displays **System**, **Custom**, and **Shared with me** dashboard groups, including their respective dashboards.

#### System dashboard groups

System dashboard groups contain dashboards with predefined widgets designed to meet data analysis needs for cloud data, security, and compliance. The following System dashboard groups are available in the Graph Reporting Dashboards.

| **Compliance** The Compliance group includes one dashboard for backup and disaster recovery which gives you visibility into organization’s structural resilience, business continuity, and backup readiness. The dashboard within this group is: - Backup and Disaster Recovery [Learn more.](/v1/docs/compliance-system-dashboard) | ![Dashboard displaying backup and disaster recovery metrics and project statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/backupanddisasterrecovery_compliancedashboard.png) |
| --- | --- |
| **Data Security** The system dashboard group includes four dashboards which lets you gain insights into security findings, and sensitive data elements. These include: - Data and AI Security Overview - Unstructured Data Overview - Structured Data Overview - Microsoft 365 Data and AI Security [Learn more.](/v1/docs/data-and-ai-security-system-dashboards) | ![Dashboard displaying data security findings and risk severity metrics for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datasecurity.png) |
| **AI Security** The system dashboard group includes four dashboards which lets you gain insights into AI models and agents. These include: - Inventory: AI Models & Agents - Agents with Access to Sensitive Data - Sensitive Data Accessible by AI - AI Security: Toxic Combinations [Learn more.](/latest/docs/ai-security-system-dashboards) | ![Dashboard displaying AI models and agents inventory with total counts and trends.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aisecurity_dashboard.png) |
| **Public Cloud** The system dashboard group lets you view and analyse metrics for your public cloud environment's accounts, data, and security posture with the following available dashboards. - Public Cloud Overview - AWS - Data Discovery and Classification - AWS - Data Security - AWS - Compliance - Azure - Data Discovery and Classification - Azure - Data Security - Azure - Compliance - Google Cloud - Data Discovery and Classification - Google Cloud - Data Security - Google Cloud - Compliance [Learn more.](/v1/docs/public-cloud-system-dashboard-group) | [Embedded content](https://app.storylane.io/demo/g6ps2luulfyx?embed=inline) |

#### Step 2 - Analyze dashboards and widgets

After selecting your dashboard, you can start analyzing data in widgets by exploring grid, metric, and chart widgets and using clickable features for a more detailed view. Refer to the table below for available dashboard and widget features that can be used in both system and custom dashboards without entering Edit mode.

| ![Widget details showing JSON query for frameworks and associated categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewwidgetdetails_reporting.png) | **View Widget Details** You can view widget details like the JSON query and metadata behind the widget to understand the type of request used for making the widget and the source data for it. The JSON query and metadata can also be copied and used for multiple purposes like creating widgets from JSON, sharing the widget details with other users, and using in APIs. [Learn more.](/v1/docs/editing-dashboards-and-widgets) |
| --- | --- |
| ![Overview of AWS Cloud services including data systems, files, and storage details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/instanceviewpopup_reportingdashboard(1).png) | **Use Instance Explorer** You can also analyze the data in your grid widgets and chart widgets for its relationships and properties in the Instance explorer by simply clicking on any cell or column with the "display name" property. [Learn more.](/v1/docs/using-instance-explorer-for-widgets) |
| [Embedded content](https://app.storylane.io/demo/otfpfj6w3ixd?embed=inline) | **Go to widget's source page** View the source page for your widget's origin by using options like **Go to Data Command Graph** for your widgets. The option lets you get more understanding for your widget's data. Additionally, you can click on any cell for grid widgets and any segment for chart widgets to go to their source data query in the Graph Explorer. [Learn more.](/v1/docs/accessing-source-query-for-widgets) |
| ![Widget creation interface displaying an aggregated graph chart with a count of 33.7k.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/createwidgetsfromjson.png) | **Create widgets from JSON** You can add more widgets in your dashboard without having to go back and forth between graph modules. All you need is a JSON query for your widget. Use the **Create widget from JSON** option to add your widget in the dashboard. [Learn more.](/v1/docs/creating-widgets-from-json-queries) |
| ![Graph Explorer interface displaying security posture and policy counts for assets.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aggregatequery_createwidget.png) | **Create widgets from aggregate queries** Use **Graph Explorer** to create widgets for aggregate queries and save them to your custom dashboards in Graph Reporting Dashboards. These widgets let you summarize and visualize data across entities by counting records, grouping results by a property, or displaying high-level metrics. [Learn more](/latest/docs/creating-widgets-from-aggregate-queries). |
| ![Dashboard overview displaying security metrics and options for copying widgets.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/copywidgetoption_reportingdashboard(1).png) | **Copy widgets to another dashboard** Copy widgets from one dashboard to another if you want to save widgets in your new dashboard, edit system dashboard widgets in your custom dashboards, or simply want to make your own dashboard from the existing widgets. [Learn more.](/v1/docs/copying-dashboard-widgets) |

#### Step 3 - Refresh widgets data

| **Refresh Widgets Data** You can use the refresh option on the dashboards page to fetch latest data in your widgets and analyze updated information. [Learn more.](/v1/docs/refreshing-dashboards-and-widgets) | ![Dashboard overview displaying security posture scores and widget data refresh options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/refreshwidgetdata_reportingdashboard(1).png) |
| --- | --- |

#### Step 4a - Edit widgets in your dashboard

> [!NOTE]
> **Important**
> 
> You can edit **custom** dashboards only and these features do not apply to system dashboards.

| [Embedded content](https://app.storylane.io/demo/82bdszuhzdmh?embed=inline) | **Widget actions in edit mode** As you enter in Edit mode, you can choose to perform multiple actions on your widgets to suit your needs, as listed below. - Update widget name - Change chart type for widgets - Update widget details like JSON query or metadata - Resize widgets on your dashboard - Drag and drop widgets to rearrange them on your dashboard - Go to the Test Findings of a widget (if applicable) - Duplicate a widget - Delete a widget [Learn more.](/v1/docs/editing-dashboards-and-widgets) |
| --- | --- |
| ![Interface for adding a rich text widget with editable text and options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/addingarichtextwidget.png) | **Add rich text widgets** Apart from the widget actions listed above, you can also add rich text widgets in your dashboard for any documents, links, code or any information that assists with your data analysis requirements. [Learn more.](/v1/docs/editing-dashboards-and-widgets) |

#### Step 4b - Edit, clone or share your dashboards

Apart from editing or customizing widgets in your dashboard, there are a number of features supported for your system and custom dashboards.

| **View dashboard** The view option lets you open and view a dashboard and its widgets. [Learn more.](/v1/docs/managing-dashboards) | ![Dashboard displaying security findings, asset posture score, and data posture metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewdashboard.png) |
| --- | --- |
| **Clone dashboard** You can clone dashboard to copy all of its widgets as is in another dashboard. This option is useful if you want to edit and use the widgets in a system dashboard. [Learn more.](/v1/docs/managing-dashboards) | ![Dashboard displaying security findings, asset posture score, and data posture metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/clonedashboard.png) |
| **Mark as default** You can choose to make a dashboard as default to access it automatically as you open the Dashboards page. The default dashboard also shows up in the **Default dashboard** page. [Learn more.](/v1/docs/managing-dashboards) | ![Dashboard displaying security findings, asset posture score, and data posture score metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/markasdefault.png) |
| **Edit dashboard** > [!NOTE] > **Important** > > This option does not apply to **System** dashboards. The Edit option lets you make modifications to your dashboard such as changing dashboard name. [Learn more.](/v1/docs/editing-dashboards-and-widgets) | ![Dashboard displaying security findings, asset posture score, and data posture score metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/editdashboard.png) |
| **Reorder dashboard and groups** > [!NOTE] > **Important** > > This option does not apply to **System** dashboards. In Edit mode, you can change the order of your dashboard groups and the dashboards within them. [Learn more.](/v1/docs/editing-dashboards-and-widgets) | [Embedded content](https://app.storylane.io/demo/94esyfoo0uks?embed=inline) |
| **Share dashboards** > [!NOTE] > **Important** > > This option does not apply to **System** dashboards. You can share your dashboards with users across a tenant by marking it as Public or share it specific users. [Learn more.](/v1/docs/managing-dashboard-access) | ![Dashboard displaying security findings, asset posture score, and data posture score metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sharedashboard.png) |
| **Delete dashboard** > [!NOTE] > **Important** > > This option does not apply to **System** dashboards. You can delete any custom dashboard that is not required, with the delete option. [Learn more.](/v1/docs/managing-dashboards) | ![Overview of data security findings, including risk severity and asset posture scores.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deletedashboard.png) |

#### Step 6 - Generate report for your dashboard

| ![Dashboard displaying security findings, asset posture score, and report generation options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/generateandschedulereports.png) | **Generate or schedule reports** You can download a PDF or PPTX report for your dashboard for sharing and data analysis purposes or schedule automatic download of reports. Also, you can share the generated report with anyone inside Securiti by adding recipients’ emails. When scheduling report, you can specify the dashboards, whether you want a weekly or daily download, and turn on notifications as well. [Learn more.](/v1/docs/generating-and-scheduling-reports) |
| --- | --- |

#### Step 7 - View your downloaded reports

| **View or access reports** You can access the downloaded report from the following pages. - **Notifications** page for the Securiti tenant you are using. - **My Downloads** page for the Securiti tenant you are using. - Your **email** inbox. [Learn more](/v1/docs/generating-and-scheduling-reports) | [Embedded content](https://app.storylane.io/demo/h4ezv4efyyze?embed=inline) |
| --- | --- |

#### Graph Reporting Dashboards API documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The Graph Reporting Dashboards API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| [Embedded content](https://player.vimeo.com/video/1012313059) | **Run APIs directly from the docs** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without setting up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/reporting-dashboard/apidocs/index.html) |
| --- | --- |
| ![gs_reporting_postman.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff38a8e8-c005-3cb5-3863-9bbf3d3094a7.png) | **Download the postman collection** We also provide postman collection for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that let you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/reporting-dashboard/apidocs/index.html#section/Getting-Started/Import-Postman-Collection) |
