---
title: "Test findings"
slug: "test-findings"
updated: 2026-07-21T07:01:36Z
published: 2026-07-21T07:01:36Z
canonical: "helpcenter.securiti.ai/test-findings"
stale: true
area: dspm
modulo: compliance
tipo: guia
data_captura: 2026-10-06
---

# Test findings

**Scenario**

As a data compliance officer, staying ahead of violations is part of your daily responsibility. But reviewing scattered test results across systems slows you down. The Test Findings dashboard changes that by giving you a real-time, visual overview of control failures across frameworks. You quickly detect problem areas, prioritize remediation, and demonstrate ongoing compliance with confidence.

The test findings dashboard lets you view the findings against the tests and address the violations of the established rules, potentially leading to data vulnerabilities or non-compliance. You can explore, identify, and resolve compliance challenges and roadblocks. The dashboard comprises graphs and widgets offering real-time compliance status across various international frameworks.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

To access test findings:

1. Open the compliance dashboard.
2. From the top right corner, click **Test Findings**.
3. Or from the left navigation bar, select **Test Findings > Test Findings**.

> [!NOTE]
> **Note**
> 
> You can also see the findings page through the Securiti dashboard.
> 
> 1. Open Securiti, and from the bottom cards, click **Findings**.
> 2. On the **Findings** page, from the left panel, select **Tests** to view the compliance findings in detail.

![Screenshot_2025-09-26_at_2_46_55_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1f24a3ef-91f5-9a72-6d0e-f202556030bc.png)

> [!NOTE]
> **Important**
> 
> Test Findings are no longer tied to the Compliance module. This update lets Compliance be offered as an add-on.
> 
> They are now included in the base Sensitive Data Intelligence license and no longer require Compliance to be enabled. The Compliance module continues to function as before.

- At the top, the dashboard shows you the widgets. Each widget depicts certain statistics related to the test findings.

| Widget name | Description |
| --- | --- |
| Asset Posture Score | This widget displays the security health of data systems and supported nodes over time. |
| Open Asset Findings | This widget displays the count of open asset findings over time. |

- The **Manage Compliance** option, located above the widgets, directs you to the [compliance module](/v1/docs/using-compliance) dashboard.
- The **Rule Center** option, located next to **Manage Compliance** option, directs you to the [Rule Center](/v1/docs/rule-center-overview) page.
- The search bar, below the widgets, lets you search findings by name or description.

#### Filtering findings

At the top of the page, above the statistics widgets, you can see a filter bar. This filter bar makes it easier to search for finding-specific information based on various properties such as data risk factor, owner, and more.

Additionally, the state of the applied filters is now retained when switching between different policies or findings from the side panel within the same page. For example, you can apply a filter to view only findings related to unprotected data by selecting the Risk Factor as Unprotected Data, then switch to another policy and come back here to find the filter state retained.

To apply the filter:

1. Click the ➕ icon to add a new filter.
2. Select a property (for example, Owner, Severity, Risk Factor) from the list.
3. Choose a filter condition (for example, is one of, contains, before).
4. Provide or select the value(s) for the chosen condition.
5. Click **Apply** to filter the findings.

**Creating a saved view**

The **Saved Views** feature lets you save applied filters and reuse them whenever needed. Instead of reapplying multiple filters every time you navigate away and return, you can quickly access your saved view with just a couple of clicks. By making it easier to focus on specific finding, Saved Views reduces repetitive effort and helps you analyze results faster.

To save a view:

1. Apply the desired filters.
2. Once filters are applied, from the top right corner of the page, the **Save View** option becomes enabled.
3. Click **Save View**.
4. In the Save View panel, enter:
  - Group name
  - Name of the view
  - Optional description
5. Click **Save View** to confirm.
6. Click **Saved View** button located next to the **Save View** button to open and select from your saved views.

On the right side of the page, below the statistics widgets, you can view the **Group by** menu. This menu lets you filter search results by **Test** or **Control** groups.

Once you apply the filters, the small widgets beneath the search menus display specific statistics related to the findings. For example, if you select **Test** from the **Group by** menu and select any entity from the **Entity Type** menu, then:

- The **Test** widget displays the total count of tests created for the selected entity type.
- The **Findings** widget shows the total count of findings associated with these tests.
- The **Asset Posture Score** widget shows the score associated with tests based on asset level systems.
- The **Frameworks** widget reveals the count of frameworks under which these tests are categorized.
- The **Controls** widget shows the number of controls linked to the tests.

To view findings from file-based tests:

1. Select **Test** from the **Group By** menu.
2. Choose the **Data Tests** option to explore file-based findings along with the following details:
  - The **Test** widget displays the total count of file-based tests created for the selected entity type.
  - The **Findings** widget shows the total number of findings associated with these file-based tests.

The posture score provides a comprehensive measure of your organization's risk by quantifying the severity and volume of findings. It serves as a key indicator of the organization’s overall risk posture, highlighting potential areas of concern and identifying toxic combinations of elements that could increase risk. The score calculation incorporates both the number and the weighted severity of findings, producing a value scaled between 0 and 100. It includes **Asset Posture Score**, which evaluates security posture of all asset level systems.

