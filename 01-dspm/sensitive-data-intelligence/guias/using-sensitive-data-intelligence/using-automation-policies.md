---
title: "Using Automation Policies"
slug: "using-automation-policies"
updated: 2026-09-25T04:55:46Z
published: 2026-09-25T04:55:46Z
canonical: "helpcenter.securiti.ai/using-automation-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using Automation Policies

**Scenario**

As a Data Compliance Officer, you are responsible for making sure that security and compliance findings across your data environment get resolved quickly. Reviewing findings from File Insights, Quarantine, ROT, Security Posture, and other sources by hand, then routing each one to the right team, is slow and easy to lose track of. With automation policies, you define the scope and conditions once, and Securiti creates ServiceNow tasks or Jira tickets automatically as matching findings appear. This gives your teams a consistent, auditable remediation workflow instead of manual triage.

Automation policies let you take action automatically on file findings and file entities that Securiti generates at runtime, based on a scope and conditions you define. When a finding matches your conditions, Securiti creates a ServiceNow task, a Jira ticket, or an email notification without any manual triage. This shortens the time between a finding being detected and the right team acting on it.

## Overview

An automation policy evaluates findings and file entities against a scope you define, then triggers an action in a third-party system or by email when a finding matches. Once you activate a policy, Securiti automatically detects matching findings and executes the configured actions using the following integrations:

- Create ServiceNow tasks or Jira tickets for issue resolution
- Trigger email notifications
- Generate findings in Google Cloud Security Command Center (SCC)

After you assign a task or ticket, the relevant team member can resolve the issue directly in Securiti. You can track progress on the Findings dashboard and in Graph Explorer.

> [!NOTE]
> Note
> 
> Automation policies do not support the multi-org feature.

## Entity types and example use cases

| Entity Type | Description | Use Case |
| --- | --- | --- |
| File Insights | The File Insights policy analyzes files and extracts useful information to help identify risks, patterns, or compliance issues. Automation policies operate on the set of files scoped in the selected File Insights policies. | When you select File Insights, an Automation policy triggers remediation actions for files within the scope of the selected Insights policies. These actions can include assigning a ServiceNow task or generating a Jira ticket for the user responsible for addressing the findings and issues associated with the in-scope files. > [!NOTE] > **Note** > > You can group File Insights by the following grouping attributes: > > - Asset Name > - File Owner > - Securiti Tag Category |
| File Quarantine | The File Quarantine policy isolates suspicious or non-compliant files to prevent them from harming systems, users, and data environments. Automation policies operate on the set of files scoped in the selected File Quarantine policies. | When you select File Quarantine, an Automation policy triggers remediation actions for files within the scope of the selected Quarantine policies. These actions can include assigning a ServiceNow task or generating a Jira ticket for the user responsible for addressing the findings and quarantined files. > [!NOTE] > Note > > You can group File Quarantine by the following grouping attributes: > > - Asset Name > - File Owner > - Securiti Tag Category |
| File ROT | The File ROT policy detects and addresses redundant, obsolete, or trivial data to reduce clutter, storage costs, and risk exposure. Automation policies use the scope defined by Retention policies, not individual file findings. Automation policies operate on the set of files scoped in the selected File ROT Policies. | When you select File ROT, an Automation policy triggers remediation actions for files within the scope of the selected ROT policies. These actions can include assigning a ServiceNow task or generating a Jira ticket for the user responsible for addressing the findings and ROT-identified files. > [!NOTE] > Note > > You can group File ROT by the following grouping attributes: > > - Asset Name > - File Owner > - Securiti Tag Category |
| Security Posture Finding | Security Posture Findings address the violations of the established security rules and policies, potentially leading to data vulnerabilities or non-compliance. Automation policies operate on the set of Security Posture Findings. | For each posture rule, a misconfiguration creates a finding based on the asset, rule, and posture policy. This lets the relevant person take the appropriate remediation action to fix the misconfiguration. For example, on the **Security** **Posture Findings** page, you can identify that encryption is not enabled for your AWS Redshift cluster. You can then set up an automation policy that creates a ServiceNow or Jira ticket to turn on encryption for the cluster and assign it to the relevant team member. > [!NOTE] > **Note** > > You can group Security Posture Finding by the following grouping attributes: > > - Cloud Asset > - Rule |
| Structured Data Finding | Just as File Findings display insights related to various files, Structured Data Findings present insights into data located within tables and columns of structured databases. Automation policies operate on the set of Structured Data Findings. | This category covers findings from the Structured Data Insights policy. Just as File Findings display insights related to various files, **Structured Data Findings** present insights into data located in tables and columns of structured databases. > [!NOTE] > **Note** > > You can group Structured Data Finding by the following grouping attributes: > > - Data Asset > - Table > > Data Asset is a mandatory grouping attribute. |
| Test Finding | These are the findings against the tests and address the violations of the established rules, potentially leading to data vulnerabilities or non-compliance. You can explore, identify, and resolve compliance challenges and roadblocks. Automation policies operate on the set of Test Findings. | Using **Compliance Test Findings** you can create an Automation policy that assigns a ServiceNow or Jira ticket to remediate a failing compliance test. > [!NOTE] > **Note** > > You can group Test Finding by the grouping attribute **Cloud Asset**. |

