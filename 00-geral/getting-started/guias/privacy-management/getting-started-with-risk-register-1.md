---
title: "Getting Started with Risk Management"
slug: "getting-started-with-risk-register-1"
updated: 2026-09-25T08:56:52Z
published: 2026-09-25T08:56:52Z
canonical: "helpcenter.securiti.ai/getting-started-with-risk-register-1"
area: geral
modulo: getting-started
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Risk Management

**Scenario**

As a Data Privacy Officer, you need to report on privacy risks and prepare for upcoming audits. Manually compiling risk data from multiple sources is time-consuming and error-prone. By exporting risk data from the platform, your team quickly generates internal reports with consistent metrics. This streamlines audit preparation and gives stakeholders a clear view of your organization’s risk posture. For example, after detailing the risks, users link them to relevant objects such as assessments and vendors, and finally, a remediation workflow is performed, allowing exported risk data to show the residual risk levels and scores accordingly.

## Getting Started flow

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-CR.svg)

### Step 1 - *Configure risk settings

| **Configure Risk V2 settings** Choose between linear or matrix risk, set aggregation method, and more. [Learn more](/latest/docs/configuring-settings-in-risk-v2) See what changes to expect when you upgrade from Risk V1 to Risk V2. [Learn more](/latest/docs/transitioning-from-risk-v1-to-risk-v2#data-migration-from-risk-v1-to-risk-v2) **Indicates features subject to release at a later date.* | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-20 at 11.33.56 AM.png) ![Overview of a risk register displaying various risk statuses and descriptions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-03 at 11.35.39 AM.png) |
| --- | --- |

### Step 2 - Add risk and configure risk details

| ![Overview of a risk register displaying various risk statuses and descriptions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-03 at 11.35.39 AM.png) ![Risk management overview showing inherent and residual risk levels with status updates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-03 at 11.39.30 AM.png) ![User interface displaying linked objects and processes for risk management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-03 at 11.40.24 AM.png) | **Use risk register to create risks** Use the Securiti Risk Register to create new or view existing risks. Also, you can import and export risk from the register. Use “Add Risk” to configure inherent risk, owner, reviewer, tags, etc. [Learn more](/latest/docs/create-risks-using-the-risk-register#create-risk) **Link objects** After specifying risk details, proceed to link the desired object(s). Object types include Assessments, Assets, Processes, Vendors, and Institutions. [Learn more](/latest/docs/create-risks-using-the-risk-register#add-risk-to-object) |
| --- | --- |

### Step 3 - Perform remediation workflow

| **Review proposed remediation or requested exception** If you added a risk reviewer, the reviewer can either approve or send back the risk. After the risk is approved or exception granted, Securiti shows the latest values for residual risk levels and scores, accordingly. “Risk Activities” show logs for all actions related to that risk. [Learn more](/latest/docs/navigating-the-risk-details-page#pending-actions) **Remediation based on Control implementation status** With a control in place, manual remediation is restricted. Use the effectiveness configured under Risk Settings to mitigate or reduce risk. Securiti lets you set Control status based on Linear or Risk Matrix modals whereby the risk is either reduced by existing risk level(s) or severity and likelihood levels. [Learn more](/latest/docs/implementing-control) | ![Risk management details showing inherent and residual risk levels with proposed actions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-03 at 11.40.52 AM.png) |
| --- | --- |

### Risk Management API Documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The Risk Management API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/risk-register/apidocs/index.html#section/Getting-Started) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the postman collection** We also provide Postman collection for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that let you to quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/risk-register/apidocs/index.html#section/Getting-Started/Import-Postman-Collection) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-27 at 4.18.27 PM(1).png) |
