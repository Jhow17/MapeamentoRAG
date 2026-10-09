---
title: "Using Security Posture Findings dashboard"
slug: "using-security-posture-findings-dashboard"
updated: 2026-06-24T13:45:37Z
published: 2026-06-24T13:45:37Z
canonical: "helpcenter.securiti.ai/using-security-posture-findings-dashboard"
area: dspm
modulo: security-posture-management
tipo: guia
data_captura: 2026-10-06
---

# Using Security Posture Findings dashboard

**Scenario**

As a Data Compliance Officer, you need to review security violations across IaaS and SaaS accounts. When you dig through spreadsheets and alerts, you miss high-risk issues and audits drag on. On the Security Posture Findings page, you see open, fixed, and suppressed findings sorted by severity, access guided remediation steps, and confirm resolutions. You close gaps faster and stay audit-ready.

The Security Posture Findings dashboard shows the results of posture scans run against your IaaS cloud accounts and SaaS data systems. Use it to review open, fixed, and suppressed findings, understand the severity of misconfigurations, and take remediation action.

Securiti populates findings on this page once you have connected an IaaS or SaaS account with posture scanning enabled. When you connect an IaaS cloud account (AWS, GCP, Azure, or OCI) with the security posture scan enabled, Securiti automatically generates posture findings for that cloud.

For SaaS data systems, such as Microsoft 365 SharePoint Online or Workday, Securiti populates findings after you configure and activate the relevant connector and initiate a posture scan from the Permissions tab on your Data Systems page.

> [!NOTE]
> Note
> 
> - For Sovereign environments, Security Posture Management is available only for self-hosted data systems supported for these environments.
> - You can use Securiti's Automation Policies to address findings by creating tickets in ServiceNow or Jira and assigning them to the relevant team members. For more information, see Configuring automation policies.

### Navigating to the Findings dashboard

You can access the Security Posture Findings page in two ways:

- From the **Security Posture Policies** page, click **View Findings** in the top-right corner.

![Overview of security posture policies with active policies and findings displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-05 at 12.43.50 PM.png)
- Click the jewel icon on the left panel, select **Findings**, then choose **Security Posture**.

![Dashboard displaying security posture findings and active policy details for cloud services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-05 at 12.47.08 PM.png)

![Overview of security posture findings and their statuses in a data management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-05 at 12.47.31 PM.png)

### Dashboard overview

The Security Posture Findings dashboard gives you a consolidated view of all posture scan results across your IaaS and SaaS environments. The sections that follow provide a detailed overview of the Findings dashboard.

#### Findings widgets

At the top of the page, two widgets provide an overview of your findings:

- **Open Findings:** Displays the total count of open findings.
- **Fixed & Suppressed:** Displays the total count of fixed and suppressed findings.
- **Open Findings chart:** Displays trendlines for Total, Very High, and High severity findings. Use the time range selector to view data for the past 7 days up to 12 months.
- **Resolved Findings chart**: Displays trendlines for Passed, Fixed, Suppressed, and Closed findings. Use the time range selector to view data for the past 7 days up to 12 months.

![Dashboard displaying open and resolved findings related to security posture metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-05 at 2.59.57 PM(1).png)

#### Searching findings

Use the search bar to locate findings by policy name, rule name, asset name, or object name.

![Dashboard displaying security posture findings and search functionality for specific findings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-05 at 3.00.25 PM.png)

> [!NOTE]
> Note
> 
> Findings beyond 10,000 cannot be fetched. If your results exceed this limit, apply filters to narrow your search to specific findings.

#### Filtering findings

Use the filter bar at the top of the page to narrow findings by one or more properties. Click **+** to add a filter, select a property, choose an operator, and click **Apply**.

![Filter options for security findings with various property selections displayed on the interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-05 at 3.04.48 PM.png)

Each filter supports the following operators:

| Operator | Description |
| --- | --- |
| Is one of | Returns findings that match any of the selected values. Use this to include multiple options in your results. |
| Is not one of | Returns findings that do not match any of the selected values. Use this to exclude multiple options from your results. |
| Is equal to | Returns findings that match exactly one specified value. |
| Is not equal to | Returns findings that do not match the specified value. |

The following table describes the available filters.

