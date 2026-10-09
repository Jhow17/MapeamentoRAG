---
title: "Getting Started with Security Posture Management"
slug: "getting-started-with-security-posture-management-1"
updated: 2026-05-04T10:47:40Z
published: 2026-05-04T10:47:40Z
canonical: "helpcenter.securiti.ai/getting-started-with-security-posture-management-1"
area: geral
modulo: getting-started
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Security Posture Management

Security Posture Management lets you identify the misconfigurations and vulnerabilities across your local and multi-cloud environment. You gain visibility into the configuration state of your data across public cloud systems and SaaS applications, helping ensure compliance with regulatory standards and best practices. Securiti applies built-in industry-standard posture rules to detect misconfigurations and take action to remediate risks effectively.

With intelligent automation, this tool helps you remediate (manual or automatic) misconfigurations such as access control, network security, encryption in transit, rest, backup, and many more to comply with necessary data privacy, security, compliance, and governance operations to ensure your data remains safe and secure.

Regular testing and auditing helps you maintain effective controls and quickly identify and implement changes to enhance your security posture.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[GS]Security Posture Management.drawio(2).svg)

### Step 1a - Configure posture scan for IaaS Cloud/SaaS Data Systems

Security Posture Management module detects security misconfigurations and performs auto-remediation for selective cloud systems such as AWS, Azure, or GCP, as well as SaaS data systems such as Workday, SharePoint online, and so on.

#### Detect Posture Misconfigurations and Auto-Remediation (IaaS Clouds)

You can enable the following options for new and existing IaaS clouds:

