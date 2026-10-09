---
title: "Using Cross Border Transfer policies"
slug: "using-cross-border-transfer-policies"
updated: 2026-08-18T10:58:06Z
published: 2026-08-18T10:58:06Z
canonical: "helpcenter.securiti.ai/using-cross-border-transfer-policies"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Using Cross Border Transfer policies

**Scenario**

As a Privacy Compliance Officer, you're responsible for ensuring your organization's data handling complies with privacy regulations across multiple jurisdictions. Manually tracking whether data stored or accessed across borders aligns with regulations like EU GDPR or SG PDPA is complex and leaves potential violations undetected until it's too late. With Cross Border Transfer Policies, you automate the detection of illegal cross-border data transfers by continuously evaluating where your data is stored and accessed against the requirements of applicable regulations across all connected data systems. This ensures violations are surfaced immediately with supporting evidence and remediation guidance, keeping your organization audit-ready and reducing the risk of non-compliance penalties.

Cross-border data transfer policy let you mitigate the risk associated with illegal data access across borders and assist with the remediation through governance workflows. Cross-border transfer policies can be used to incorporate a wide range of embedded global regulatory insights, enabling the analysis of data access scenarios that might result in compliance breaches. Automated data mapping determines the location, type, and access point of data, while the policy engine cross-references this information with relevant regulations. If a violation is detected, such as personal data stored in Germany being accessed from Singapore, the system issues an alert and initiates corrective actions.

### Cross Border Policy types

Securiti provides out-of-the -box Cross Border Transfer Policies based on:

- Data Location - The policy evaluates the **Data Location** you configured while activating the data system connector, and compares it with the **Data Location** documented in the selected regulation. For More information, see [prerequisites for Cross Border Transfer Policies based on Data Location](https://helpcenter.securiti.ai/docs/cross-border-transfer-policies#prerequisites-for-cross-border-transfer-policies-based-on-data-location). For example, You create a data system instance for the Starburst connector and define its Location as Singapore. The policy will generate alerts and recommendations, as the Data Location you defined while creating an instance matches the **Data Location** documented in the **SG PDPA** regulation.
- Data Access Location - The policy evaluates the location from where the data is accessed and compares it with the exempted locations documented in the selected regulation.

### Supported Data Systems for Cross Border Transfer Policies

Cross Border Transfer Policies Based on the **Data Location** is supported for:

- All Structured and Unstructured Data Systems.

Cross Border Transfer Policies Based on the **Data Access Location** is supported for:

- Starburst
- Microsoft 365 SharePoint Online

### Prerequisites for Cross Border Transfer Policies based on Data Location

To get Cross Border Transfer alerts and recommendations based on the **Data Location**, you must:

- [Set up a Securiti variables: Platform name pod or elastic pod.](/v1/docs/securiti-pods-and-elastic-pods)
- Configure and activate the relevant data system connector
- Perform a discovery scan for relevant data system connector instance
- Define **Data Subject Types**, e.g. employees, job applicants, prospects, partners, etc. for the Starburst asset in the data mapping automation module. See [creating and editing data subjects](https://helpcenter.securiti.ai/docs/creating-and-editing-data-subjects).
- Define an Institute in the data mapping automation module. Specify the **Primary Covered Entities** e.g., Educational Institutions, Medical Industry, and **Secondary Covered Entities** e.g., Public Universities, Healthcare Providers, etc. See [creating and editing institutions](/v1/docs/creating-and-editing-institutions)

### Prerequisites for Cross Border Transfer Policies based on Data Access Location

To get Cross Border Transfer alerts and recommendations based on the **Data Location**, you must:

- [Set up a Securiti variables: Platform name pod or elastic pod.](/v1/docs/securiti-pods-and-elastic-pods)
- Configure and activate the relevant data system connector
- Perform a discovery scan for relevant data system connector instance
- [Configure an IAM Metadata source for the relevant data system connector](/v1/docs/configuring-access-intelligence-scans-using-access-scan-definitions-and-iam-metadata-sources)
- [Configure an Access Scan Definition for the relevant data system connector](/v1/docs/configuring-access-intelligence-scans-using-access-scan-definitions-and-iam-metadata-sources)

> [!NOTE]
> **Note**
> 
> Cross Border Data Transfer Policies for Starburst and SharePoint utilize the metadata gathered from Starburst Activity Analysis. Therefore, it is mandatory to configure Activity Analysis for Starburst and Sharepoint to receive alerts for your cross border data transfers using policies.
> 
> For more information on Starburst Activity Analysis, see [Configuring Activity Analysis for Starburst](/latest/docs/starburst#activity-analysis).
> 
> For more information on SharePoint Activity Analysis, see [Configuring Activity Analysis for SharePoint](/latest/docs/microsoft-365-sharepoint-online#access-intelligence).
- Define **Data Subject Types**, e.g. employees, job applicants, prospects, partners, etc. for the Starburst asset in the data mapping automation module. See [creating and editing data subjects](/v1/docs/using-data-mapping-automation).
- Define an Institute in the data mapping automation module. Specify the **Primary Covered Entities**e.g., Educational Institutions, Medical Industry, and **Secondary Covered Entities** e.g., Public Universities, Healthcare Providers, etc. See [creating and editing institutions](/v1/docs/creating-and-editing-institutions)

### Viewing cross-border transfer findings

Cross Border Transfer policies let you mitigate the risk associated with illegal data access across borders and assist with the remediation through governance workflows.

To view the Cross Border Transfer findings:

- In Securiti, near the upper left corner, click the jewel icon, and choose **Findings** as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FLBQQGRY.png)
- From the left panel, choose **Cross Border Transfer**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZSA4EVXK.png)
- You can view the following on the Cross Border Transfer Findings page:

| State | Explanation |
| --- | --- |
| Open Findings | A newly detected finding that requires attention. |
| Suppressed | A finding that has been manually acknowledged but intentionally ignored. |
| Fixed | A finding that has been addressed or no longer applies. |
- You can view counts for Open, Fixed & Suppressed findings, with their trendlines based on the past week to 12 months.
- You can view the counts for Total Findings and Open Findings.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 1.22.53 PM.png)
- The **Group by** button gives three grouping attribute options, i.e, **Policy**, **Data Source**, and **Regulations**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 1.24.58 PM.png)
- Below the widgets, there is a search bar to sort the findings based on the Policy, Data System, or Asset.
- Click **+** to sort the Findings. You can filter the Findings based on:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-I2X47FLU.png)
  - Asset Name (Name of the data system instance that you create while configuring the connector)
  - Data System Type
  - Finding Name
  - Finding ID
  - Policy
  - Regulations
  - Status
