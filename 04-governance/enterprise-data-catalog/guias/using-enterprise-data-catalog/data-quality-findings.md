---
title: "Data quality findings"
slug: "data-quality-findings"
updated: 2026-07-18T12:45:51Z
published: 2026-07-18T12:45:51Z
canonical: "helpcenter.securiti.ai/data-quality-findings"
stale: true
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Data quality findings

The data quality findings provide insight into data quality issues in datasets based on the expectations executed. These insights are generated when a checkpoint is executed to assess data quality. During execution, checkpoints apply specific rules or expectations to datasets. If the data fails to meet these expectations, findings are generated to highlight the issues, enabling you to address and resolve data quality problems effectively.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Prerequisites

To perform actions on Data Quality Findings, enable the corresponding permission(s) for the required operation. Only the permission(s) associated with the action you intend to perform are required. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

- Read Data Quality Findings
- Update Data Quality Findings

To access data quality findings:

1. Open Securiti, and from the bottom cards, click **Findings**.
2. On the **Findings** page, from the left panel, select **Data Quality** to view the data quality findings in detail.

![Data quality findings dashboard](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-08-22 at 1.16.09 PM.png)

- At the top, the dashboard shows you the widgets. Each widget depicts certain statistics related to the data quality findings.

| Widget name | Description |
| --- | --- |
| Total findings | This widget displays the total number of findings over time. |
| Open findings | This widget displays the total number of open findings. |
| Closed findings | This widget displays the total number of closed findings. |
| Security findings by status | This widget depicts the graph that shows the number of open and closed findings over time. |

- The search bar below the widgets lets you search for findings by dataset name, checkpoint name, or expectation name.
- On the right side of the search bar, you can click **Actions** to:
  - Close the finding
  - Change the finding assignee

> [!NOTE]
> **Note**
> 
> You first need to select any finding to perform the close or change the assignee.

### Filtering findings

At the top of the page, above the statistics widgets, you can see a filter bar. This filter bar makes it easier to search for finding-specific information based on various properties such as dataset name, domain, status, and more.

Additionally, the state of the applied filters is now retained when switching between different policies or findings from the side panel within the same page. For example, you can apply a filter to view only closed data quality findings by selecting the Status as Closed, then switch to another policy and come back here to find the filter state retained.

To apply the filter:

1. Click the ➕ icon to add a new filter.
2. Select a property (for example, Domain, Status, Expectations) from the list.
3. Choose a filter condition (for example, is one of, contains, before).
4. Provide or select the value(s) for the chosen condition.
5. Click ​**Apply**​​ to filter the findings.

#### Creating a saved view

The ​**Saved Views**​​ feature lets you save applied filters and reuse them whenever needed. Instead of reapplying multiple filters every time you navigate away and return, you can quickly access your saved view with just a couple of clicks. By making it easier to focus on specific finding, Saved Views reduces repetitive effort and helps you analyze results faster.

To save a view:

1. Apply the desired filters.
2. ​Once filters are applied, from the top right corner of the page, the ​**Save View**​​ option becomes enabled.
3. ​Click ​**Save View**​​.
4. ​In the Save View panel, enter:
  1. ​Group name
  2. ​Name of the view
  3. ​Optional description
5. ​Click ​**Save View​​** to confirm.
6. ​Click ​**Saved View**​ button located next to the ​**Save View​​** button to open and select from your saved views.

#### Group by menu

On the right side of the page, below the search bar, you can view the **Group by** menu. This menu lets you filter search results by:

- Dataset
- Checkpoint
- Expectation

Once you apply the filters, the small widgets beneath the search menus display specific statistics related to the findings. For example, if you select **Dataset** from the **Group by** menu, then:

- The **Dataset** widget displays the total count of datasets for which checkpoints were executed.
- The **Findings** widget shows the total count of findings associated with these datasets.
- The **Checkpoints** widget shows the count of checkpoints associated with the findings.
- The **Expectation** widget displays the number of expectations associated with the checkpoints.

### Exploring findings

Below the filtering options, the table presents a list of datasets/checkpoints/expectations (based on the selection in the **Group by** menu) where findings have been raised. if you select **Dataset** from the **Group by** menu, the table will display a list of datasets along with the findings associated with each. For each dataset, you can view:

- Dataset name
- Dataset domain
- Findings
- Dataset owner

> [!NOTE]
> **Note**
> 
> On the right side of the owner column, you can find the column selector. It lets you choose which columns to display in the tables listing datasets/checkpoints/expectations and their respective findings. This way, you can customize the view according to your preferences. You can also reset the selection to default settings.
> 
> You can display the following columns in the table listing findings against the datasets:
> 
> - Dataset name
> - Domain
> - Findings
> - Owner
> 
> The values under the column selector depend on your selection from the **Group by** menu.

Below the column selection, you can click **Metadata explorer** to view complete metadata details.

#### Expanded view

You can click the down arrow in the table view to expand the dataset/checkpoint/expectation to view the associated findings. For example, you can expand a dataset in the table view to see the list of associated checkpoints and the generated findings. For each finding, you can view the following details:

- Finding date created
- Status
- Expectation name
- Checkpoint name
- Last event date/time
- Events
- Data system
- Finding owner

#### Metadata explorer

- Click **Metadata Explorer** located to the right of the finding owner to explore detailed information about that particular finding.

### Assigning owners to the findings

You can change the owners of the findings by following the below steps:

1. Select a finding from the expanded view. You can also select multiple findings.
2. In the pop-up that appears at the bottom middle of the page, click **Change Assignee**.
3. In the change assignee pop-up, choose a user from the **User** menu.
4. Click **Yes, continue** to confirm.

> [!NOTE]
> **Note**
> 
> You can also change the assignee using the **Actions** button located at the right end of the search bar.

### Closing findings

You can close the findings by following the below steps:

1. Select a finding from the expanded view. You can also select multiple findings.
2. In the pop-up that appears at the bottom middle of the page, click **Close Finding**.

> [!NOTE]
> **Note**
> 
> You can also close the finding using the **Actions** button located at the right end of the search bar.

## Related

- [Data quality](/data-quality-framework.md)
