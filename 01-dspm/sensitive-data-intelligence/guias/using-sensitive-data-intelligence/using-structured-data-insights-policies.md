---
title: "Using Structured Data Insights Policies"
slug: "using-structured-data-insights-policies"
updated: 2026-09-22T12:06:13Z
published: 2026-09-22T12:06:13Z
canonical: "helpcenter.securiti.ai/using-structured-data-insights-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using Structured Data Insights Policies

**Scenario**

As a Data Governance Manager, you are responsible for ensuring sensitive data stored across your organization's databases stays properly classified and compliant with regulatory requirements. Manually querying every table and column across your structured data systems to catch misplaced or high-risk data is slow and easy to get wrong. With Structured Data Insights policies, you can define targeted queries against your tables and columns to surface sensitive or high-risk data, so you can catch compliance risks and data quality issues before they escalate.

Structured Data Insights policies let you identify, analyze, and manage sensitive data across structured data systems. These policies strengthen data governance by detecting sensitive information and surfacing potential risks at the column and table levels.

When you create a Structured Data Insights policy, Securiti filters the structured data objects identified during discovery scans based on the scope and query conditions you define. You can also use policy findings to trigger workflow automation by creating workflow nodes in the Workflow Generator. This lets you automate downstream actions, such as investigation, remediation, or approval processes, so you can efficiently manage sensitive data across your structured data systems.

## Use cases

The following examples show how you can use Structured Data Insights policies to solve common data governance and compliance challenges.

### Identify misplaced customer data

A multinational automobile company suspects that customer records belonging to U.S. residents have been unintentionally stored in a database located in China. To verify the issue, the company creates a Structured Data Insights policy that searches the database for U.S. Social Security Numbers (SSNs).

If the policy identifies matching records, the company can review the findings, investigate the affected data, and remediate the issue to maintain regulatory compliance and protect customer information. If no findings are returned, the company can confidently conclude that customer records remain properly segregated across regional databases.

### Validate database organization

A multinational bank wants to verify that customer information is accurately categorized and stored within its structured data systems. The bank creates a Structured Data Insights policy to analyze database metadata and identify inconsistencies, such as transaction records with missing attributes, incomplete metadata, or records stored in incorrect tables.

The policy helps the bank identify data quality issues, reorganize records where necessary, improve data accuracy, and maintain compliance with internal governance policies and regulatory requirements.

## Prerequisites

Before you create a Structured Data Insights policy, ensure your environment meets the following requirements:

- Sensitive Data Intelligence is enabled for your tenant.
- Data Command Graph is enabled for your tenant.
- Your user role has the required permissions to create and manage Structured Data Insights policies. For more information, see [Sensitive Data Intelligence Roles and Permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions).
- Structured Data Insights policies support multi-organization environments. For more information, see [Changing your Organization](/latest/docs/system-settings-managing-organizations).

> [!NOTE]
> Note
> 
> - The Structured Data Insights policy extends the File Insights policy and currently supports structured data tables and columns.
> - If these features are not available, contact your Customer Success Manager or Account Representative to confirm whether they are included in your plan and whether your tenant meets the eligibility requirements for activation.

## Interactive demos

These click-through demos show how to perform actions step by step. Click **Start Demo** to begin. Then click **Next**, or use the **right arrow** key on your keyboard, to proceed, and the **left arrow** key to go back. These demos may include screens from multiple features to illustrate the complete procedure.

### Structured Data Insights Policy for AWS records

See how Securiti lets you create a Structured Data Insights policy to identify sensitive data from AWS records, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/bah2pephyzah?embed=inline)

### Structured Data Insights Policy for Google BigQuery records

See how Securiti lets you create a Structured Data Insights policy to identify sensitive data from Google BigQuery records, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/qs9hacyyjqmj?embed=inline)

> [!NOTE]
> Note
> 
> To see more demos related to policies, refer to the following help center articles:
> 
> - [Interactive Demos: Discover and Classify Sensitive Data for AWS](/latest/docs/sensitive-data-intelligence-interactive-demos)
> - [Interactive Demos: Discover and Classify Sensitive Data for GCP](/latest/docs/interactive-demos-discover-and-classify-sensitive-data-for-gcp)
> - [Interactive Demos: Discover and Classify Sensitive Data for SharePoint Online](/latest/docs/policies-2)

## Using the Structured Data Insights policies page

The Structured Data Insights Policies page lets you create, manage, and monitor your Structured Data Insights policies from a centralized location.

- Use the filters at the top of the page to view policies by **Date Created**, **Date Modified**, **Last Executed**, **Policy ID**, **Policy Name**, and other properties, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZHCV3IUG.png)
- Use the search bar to find a policy by its name, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TD4DCSMY.png)
- View summary metrics at the top of the page, including the total number of policies and the number of active policies, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1LMA6J55.png)
- Use the **Column Selector** to show or hide columns such as **Status**, **Policy ID**, **Policy Name**, **Findings**, **Data Scope**, and others, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DIXV8V8Z.png)
- Use the **Status** toggle next to a policy to activate or deactivate it, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-26EAU3TC.png)
- Click **Show Policy Metadata**, then select **Explore** to view file relationships in **Graph Explorer**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YC10GME3.png)
- Click the options menu (three dots) on the right side of a policy entry to view, edit, clone, or delete the policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Y33K55YI.png)

> [!NOTE]
> Note
> 
> - Editing the scope of a policy updates the findings associated with that policy.
> - Cloning a Structured Data Insights policy creates an identical copy of the original policy.
> - Deleting a Structured Data Insights policy permanently removes the policy and all findings associated with it.