- You can suppress the Findings and change the assignee for a particular Finding. To suppress a Finding or change its assignee, select the Finding, and click on the **Suppress Finding** button. The status of the finding will be changed to **Suppressed**. To Change the Assignee, select the finding, click on the **Change Assignee** button, and select the user in the popup to which you must assign the finding.
- For each of the Finding, you can view the Evidence related to potential violation. To view the evidence related to a Finding, click **View Evidence** in the **Evidence** column in the grid.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-K6AV82A3.png)

### Managing Cross Border Transfer Policies

You can manage the out-of-the-box policies to:

- View the out of the box policies and details associated with it such as Regulation, Cross Border Type, Responses, etc.
- Activate or Deactivate the policies
- Edit the policies to change the Response of the policies

To access the out-of-the-box Cross Border Transfer Policies:

- Click **Manage Policies** on the Cross Border Transfer Findings page

OR
- In Securiti, near the upper left corner, click the jewel icon, and choose **Policies**.
- From the left panel, choose **Cross Border Transfer**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 1.33.54 PM.png)

#### Filtering the Cross Border Transfer Policies

You can sort and filter the Cross Border Transfer Policies based on the following properties:

- Cross Border Type, such as Data Access Location and Data Location
- Date Created
- Date Modified
- Policy ID
- Regulation
- Policy Name
- Status

To filter the policies:

- Click **+** near the top of the page
- Select the property based on which you must sort the policies. For example, **Regulation**
- From the menu, select the relevant operator
- Enable the checkbox for the relevant regulation, such as **EU GDPR**
- Click **Apply**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SRV0AU9Z.png)

#### Editing the Cross Border Transfer Policies

You can **Edit** the **Responses** of out-of-the-box Cross Border Transfer Policies to configure the actions that Securiti will trigger if any potential violation occurs. You can define the response actions as per your organization's workflows such as alerting the Data Governance Officers if sensitive data is accessed outside the regulatory jurisdiction in which your business is operating. To Edit the Policy:

1. To edit an existing Policy, at the right end of its tile choose **Options (three dots) > Edit**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-T5L44UFI.png)
2. In the **Responses** section, the **Generate Findings** toggle is already enabled. Choose the relevant severity level ranging from **Very High**, **Medium** to **Very Low**. You can set the severity of the Cross Border Transfer Findings as per your requirements, and Findings generated whenever a policy violation is detected.
3. (Optional) To configure email notifications for specific users, enable the toggle in the **Send an Email Notification** area. Select the email addresses from the menu. Select the email template from the **Email notification template** menu. Specify the **Notification Limit**.
4. (Optional) To trigger a workflow for a file insights policy, enable the **Trigger Workflow** toggle and add the relevant workflow. For more information, see the [Policy alerts](/v1/docs/policy-alert) node documentation.
5. Near the upper right corner of the page, click **Update**.

#### Examples

Let’s take an example of the Cross Border Transfer Policy to avoid violation of Singapore’s Personal Data Protection Act (PDPA). Using this policy, you can get alerts and recommendations for cross border transfer. To view the Cross Border Transfer related Findings:

1. Create a data system instance for the Databricks connector and define its Location as Singapore.
2. Create an **Institution** in the Data Mapping Automation module with one of the following **Primary Covered Entities**. See [creating and editing institutions](/v1/docs/creating-and-editing-institutions) for more information:
  - Commercial Entities
  - Digital Service Industry
  - Telecommunications Industry
  - Non-Profit Entities
  - Medical Industry
  - Financial Institutions
  - Educational Instituions
  - Employers

Or any of the following **Secondary Covered Entities**:
  - Any Commercial entity
  - Any Entity in the Digital Services Industry
  - Any Entity in the Telecommunications Industry
  - Any Non-profit Organizations
  - Any Entity within the Medical Industry
  - Any Financial Institution
  - Any Private Educational Institute
  - Any Employer
3. Perform a discovery scan for your Databricks instance.
4. If the data elements discovered during the data scan have a Locality of Singapore. Securiti will infer the data subject residency from these data elements, and that in this case is Singapore.

When this policy is evaluated, and all the above-mentioned triggers match, the policy will generate alerts and recommendations.

## Demo : Managing Cross Border Data Transfer Policies for SharePoint

**Microsoft 365 SharePoint Online** supports Cross Border Transfer Policies based on both **Data Location** (where data is stored), and **Data Access Location**, where data is being accessed from. These policies use metadata gathered from Activity Analysis, making it mandatory to configure Activity Analysis for SharePoint before you can receive alerts for cross-border data transfer violations. This demo walks through activating a Cross Border Transfer Policy for SharePoint, reviewing the open findings generated, and drilling into the evidence captured for each detected violation

It is a set of definitions related to the movement and access of data across national borders to comply with privacy regulations. It aims to mitigate the risk of unauthorized access, providing a framework for managing and remediating such risks through governance workflows.