| Filter | Description |
| --- | --- |
| Account | Filters findings by the cloud or SaaS account they belong to. |
| Asset Name | Filters findings by the name of the affected asset. |
| Asset Type | Filters findings by the type of asset, such as an S3 bucket or Azure Blob Storage container. |
| Assignee | Filters findings by the user assigned to remediate them. |
| Auto Remediation | Filters findings based on whether auto-remediation is enabled for the associated rule. |
| Cloud Provider | Filters findings by the cloud provider, such as AWS, Azure, or GCP. |
| Cloud Resource ID | Filters findings by the unique identifier of the cloud resource. |
| Controls | Filters findings by the security controls associated with the finding. |
| Date Created | Filters findings by the date they were first generated. |
| Dark Asset | Filters findings to display only those associated with dark assets. |
| Finding ID | Filters findings by their unique identifier. |
| Is Sensitive Data Finding | Filters findings that involve sensitive data. > [!NOTE] > Note > > This filter is mutually exclusive with the Rule Name filter. Selecting one automatically removes the other. |
| Last Checked | Filters findings by the date they were last evaluated during a posture scan. |
| Date Modified | Filters findings by the date they were last updated. |
| Owner | Filters findings by the user designated as the owner of the finding. |
| Org Name | Filters findings by the organization they belong to. > [!NOTE] > Note > > This filter is visible only when multiple organizations are selected. It is not available when a single organization is selected. The Org Name column in the findings table follows the same behavior. |
| Policy Name | Filters findings by the security posture policy that generated them. |
| Region | Filters findings by the cloud region of the affected asset. |
| Regulation | Filters findings by the regulatory framework they are associated with, such as GDPR or HIPAA. |
| Rule Category | Filters findings by the category of the posture rule that triggered them, such as encryption or access control. |
| Rule Name | Filters findings by the specific posture rule that generated them. > [!NOTE] > Note > > This filter is mutually exclusive with the Is Sensitive Data Finding filter. Selecting one automatically removes the other. |
| Severity | Filters findings by severity level: Very High, High, Medium, or Low. |
| Standard | Filters findings by the security standard they are associated with, such as CIS or NIST. |
| Status | Filters findings by their current status: Open, Fixed, Suppressed, Closed, or Passed. |
| Tags | Filters findings by the tags applied to the associated cloud resource. |

#### Viewing findings metadata

Click the **show metadata** icon at the end of a row and select **View Details** to open the metadata panel. This displays the posture rule name, policy name, and other details for that finding.

![Overview of security posture findings with details on AWS Glue Data Catalog issues.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/findings-metadata.png)

#### Customizing visible columns

Click **Column Selector** at the end of the grid to include or exclude columns from the findings table.

![Overview of security posture findings and open issues in a dashboard interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/column-selector-1.png)

![Dashboard displaying security posture findings and open findings statistics for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/column-selector-2.png)

#### Grouping findings

Use the **Group by** menu to organize findings by:

- None
- Rule
- Owner
- Policy
- Asset

> [!NOTE]
> Note
> 
> When grouping by Asset with a large number of items, apply one or more filters first to narrow your results.

![Overview of open findings, highlighting security posture and total counts for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/group-by(1).png)

#### Saving and managing views

Saved views allow you to store a combination of filters and quickly return to a specific set of results without reapplying them each time.

1. Apply the required filters.
2. Click **Save View** in the top-right corner of the findings page.

![Dashboard displaying open findings, security posture, and resolved findings over time.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-22 at 11.04.02 AM.png)
3. To access your saved views, click **Saved Views**. The saved views panel opens on the left.

![Dashboard displaying open findings and security posture metrics for AWS resources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-22 at 11.06.42 AM.png)

### Managing findings

Once findings are generated, you can take actions on them directly from the dashboard. The following sections describe the actions you can perform on findings from the dashboard.

#### Suppressing a finding

Suppressing a finding removes it from the active findings list without deleting it. Use this option for findings you have reviewed and determined require no immediate action.

1. Select the finding you want to suppress.
2. Click **Suppress** as indicated below.

![Dashboard displaying open findings, security posture, and resolved findings over time.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/suppress-1(1).png)
3. In the **Suppress Finding(s)** dialog, enter a reason (up to 30 characters) and click **Suppress Findings**.

![Popup window to suppress selected findings with an input field for reasons.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/suppress-2(1).png)

To suppress multiple findings simultaneously, click the down arrow next to the column headings and select either **Select all across all pages** or **Select all on this page**.