- If the score is higher than the trend, it signals that data risk is increasing, indicating worsening vulnerabilities that require immediate attention.
- If the score is lower than the trend, it demonstrates that data risk is decreasing, reflecting improvements in the organization’s risk posture.

This makes the posture score a dynamic and actionable tool, providing a clear view of the organization’s current and evolving risk environment.

#### Exploring findings

Below the filtering options, the table presents a list of tests/controls/files by tests (based on the selection in the **Group by** menu) where findings have been raised. For instance, if you have selected **Test** from the **Group by** menu, the table will display a list of tests. For each test, you can view:

- Complete test name
- Test type
- Count of findings found against the tests
- Owner of the test

> [!NOTE]
> **Note**
> 
> On the right side of the owner column, you can find the column selector. It lets you choose which columns to display in the tables listing test/controls and their respective findings. This way, you can customize the view according to your preferences. You can also reset the selection to default settings.

Below the column selection, you can click **Metadata explorer** to view complete metadata details.

### Metadata explorer

1. Click on the **Metadata Explorer** located at the right-most side of each test to view the following metadata for that finding.
  - Test name
  - Test description
  - Owner name
  - Tags
  - Controls
  - Data system (Data system information is provided for system-generated tests; however, this information is omitted for custom tests)

> [!NOTE]
> **Note**
> 
> You may observe varying details across different entities. For instance, in the case of system controls, you can view the control name, description, and the number of tests conducted against each control.
2. Click **Explore** to open the instance explorer.

On the instance explorer detailed page, you can view the following details:

Below these details, you can access the instance explorer, which provides a visual representation of the entire hierarchy of findings. For instance, in the provided screenshot, the instance explorer displays:

Below the instance explorer, you can explore the above details further in tables. This table interface is divided into two panels:
  - At the top, you can view the test details, including:
    - Test name
    - Test description
    - Control/test
    - Status
    - Type
    - Severity
  - The number of frameworks associated with each project.
  - The count of categories and subcategories linked to the frameworks.
  - The number of controls and tests against which the findings were raised.
  - Cloud assets associated with the findings.

![Screenshot_2024-07-09_at_10_19_51_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-141a5903-9fed-b0f9-94d1-d73bf9c72a77.png)
  - The left panel lists the components associated with the findings and their respective counts.
  - Click on any component in the left panel to view detailed information in the right panel. For instance, clicking on a project name in the left panel will display comprehensive project details in the right panel, including status, scope, and additional information.

### Expanded view

- On the main page, click the down arrow in the table view to expand the tests/controls/ files by tests to view the findings associated with the particular test/control/file.
- The expanded view displays a list of associated findings, and for each finding, you can view the following details:

| Filter | Description |
| --- | --- |
| Entity Id | The unique identifier for the entity associated with the finding. |
| Alert Id | The unique identifier for the alert associated with the finding. |
| Finding name | The name of the test against which the finding is raised. |
| Entity name | The name of the entity associated with the finding. |
| Entity type | The type of the entity linked to the finding. |
| Last event date/time | The date along with the time when the finding was last reviewed. |
| Severity | The severity level of the finding. |
| Finding assignee | The assignee who is responsible for addressing the finding. |
| Ticket number | The clickable ticket number for the ticket you created in platforms like ServiceNow or Jira allows you to quickly track and address compliance test findings. > [!NOTE] > **Note** > > The ticket number is visible only if the **View Policy** operation is enabled from the **Policy Engine** permission. For more details, see RBAC Roles and Permissions for Policies and Compliance. |

#### Assigning owners to the findings

1. Click **Options** (three dots) located at the right side of the finding and select **Change Assignee**.
2. On the popup screen, click on the search user menu to view the list of users and choose the user you want to assign that finding to.
3. Click **Yes, continue**.

#### Metadata explorer for a particular finding

- Click **Metadata Explorer** located to the right of the assigning owners option, to explore detailed information about that particular finding.
- Click **Explore** to open Instance Explorer for that finding.

#### Tracking and addressing compliance test findings

You can streamline the process of tracking and addressing compliance test findings. Using Securiti's automation policies, you can create task tickets in platforms such as **ServiceNow** and **Jira** to quickly track and address compliance test findings. Securiti's Findings dashboard shows compliance test findings generated as a result of compliance tests. This lets you review alerts to identify misconfigurations that need remediation. Using Securiti's DataCommand Graph capability, you can create automation policies to manage the actions needed to address these findings.

Once you assign the task, the relevant team member can quickly address any **Failed** compliance test.

For details, refer to [Automation policy](/latest/docs/using-automation-policies).

#### Creating widgets

You can see the **Create Widget** button on the right side of the findings search bar. This option lets you place widgets on any custom reporting dashboard to track metrics, trendlines, and more. You can place the following widgets on any custom reporting dashboard:

- Asset posture score metric
- Asset posture score
- Test open findings

To create and export widgets:

1. Click **Create Widget**.
2. Enter relevant information and save.

For more information, see [Creating widgets into dashboard](/v1/docs/creating-widgets-in-graph-explorer).
