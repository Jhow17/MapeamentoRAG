---
title: "Using Security Posture Policies dashboard"
slug: "using-security-posture-policies-dashboard"
updated: 2026-09-21T15:03:05Z
published: 2026-09-21T15:03:05Z
canonical: "helpcenter.securiti.ai/using-security-posture-policies-dashboard"
area: dspm
modulo: security-posture-management
tipo: guia
data_captura: 2026-10-06
---

# Using Security Posture Policies dashboard

**Scenario**

As a Data Security Officer, you oversee rule configuration for both cloud servers and SaaS applications. When you set rules by hand, you fall behind and often overlook dangerous configuration errors. With Securiti’s posture policies, system-generated rule sets are implemented across environments in just a few clicks. You detect issues instantly and correct them, tightening protection and slashing response time.

Security posture policies help you reduce data breach risks, enhance data sharing security, and improve compliance. Each policy contains a set of posture rules that check your Infrastructure as a Service (IaaS) or Software as a Service (SaaS) systems for security misconfigurations, including access controls, network security, encryption in transit and at rest, backups, and security alerts.

Securiti automatically generates all policies on the platform. When you connect an IaaS cloud account (AWS, GCP, Azure, or OCI) and enable the security posture scan, Securiti automatically creates a posture policy for that cloud. For SaaS data systems, such as Microsoft 365 SharePoint Online or Workday, Securiti generates posture policies once you configure and activate the relevant connector and initiate a posture scan from the Permissions tab on your Data Systems page.

> [!NOTE]
> Note
> 
> For Sovereign environments, Security Posture Management is available only for self-hosted data systems supported for these environments.

### Prerequisites

Before using Security Posture policies, make sure you have the following:

- A **Security Posture Management** module subscription.
- A **Sensitive Data Intelligence (SDI)** module subscription.
- Permission to run posture scans for IaaS or SaaS cloud accounts.
- Your SaaS or IaaS cloud account integrated with Securiti. For details, see:
  - [Supported cloud native services for posture policy rules](/latest/docs/supported-cloud-native-services-for-posture-policy-rules)
  - [List of Supported Cloud Native Services](/latest/docs/data-security-posture-management-solution#list-of-supported-cloud-native-services)

> [!NOTE]
> **Note**
> 
> The Security Posture Management and Sensitive Data Intelligence subscriptions work together to identify security and compliance-related misconfiguration risks, with a focus on sensitive data in your SaaS or cloud accounts.

### Navigating to the Policies dashboard

You can access the Security Posture Policies page in two ways:

- Click the jewel icon on the left panel, select **Policies**, then go to the **Security Posture** section.

![Dashboard displaying security findings and risk severity metrics for analysis and monitoring.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/nav-policies-1.png)

![Overview of security posture policies with active and total policy counts displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/nav-policies-2.png)
- Alternatively, from the Security Posture Findings page, click the **Manage** **Policies** link in the top navigation.

![Dashboard displaying security posture findings and open issues for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/nav-policies-3.png)

### Dashboard overview

The Security Posture Policies dashboard gives you a consolidated view of all system-generated posture policies across your IaaS and SaaS environments. The following sections describe the key elements of the dashboard.

#### Policy summary

At the top of the policies list, two summary counts give you an at-a-glance view of your policies:

- **Total Policies:** Displays the total number of security posture policies in your environment.
- **Active Policies:** Displays the number of policies currently enabled and running posture scans.

![Overview of security posture policies, including total and active policies listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/policy-summary.png)

#### Searching policies

Use the **Search by policy name** bar to locate a specific policy by name.

![Overview of security posture policies with a search feature for policy names.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/search-policy.png)

#### Filtering policies

Use the filter bar to narrow policies by one or more properties. Click **+** to add a filter, select a property, choose an operator, and click **Apply**.

![Filter options for asset types in a cloud security policy management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/policy-filters.png)

Each filter supports the following operators:

| Operator | Description |
| --- | --- |
| Is one of | Returns policies that match any of the selected values. Use this to include multiple options in your results. |
| Is not one of | Returns policies that do not match any of the selected values. Use this to exclude multiple options from your results. |
| Is equal to | Returns policies that match exactly one specified value. |
| Is not equal to | Returns policies that do not match the specified value. |
| Before | Returns policies with a date value earlier than the specified date. Applies to date filters only. |
| After | Returns policies with a date value later than the specified date. Applies to date filters only. |

The following table describes the available filters.

| Filter | Description |
| --- | --- |
| Asset Type | Filters policies by the type of asset they apply to, such as an S3 bucket or Azure Blob Storage container. |
| Cloud Provider | Filters policies by the cloud provider, such as AWS, Azure, or GCP. |
| Date Created | Filters policies by the date they were first generated. |
| Date Modified | Filters policies by the date they were last updated. |
| Policy ID | Filters policies by their unique identifier. |
| Policy Name | Filters policies by name. |
| Rule Type | Filters policies by the type of posture rule associated with them. |
| Severity | Filters policies by the severity level of their associated rules: Very High, High, Medium, or Low. |
| Status | Filters policies by their current status: Active or Inactive. |

#### Saving and managing views

Saved views allow you to store a combination of filters and quickly return to a specific set of results without reapplying them each time.

1. Apply the required filters.
2. Click the ellipsis icon (**⋯**) in the top-right corner and select **Save View**.

![Overview of security posture policies with active policies and options to save views.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/save-view(2).png)
3. To access your saved views, click **Saved Views** in the top-right corner. The saved views panel opens on the left.

![Overview of security posture policies with active policies and details displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/another-saved-view.png)

![Overview of security posture policies with active findings and severity levels displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saved-view.png)

### Viewing policy details

The policy details page provides a comprehensive view of each policy, giving you the context needed to understand its scope, rules, and findings.

#### Policy Details page

To open a policy, click on it directly, or click the ellipsis icon (**⋯**) next to it and select **View**.

![Details of the active security posture policy for Workday assets are displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/details-page.png)

Each policy has a details page with three tabs:

| Tab | Description |
| --- | --- |
| Summary | Displays the policy status, name, description, scope, posture rules, and responses. |
| Logs | Displays all activity that Securiti logs against the policy. |
| Policy Findings | Displays all findings that Securiti generates for the policy. |

#### Exploring policy metadata

The Explore view uses **Graph Explorer** to display how a policy connects to its related entities, helping you understand the full scope of what the policy covers. To open it, click the **show metadata** icon next to a policy and select **Explore**.

![Overview of security posture policies with active and total policy counts displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/explore.png)

The left panel lists the related entity types, such as Security Posture, Data System, Securiti User, Security Posture Finding, Security Posture Rule, and Cloud Asset, along with their counts. Select an entity type to view its details. The main area displays a visual graph of the relationships between these entities.

Below the graph, the **Properties** section shows key attributes of the selected entity, including ID, Name, Policy Category, Active status, Severity, and Target Type.

![Overview of security posture policy for Workday assets with related components and findings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/graph.png)

### Accessing the Rule Center

The Rule Center gives you visibility into all posture rules available in Securiti, helping you understand what each policy evaluates. To open the Rule Center, click the ellipsis icon (**⋯**) in the top-right corner and select **Rule Center** from the dropdown. For more information, see [Security posture rules library and severity](/latest/docs/security-posture-rules-library-and-severity) and [Rule center](/latest/docs/rule-center-overview).

### Viewing Security Posture Findings

To navigate from the Policies dashboard to the Security Posture Findings dashboard, click **View Findings** in the top-right corner. For a full walkthrough of the Findings dashboard, see [Using Security Posture Findings dashboard](/latest/docs/using-security-posture-findings-dashboard).

## Related

- [Getting Started with Security Posture Management](/getting-started-with-security-posture-management.md)
- [Using Security Posture Management](/using-security-posture-management.md)
