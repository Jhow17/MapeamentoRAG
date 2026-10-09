---
title: "Using Security Posture Management"
slug: "using-security-posture-management"
updated: 2026-04-23T09:05:08Z
published: 2026-04-23T09:05:21Z
canonical: "helpcenter.securiti.ai/using-security-posture-management"
area: dspm
modulo: security-posture-management
tipo: guia
data_captura: 2026-10-06
---

# Using Security Posture Management

**Scenario**

As a Data Security Officer, you must protect sensitive data across both IaaS clouds and SaaS applications. When you manually audit each environment for misconfigurations, you waste time and risk overlooking threats. With Securiti’s posture management, you automatically scan IaaS and SaaS platforms, pinpoint risky settings, and enforce encryption, access controls, and DLP rules. You receive instant alerts and remediate issues swiftly, reducing breach risk and ensuring compliance.

Securiti's Security Posture Management module helps you reduce data breach risks, enhance data security, and improve data privacy and compliance. It scans your Infrastructure as a Service (IaaS) or Software as a Service (SaaS) systems for security vulnerabilities and identifies sensitive data across multiple cloud environments and services, accessing vulnerabilities to security threats and misconfigurations, such as access control, network security, encryption in transit, rest, backup, and many more. It does it all while reducing the cost and complexity of building data controls. Posture management focuses on securing data across multi-cloud environments, including your IaaS clouds and SaaS applications.

> [!NOTE]
> Note
> 
> For Sovereign environments, Security Posture Management is available only for self-hosted data systems supported for these environments.

### Why Security Posture Management

Security Posture Management provides insight and automation that enable security teams to quickly address data security and compliance issues and prevent their recurrence. It offers system-generated security posture policies and rules to control and protect your data, including encryption, access controls, and Data Loss Prevention (DLP). These policies make sure that your data is protected and complies with regulatory standards. Securiti triggers alerts if any misconfiguration or policy or rule violation is found.

This module also facilitates the remediation of security settings for data resources, whether manually or automatically. Security Posture Management not only identifies and automatically remediates security misconfiguration risks but also focuses on detecting exposures of sensitive data across your multi-cloud environment.

It continuously monitors the environment for new data assets and continually audits those assets for potential security risks. It protects enterprise data across multi-cloud environments, gives greater visibility to investigate and remediate cyber threats, meets privacy regulations, and simplifies operational complexity by providing automatic and manual remediation.

### Benefits of Security Posture Management

Our posture management solution can provide:

- Stronger security and a reduced risk of data breaches
- Lower attack possibility through effective data discovery
- Greater operational efficiency and cost savings
- Data loss prevention (DLP)
- Establish security policies for data protection and compliance
- Implement security posture rules

### Difference between CSPM and SSPM

**CSPM**

Cloud Security Posture Management (CSPM) focuses on cloud data security, identifying and managing risk and compliance issues in your multi-cloud environments through asset discovery, configuration and access management, detection, and response.

**SSPM**

SaaS Security Posture Management (SSPM) focuses on discovering sensitive data within your cloud infrastructure services and SaaS applications. This prioritizes the discovery of sensitive data to identify potential security and compliance misconfigurations.

### Using the Security Posture Dashboard

You can use the security posture dashboard to view posture policies and rules, as well as view alerts on the posture findings page.

#### Searching for a security posture policy

You can use the search bar to find a specific policy.

![Overview of cloud security policies with a search bar for policy names.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/search-for-a-policy.png)

#### Filtering security posture policy details

You can use the following filters to limit the dashboard view or find a desired policy using one of the **Equals**, **Not equals**, or **Is one of** operators.

> [!NOTE]
> **Note**
> 
> Applying these filters also updates the tile counts for **Total** and **Active Policies**.

Properties supported for these filters are as follows:

- Asset Type
- Cloud Provider
- Date Created
- Date Modified
- Owner
- Policy ID etc

![Filter options for asset types in a policy management interface with various selections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dashboard-filters.png)

#### Viewing security posture policy

From the right-most side of any policy entry on this dashboard, click the ellipsis menu to view the details of a security posture policy. Alternatively, click directly on the specific policy to open its details.

![Overview of security posture policies with active policies and details displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/view-option.png)

#### Viewing security posture metadata

From the right-most side of any policy entry on this dashboard, click the show metadata icon to open the posture policy details.

![Overview of security posture policies with active and total policy counts displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/posture-metadata.png)

Choose **Explore** to view the posture policy's relationships with other nodes such as posture rules, remediation, and so on. To view further details, click a node displayed in the relationship.

## Related

- [Getting Started with Security Posture Management](/getting-started-with-security-posture-management.md)
