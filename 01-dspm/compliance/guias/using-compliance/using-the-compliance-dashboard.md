---
title: "Using the Compliance dashboard"
slug: "using-the-compliance-dashboard"
updated: 2026-07-21T06:47:43Z
published: 2026-07-21T06:47:43Z
canonical: "helpcenter.securiti.ai/using-the-compliance-dashboard"
stale: true
area: dspm
modulo: compliance
tipo: guia
data_captura: 2026-10-06
---

# Using the Compliance dashboard

**Scenario**

As a data compliance officer, you are responsible for ensuring your cloud environments meet ISO 27001 and GDPR requirements. Manually mapping controls and tracking compliance across systems is time-consuming and error-prone. With the Compliance module, you define your scope, apply frameworks, and run expression-based or attestation tests. You quickly identify failed controls and take action, saving time and reducing compliance risk.

The compliance dashboard shows your compliance status at a glance. To open the compliance dashboard:

- On the Securiti dashboard, click the **Compliance** card.

> [!NOTE]
> **Note**
> 
> If you are on another page within the compliance module, you can navigate to the compliance dashboard by:
> 
> - Click **Compliance** from the top menu.
> - From the left navigation bar, select **Dashboard > Compliance Overview**.

On the top right corner of the page, you can view different options as shown below:

- The **Projects** option lets you see all the projects created to implement controls within a defined scope.
- Click **Frameworks** to view a list of all pre-defined and custom frameworks. For more information, see [Using Framework Dashboard](/v1/docs/using-the-framework-dashboard).
- The **Controls** option lets you view all pre-defined and custom controls within the module. For more information see [Controls](/v1/docs/controls-overview).
- You can click **Tests** to view a list of tests created. These tests assess the effectiveness of controls in ensuring compliance with regulations, standards, and internal policies. For more information, see [tests](/v1/docs/rule-center-overview).
- You can click **Test Findings** to view the findings against the tests and address the violations of the established rules, potentially leading to data vulnerabilities or non-compliance. For more information, see [test findings](/v1/docs/test-findings).
- Click **Create Widget** to create widget.

> [!NOTE]
> **Note**
> 
> For more information on creating widgets, visit [Creating widgets into dashboard](/v1/docs/using-data-command-graph)

The compliance dashboard presents you with four consolidated widgets. Each widget presents a trend line to monitor compliance performance over time, helping you visualize increases or decreases in compliance failures or successes.

- The **passed tests** widget displays the number of passed tests compared to the total number of tests. The graph beneath shows the trend over time, with separate lines for passed and failed tests.
- The **passed controls** widget represents the number of passed controls versus the total number of controls. The trend graph shows separate lines for passed and failed controls over time.
- The **passed entities** widget shows the number of passed entities versus the total entities. The graph represents the trend in passed and failed entities over time.

![Compliance_dashboard_widgets.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-230435e1-d175-8727-260c-5df380ccee69.png)

On the left side of the widget panel, you can see a list of projects along with their associated frameworks. At the top, the project menu lets you search for and select from your created projects. Below it, the search bar lets you find frameworks by name.

#### Exploring frameworks

Below the widgets panel, you can see the name of the selected framework. On the right end, you can see its type, whether **System** or **Custom**.

Directly below the framework name, a search bar lets you find framework categories quickly.

### Filtering frameworks details

You can filter framework details based on Category, test type and test status.

- The **Category** name menu lets you filter categories based on the category name.
- The **Test** type menu lets you filter categories based on the type of the test i.e. **Expression** or **Attestation**.
- The **Test status** menu lets you filter categories based on the status of the test as passed or failed.

Below these filters, you can see the total count of categories within the framework.

### Framework details

For each category of the framework, you can view the following details:

- Category name (Also known as **Compliance Posture**).
- Passed percentage: It indicates the ratio of passed tests to the total tests conducted.
- Entities count: It displays the number of entities where tests passed and failed. The green dot represents the number of entities that passed the compliance test. However, the brown dot represents the number of entities that failed the compliance test.

> [!NOTE]
> **Note**
> 
> This column shows zero value if the associated tests are file-based.
- Data objects count: It displays the number of files where tests passed and failed. The green dot represents the number of files that passed the test. However, the brown dot represents the number of files that failed the test.

> [!NOTE]
> **Note**
> 
> This column shows zero value if the tests under this framework involve different entities other than files.
- Passed tests count: It is the number of compliance tests passed out of the total conducted. For example, 1 of 1, means one test was run and passed successfully.

#### Expanded view

- Click on any category from the list to view its subcategories. You can further expand subcategories to see the controls associated with each. Each subcategory displays the same details as the category.
- Click on any control to view the list of tests associated with it. For controls and their respective tests, you can see the same details as categories and subcategories, including the pass percentage, the count of passed and failed entities, and data objects. Additionally, the test results are displayed as pass or fail.

#### Compliance Metadata

- At the right end of the row containing the framework category, click **Compliance Metadata** to view a graphical representation of the metadata. This metadata option is also available for associated subcategories, controls, and all associated tests, letting you view detailed metadata for each.
- The graphical representation displays all the interconnected nodes. On clicking a specific node, you can view the information relevant to the corresponding node in a tabular format. You can click on any component in the left panel to view its detailed information in the right panel.

![Compliance_metadata.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86c8909e-63bc-7dbb-316e-219bd75a8555.png)

#### Creating widgets

You can see the **Create Widget** button on the right side of the **Create** button. This option lets you display compliance-specific widgets on the compliance dashboard to track metrics, trendlines, and more.

1. Click **Create Widget**.
2. Enter relevant information and save.

For more information, see [Creating widgets into dashboard](/v1/docs/creating-widgets-in-graph-explorer).

### Exporting the selected framework grid to the reporting dashboard

You can select any framework grid from the Compliance dashboard and create a widget to export it directly to the reporting dashboard. This lets you present the data in a more interactive, visually engaging, and accessible format for stakeholders and decision-makers.

Additionally, the grid can fetch and update data dynamically, ensuring that the reporting dashboard always reflects real-time information. This capability also provides more flexibility in interacting with the grid, offering a seamless experience for users to explore and analyze data on-demand.

![Complinace_frameworks.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5221a413-b422-0efa-9353-ed28cdbdc281.png)

> [!NOTE]
> **Note**
> 
> These grids are also filterable by **Framework** and **Project**, making it easier to compare and report progress across initiatives.

A category in a compliance framework is a high-level classification or grouping of related compliance requirements or objectives. For example, Data Cataloging and Classification is one of the categories in the CDMC framework.