![Dashboard displaying security findings, including total counts and selection options for actions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/suppress-3(1).png)

#### Unsuppressing a finding

Use this option when you need to re-evaluate or act on a previously suppressed finding. To unsuppress a finding:

1. Select a finding with **Suppressed** status.
2. Click **Unsuppress**.

![Overview of security posture findings with suppressed items and options to unsuppress them.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/unsuppress(3).png)

> [!NOTE]
> Note
> 
> - Only findings with Suppressed status are eligible for this action. Findings with other statuses cannot be unsuppressed.
> - The time required to suppress or unsuppress findings varies depending on the number of findings selected.
> - When an asset is deleted from your IaaS connector account, Securiti automatically updates the status of all associated findings to **Closed** on the next posture scan.
> - Fixed findings cannot be suppressed or unsuppressed

#### Changing the owner or assignee

Assigning the right owner or assignee ensures accountability and routes findings to the team members best placed to act on them.

- To change the **owner**: click the ellipsis (**⋯**) next to a finding, select **Change Owner**, select a user from the Search User dropdown, and click **Yes, continue**.

![Overview of security posture findings with options to change owner and assignee.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/owner-assignee-1.png)

![Prompt to change the owner of a security posture ticket in the application.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/owner-assignee-2(1).png)
- To change the **assignee**: repeat the same steps above and select **Change Assignee**.

### Reviewing the details of a finding

The finding details page provides a comprehensive view of each finding, giving you the context needed to understand, investigate, and remediate it effectively.

#### Viewing evidence for a finding

Evidence provides the underlying data that triggered a finding, helping you understand the exact misconfiguration detected and assess its impact. To view the evidence, click **View Evidence** on the finding's details page. This provides a detailed view of the misconfiguration that Securiti detected.

![Overview of security posture findings with options to view details and evidence.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/evidence-1.png)

![Security posture policy details for AWS Glue Data Catalog encryption settings displayed on screen.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/evidence-2.png)

#### Viewing remediation steps for a finding

Remediation steps provide step-by-step guidance for resolving a misconfiguration directly at your data system console. To view them, click **View Remediation Steps** on the finding's details page.

![Overview of security posture findings with options for remediation steps and account details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/remediation-1.png)

![Instructions for AWS remediation steps in the Kinesis dashboard interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/remediation-2.png)

#### Viewing relationships of a finding in Graph Explorer

Graph Explorer helps you understand how a finding connects to its related entities, providing context for investigation and remediation. To open a finding in Graph Explorer, click **View Details**.

![Overview of AWS Glue Data Catalog security posture and encryption status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/view-details.png)

The left panel lists the related entity types, such as Security Posture Finding, Security Posture, and Rule, along with their counts. Select an entity type to explore its details. The main area displays a visual graph of the relationships between these entities. Below the graph, the **Properties** section shows key attributes of the selected entity, including Rule Name, Asset Type, Hosting, and Severity.

#### Running auto-remediation for a finding

Auto-remediation reduces manual effort by allowing Securiti to automatically apply fixes to identified misconfigurations in supported IaaS cloud accounts. To initiate auto-remediation, follow the steps on the finding's details page. For more information, see [Automatic Remediation](/latest/docs/remediating-security-misconfigurations#remediating-misconfigurations-automatically).

#### Exporting findings to a CSV file

Exporting findings allows you to share posture scan results with stakeholders outside the platform and use them for reporting and offline analysis.

1. On the Security Posture Findings page, select the findings you want to export using the checkboxes.
2. Click **Export**.

![Dashboard displaying open findings, security posture, and export options for data analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/export(2).png)
3. Securiti sends an email notification when the file is available for download.
4. Open the email and click the **Findings URL** to view the finding directly on the Security Posture Findings page or in Graph Explorer.

#### Viewing security posture rules in Rule Center

The Rule Center gives you visibility into all posture rules available in Securiti, helping you understand what is being evaluated and why findings are generated. Click **Rule Center** in the top-right corner of the findings page to view all available posture rules. For more information, see [Security posture rules library and severity](/latest/docs/security-posture-rules-library-and-severity), and [Rule center overview](/latest/docs/rule-center-overview).

![Dashboard displaying security posture findings and statistics for open and resolved issues.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-22 at 11.08.32 AM.png)