> [!NOTE]
> Note
> 
> - Grouping attributes limit how many tickets a policy creates when its scope contains many findings. For instance, if 100 files are in scope and you group by Asset Name, and that produces two groups, Securiti creates two tickets, not 100. If you don't select a grouping attribute, Securiti creates one ticket for each finding by default.
> - For File Insights, File Quarantine, and File ROT, the automation policy defines scope only. These policies don't generate findings themselves. The underlying File Insights, File Quarantine, or File ROT policy generates the finding, and the automation policy acts on the files it scopes.

## Prerequisites

- You must have a subscription to the **Sensitive Data Intelligence**, **Security Posture Management**, and **Compliance** modules.
- Before you create an automation policy that assigns ServiceNow tasks or Jira tickets, set up and activate the relevant data system, and confirm it's enabled for automation policy integration.
- You can only create Automation policy on ServiceNow Cloud and Jira Cloud connectors.

## Setting up ServiceNow or Jira data system

You can create multiple ServiceNow and Jira instances, and you can enable automation policy integration for more than one. However, when you configure an automation policy, you can select only one ServiceNow instance and one Jira instance to create tickets. To create and assign tickets, confirm you have an active instance and the required permissions before you continue.

1. In Securiti open **Integrations**, then choose **Monitored Data Systems**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-62H2Q2QP.png)
2. Apply the **Data System Type** filter and set it to **ServiceNow** or **Jira Cloud** to confirm whether a connector is active, as shown below.
  - If Securiti shows 0 instances, no active ServiceNow or Jira Cloud connector exists.
    - To set up a new connector, see [ServiceNow](/latest/docs/servicenow-connectors) or [Jira Cloud](/latest/docs/jira-cloud-connectors-1) connector documentation.
    - To activate an existing instance, see [ServiceNow](/latest/docs/connecting-servicenow-with-securiti) or [Jira Cloud](/latest/docs/activate-the-jira-cloud-self-hosted-connector-in-securiti) connector documentation.
  - If Securiti shows one or more instances, confirm the instance you want to use has a green check mark next to it, which indicates it's activated.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6922VZK6.png)
3. Click your instance and go to the **General** tab. Under **Policy Integration**, mark the **Allow Automation Policy Integration** checkbox, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6ZYCHB5P.png)

## Interactive demos

These click-through demos show how to perform actions step by step. Click the **Start Demo** button to begin. Then, click the **Next** button or use the **right arrow** key on your keyboard to proceed, and the **left arrow** key to go back. These demos may include screens from multiple features to illustrate the complete procedure.

### Automation policy for AWS records

See how Securiti lets you create an Automation policy to perform automatic ticket generation based on the discovered insights from AWS records, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/s5ajfp4izudd?embed=inline)

### Automation policy for Google BigQuery records

See how Securiti lets you create an Automation policy to perform automatic ticket generation based on the discovered insights from Google BigQuery records, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/tdcp0gqhny1a?embed=inline)

> [!NOTE]
> Note
> 
> To see more demos related to policies, refer to the following help center articles:
> 
> - [Interactive Demos: Discover and Classify Sensitive Data for AWS](/latest/docs/sensitive-data-intelligence-interactive-demos)
> - [Interactive Demos: Discover and Classify Sensitive Data for GCP](/latest/docs/interactive-demos-discover-and-classify-sensitive-data-for-gcp)
> - [Interactive Demos: Discover and Classify Sensitive Data for SharePoint Online](/latest/docs/policies-2)

## Using the Automation policies page

The Automation **Policies** page lets you manage and analyze your automation policies in one place.

- Use the filters at the top to view policies by **Date Created**, **Date Modified**, **Entity Type**, **Integration Name**, **Policy ID**, and other properties, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-B23ACO6R.png)
- Use the search bar to find a policy by its name, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1MU0UN9B.png)
- View summary metrics at the top of the page, including the total number of automation policies, active policies, tickets, policy owners, and ticket owners, as shown below

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-367DKI43.png)
- Use the **Column Selector** to show or hide columns such as **Status**, **Policy ID**, **Policy Name**, **Data Scope**, and **Entity Type**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-MQ9LGBCW.png)
- Use the **Status** toggle next to a policy to activate or deactivate it, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-USSL680B.png)
- Click the expand arrow next to a policy to view the tickets created under it, including the ticket number, summary, priority, and status, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Q2LUFVWP.png)
- Click **Show Policy Metadata**, and select **Explore** to view file relationships in **Graph Explorer**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KBKPGF16.png)
- Click the options menu (three dots) on the right side of a policy entry, to view, edit, clone, or delete the policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GB0VS0BQ.png)

> [!CAUTION]
> Warning
> 
> When you delete an automation policy, Securiti automatically removes all tickets created under that policy. Securiti doesn't delete the corresponding tickets in ServiceNow or Jira; you must delete them manually from their respective portals. After you delete the policy, Securiti no longer maintains a connection to those tickets and stops performing remediation actions on them, since they're no longer tied to an active policy.