| **Detect Security Posture Misconfigurations** When you are about to onboard your IaaS cloud account, choose the Detect Security Posture Misconfigurations checkbox to detect misconfigurations for your data (e.g. access controls, network settings, encryption protocols). [Learn more](/latest/docs/data-security-posture-management-solution#security-posture-management) | ![initiatePostureScanIaaS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-597c0809-eb18-60f9-a221-5106f3f96601.png) |
| --- | --- |
| **Activate Security Posture auto-remediation** Mark the **Activate Security Posture auto-remediation** checkbox to detect misconfigurations for your data (e.g. access controls, network settings, encryption protocols). [Learn more](/latest/docs/data-security-posture-management-solution#automatic-remediation) | ![autoRemediationIaaS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-becc9ce2-1eef-dd6b-e69b-8bded4394603.png) |

#### Initiate a Posture Scan (SaaS Data Systems)

For your SaaS data systems such as Microsoft 365 SharePoint Online, you can initiate the posture scan from your data systems page.

| ![ConnectorsPostureScan.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66d55bb9-fbb6-e124-29a7-c88d1d1b33b0.png) | **Detect Security Posture Misconfigurations** To enable posture scan for your SaaS Data Systems, such as Microsoft 365 SharePoint Online or Workday, first, you must configure and activate the relevant connectors, then initiate posture scan by clicking **Run a Scan** from the **Permissions** tab on your Data Systems page. If you already have a configured connector, initiate **Run a Scan**. [Learn more](/latest/docs/configuring-connectors-for-monitored-data-systems) |
| --- | --- |

### Step 1b - View security posture policies

Securiti offers system-generated security posture policies for your SaaS and IaaS cloud systems based on posture rules which once violated, security alerts are generated on the Posture Findings page.

### Step 2 - Set Periodic Schedules for Posture Scans

You can also set schedules for periodic posture scans for your IaaS Cloud systems according to your requirements.

| ![IaaSPostureScanSchedule.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ddec1d75-5014-00d5-73bd-a1ab64baa82d.png) | **Periodic Schedules for your IaaS Clouds** You can set schedules for periodic posture scans for your IaaS Cloud systems according to your requirements. [Learn more](/latest/docs/getting-started-with-iaas-cloud#step-4-set-the-scan-frequency) |
| --- | --- |
| ![ConnectorsPostureScan.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66d55bb9-fbb6-e124-29a7-c88d1d1b33b0.png) | **Periodic Schedules for your SaaS data systems** You can set schedules for periodic posture scans for your SaaS data systems according to your requirements. [Learn more](/latest/docs/configuring-connectors-for-monitored-data-systems) |

### Step 3 - View security posture rules

Securiti offers system-generated security posture rules for your SaaS and IaaS cloud systems which once violated, security alerts are generated on the Posture Findings page. You can then perform the automatic or manual remediation of misconfigurations or vulnerabilities found.

### Step 4 - View Security Posture Findings

You can view the security posture findings to address the violations of the established security rules and policies, potentially leading to data vulnerabilities or non-compliance.

For security posture management, you have 3 options:

- Detecting posture misconfigurations for your SaaS Data Systems > View findings > Performing manual remediation
- Detecting posture misconfigurations for your IaaS Cloud accounts > View findings > Performing automatic or manual remediation

| ![gs-posture-findings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-06f0654d-1ffd-7a6c-287f-1bb66933c31e.png) | **Security Posture Findings** View security posture findings and severity on the Posture Findings page which includes Open, Fixed, and Suppressed Findings. [Learn more](/latest/docs/security-posture-policies-and-findings) |
| --- | --- |
| ![postureEvidence.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac9eaf42-d01d-9561-becd-0fa342239a9b.png) | **View Evidence for misconfigurations** You can view the evidence for misconfiguration in Securiti to get a deeper understanding. [Learn more](https://helpcenter.securiti.ai/docs/security-posture-policies-and-findings#viewing-the-evidence-relationships-manual-remediation-steps-and-running-autoremediation) |
| ![postureRelations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fd263a0d-9ebd-cc31-804b-3db238dc6e00.png) | **View Relationships in Graph Explorer** You can view the relationships of posture policy with different entities such as regulations, standards, and findings. [Learn more](https://helpcenter.securiti.ai/docs/security-posture-policies-and-findings#viewing-the-evidence-relationships-manual-remediation-steps-and-running-autoremediation) |
| ![remediation_steps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-44001c2f-25ec-694c-1da3-55827f916ac7.png) | **View remediation steps** You can view the manual remediation steps to perform at your data system console. [Learn more](https://helpcenter.securiti.ai/docs/security-posture-policies-and-findings#viewing-the-evidence-relationships-manual-remediation-steps-and-running-autoremediation) |
| ![SuppressPostureFindings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0df2ecdf-cbd9-fdc9-2004-96f5176d32fc.png) | **Suppress Findings** You can also suppress or unsuppress the findings. > [!NOTE] > **Note** > > The time taken to suppress or unsuppress varies depending on the files selected. > > You cannot unsuppress an Open finding and you cannot suppress or unsuppress a Fixed finding. [Learn more](https://helpcenter.securiti.ai/docs/security-posture-policies-and-findings#suppressing-and-unsuppressing-security-posture-findings) |
| ![exportPostureFindings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6ef42831-625f-6bb1-e0f6-538336e0eea2.png) | **Export Posture Findings** You can export the security posture findings to a CSV file that you can share with your customers and stakeholders. [Learn more](https://helpcenter.securiti.ai/docs/security-posture-policies-and-findings#exporting-posture-findings-to-a-csv-file) |

#### Remediate security posture misconfigurations

The following are the actions you can take to automatically or manually remediate your security posture misconfigurations.

| Automatic remediation of misconfigurations | Automatic Remediation refers to the process where SPM can automatically apply fixes to identified vulnerabilities or misconfigurations in your IaaS clouds. This helps reduce the time and effort needed to address security risks, allowing organizations to maintain a stronger security posture with less manual intervention. [Learn more](/latest/docs/remediating-security-misconfigurations) |
| --- | --- |
| Manual remediation of misconfigurations | Perform the following steps for manual remediation: 1. Review the posture misconfigurations, such as sensitive data identified. 2. Go to your IaaS or SaaS platform, and analyze the findings to find the summary of misconfigurations. 3. Apply the remediation, such as modifying access controls, updating network security, enabling encryption, or other actions, and so on. 4. Verify the misconfigurations by running the posture scan again. [Learn more](/latest/docs/remediating-security-misconfigurations) |

### Security Posture Management Module Release Notes

To view Security Posture Management Release Notes, see [Release Notes](/latest/docs/security-posture-management-release-notes).

### Security Posture Management Module API Documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/security-posture-management/apidocs/index.html) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the Postman collection** We also provide a Postman collection for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that let you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/security-posture-management/apidocs/index.html) | ![dspmPostmanCollection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e9b1fb23-a771-d19c-2345-5a366af331cb.png) |

## Related

- [Using Security Posture Management](/using-security-posture-management.md)
- [Using Security Posture Policies dashboard](/using-security-posture-policies-dashboard.md)
- [Remediating security misconfigurations](/remediating-security-misconfigurations.md)
- [Supported cloud natives services for posture policy rules](/supported-cloud-native-services-for-posture-policy-rules.md)
