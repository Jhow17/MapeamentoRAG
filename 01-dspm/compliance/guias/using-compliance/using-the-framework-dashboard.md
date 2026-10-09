---
title: "Using the Framework dashboard"
slug: "using-the-framework-dashboard"
status: "update"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/using-the-framework-dashboard"
area: dspm
modulo: compliance
tipo: guia
data_captura: 2026-10-06
---

# Using the Framework dashboard

**Scenario**

As a data privacy officer, you need to ensure compliance with evolving standards like GDPR and ISO 27001. Manually tracking controls across systems is inefficient and increases the risk of oversight. With Frameworks, you can access pre-built and custom frameworks, view control-level status, and track real-time test results, streamlining compliance and enabling confident, audit-ready reporting for stakeholders.

The Framework dashboard is a visual representation or summary of your organization's framework status. You can see all system frameworks as well as any custom frameworks your admins have created. All frameworks are broken down into their individual defined controls and every [control](/v1/docs/controls-overview) has one or more [Tests](/v1/docs/rule-center-overview) to measure whether the control is satisfied.

To open the Framework dashboard:

- In Securiti, open **Compliance**, and at the upper right corner of the compliance dashboard, select **Frameworks**.
- Or from the left navigation bar, select **Frameworks > Compliance Frameworks**.

![Overview of Australian Privacy Principles and related compliance frameworks in a management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance frameworks.png)

The framework dashboard includes various widgets, each displaying specific statistics regarding frameworks:

- The **Frameworks** widget shows the combined count of both system and custom frameworks.

Securiti currently supports the following frameworks in the Compliance module:
  - Australian Privacy Principles
  - CCPA/CPRA
  - CDMC
  - Chile's Law No. 21.719
  - Cloud Computing Compliance Controls Catalogue (C5)
  - CN PIPL
  - Colorado AI Act
  - CPS 234
  - EU AI ACT
  - EU DORA
  - GDPR
  - HIPAA
  - India DPDPA
  - Indonesia PDPL
  - ISO 27701
  - ISO 42001
  - ISO/IEC 27001:2013
  - ISO/IEC 27001:2022
  - KSA PDPL
  - Malaysian PDPA
  - NIST AI RMF
  - NIST CSF
  - NIST CSF 2.0
  - NIST 800-53
  - NYDFS Cybersecurity Regulation
  - OSFI Canada Guideline B-13
  - PCI DSS 3.2.1
  - PCI DSS 4.0
  - RIIO-3 Data Best Practice Guidance
  - Singapore Model Artificial Intelligence Governance Framework
  - Singapore PDPA
  - SOC 2 Type 2
  - Securiti’s Data Security Framework
  - UAE PDPL
- The **Controls** widget shows the total number of predefined and custom controls against sub-categories.
- The **Tests** widget shows the total number of predefined and custom tests.

#### Default frameworks

Compliance provides a default framework called Securiti Data Security Framework. This is a proprietary, purpose-built framework designed by Securiti with a strong emphasis on data security. The framework is automatically enabled whenever Compliance is activated in your tenant, ensuring baseline data security controls are in place by default.

#### Cloning compliance frameworks

You can clone both system-defined and custom compliance frameworks directly from the **Compliance Frameworks** page.

When you clone a framework, all associated categories, sub-categories, and controls are duplicated. You can then customize the cloned framework by renaming items, adding or removing categories, sub-categories, and controls.

> [!NOTE]
> **Note**
> 
> Securiti does not support cloning Tests. Instead, the original tests remain linked to both the original and duplicated framework. Any changes you make to a test reflects in both frameworks.

To clone a framework:

1. In the Compliance module, open the **Frameworks** page.
2. Locate the framework you want to duplicate and click the **Options** (three dots) next to the framework > **Duplicate Framework**.

![Overview of Australian Privacy Principles with highlighted duplicate framework option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance frameworks - duplicate.png)
3. On the configuration popup, you can append a postfix to differentiate the cloned framework and choose whether to apply postfix to categories, subcategories, and controls.
4. Once you have made your selections, click **Confirm** to complete the duplication process.

![Duplicating Australian Privacy Principles with a custom postfix and category options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance duplicate framework.png)

#### Viewing instance explorer

For each framework, category and subcategory, you can click the Instance Explorer to view the complete metadata details of the test.

![Overview of Australian Privacy Principles and related compliance frameworks in a management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance frameworks metadata explorer.png)

#### Creating widgets

You can see the **Create Widget** button on the right side of the **Create** button. This option lets you display frameworks-specific widgets on the frameworks dashboard to track metrics, trendlines, and more.

1. Click **Create Widget**.
2. Enter relevant information and save.

For more information, see [Creating widgets into dashboard](/v1/docs/creating-widgets-in-graph-explorer).

The framework is a set of controls which is available to you in order to remediate a risk by applying controls from different frameworks in a risk assessment.

## Related

- [Project overview](/project-overview.md)
