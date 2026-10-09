---
title: "Remediating security misconfigurations"
slug: "remediating-security-misconfigurations"
updated: 2026-04-20T07:48:27Z
published: 2026-04-20T07:48:27Z
canonical: "helpcenter.securiti.ai/remediating-security-misconfigurations"
area: dspm
modulo: security-posture-management
tipo: guia
data_captura: 2026-10-06
---

# Remediating security misconfigurations

**Scenario**

As a Data Security Officer, you need to fix misconfigurations before they create security gaps. Manually investigating each finding, logging into consoles, and adjusting settings consumes hours and invites errors. With Securiti’s automated remediation, you apply predefined fixes instantly and confirm resolutions in one place. You accelerate corrective actions, minimize manual effort, and maintain a robust security stance.

### Remediating misconfigurations manually

To manually remediate a misconfiguration found during a security posture scan, you would typically follow a process that involves investigating the identified issue, understanding the root cause, and applying the necessary corrections to your cloud configuration or data handling practices. While the specific steps can vary depending on the nature of the misconfiguration and the cloud platform or service in question, a general approach might include:

- **Reviewing the Posture Findings**: Start by examining the detailed findings, which would include information about the misconfiguration, such as its nature, the affected resources, and the potential risks associated with it.
- **Accessing the Affected Resource**: Log into your cloud service provider's management console or use CLI tools to access the resource identified in the findings.
- **Analyzing the Configuration**: Compare the current configuration of the affected resource against best practices or the recommended settings provided by DSPM or your cloud service provider. Identify the discrepancies that led to the misconfiguration.
- **Applying the Remediation**: Make the necessary adjustments to the resource's configuration to address the identified misconfiguration. This could involve modifying access controls, updating network security settings, enabling encryption, or other corrective actions.
- **Verification**: After applying the changes, verify that the misconfiguration has been successfully remediated. This might involve re-running the DSPM scan to ensure that the issue no longer appears in the posture findings.
- **Documenting the Remediation**: Keep records of the misconfiguration and the steps taken to remediate it. This documentation can be useful for compliance purposes and for improving your Security Posture Management processes.

> [!NOTE]
> **Note**
> 
> It's important to address misconfigurations promptly to mitigate potential security risks and ensure compliance with data protection regulations.

### Remediating misconfigurations automatically

Securiti offers automatic remediation capabilities to address security misconfiguration risks without requiring manual intervention. This involves the system applying predefined solutions or corrective measures automatically to fix a security issue. The concept of "Automatically Remediate" refers to this process, where Securiti can automatically apply fixes to identified vulnerabilities or misconfigurations in the cloud environment, ensuring that the security posture is enhanced promptly and efficiently.

For instance, when policy findings or violations are detected, Securiti can automatically remediate specific findings such as, blocking public access on S3 buckets, enabling encryption at rest, or enforcing automatic backups for Redshift clusters that contain sensitive data. This automatic remediation helps reduce the time and effort needed to address security risks, allowing organizations to maintain a stronger security posture with less manual oversight.

> [!NOTE]
> Note
> 
> Auto-remediation works only if the configuration is enabled for the cloud environment during onboarding. It can also be reconfigured by editing the instance after creation.

For example, to view what AWS specific findings are auto-remediated by Securiti:

- Open the main menu. Navigate to **Policies > Security Posture > Rule Center**.
- In the **Cloud Security Posture Rules** view, set the following filters:
  - **Auto Remediation** as **Yes**.
  - **Cloud Provider** as **AWS**.
- The findings generated against all these rules are auto-remediated by the Securiti platform, provided that the auto-remediation configuration is enabled for the AWS IaaS cloud during onboarding.

![Overview of AWS security rules with active rules and compliance standards displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/1(2).png)
- You can also view the findings in your AWS cloud that were auto-remediated by the Securiti platform, as a result of running the posture scans. To view these findings:
  - Open the main menu. Navigate to **Findings > Security Posture**.
  - In the **Security Posture Findings** view, click on the **+** icon to add a filter query and set the following filters:
    - **Cloud Provider** as **AWS**.

![Filter options for cloud provider selection, highlighting AWS among other choices.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/2(1).png)
    - **Auto Remediation** as **Yes**.

![Filter options for security findings, highlighting auto remediation settings in a cloud provider interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/3(1).png)

Select **Apply**. The auto-remediated findings appear on the screen as they are processed. Alternatively, you can also review the remediation activity by viewing the relevant security posture policy and opening the **Logs** tab.

## Related

- [Getting Started with Security Posture Management](/getting-started-with-security-posture-management.md)
- [Using Security Posture Management](/using-security-posture-management.md)
