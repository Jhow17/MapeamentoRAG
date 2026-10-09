---
title: "Getting Started with Compliance"
slug: "getting-started-with-compliance"
updated: 2026-01-08T07:38:14Z
published: 2026-01-08T07:38:14Z
canonical: "helpcenter.securiti.ai/getting-started-with-compliance"
area: dspm
modulo: compliance
tipo: guia
data_captura: 2026-10-06
---

# Getting Started with Compliance

Amid rising regulatory demands and data complexity, Securiti’s Compliance module streamlines data security and compliance with global standards like GDPR, ISO, and HIPAA. It enables organizations to implement controls, mitigate risks, and build trust using preloaded or customizable frameworks.

The module is your all-in-one solution for managing data security and ensuring compliance with regional and global standards. In a landscape of rapid data growth, it is vital to adhere to data policies for safe and responsible data usage.

The solution assesses risks by calculating scores through graph queries identifying vulnerabilities. Rising scores signal escalating issues requiring remediation while declining scores indicate improved security and compliance.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Using%20Complaince-Design.drawio(1).svg)

> [!NOTE]
> **Note**
> 
> This module enables you to unlock greater value and gain deeper, out-of-the-box (OOTB) insights into your data landscape. It lets you build and manage a robust system of graph-based rules as toxic combinations, designed to identify, report, manage, and monitor risky insights throughout their lifecycle. These toxic combinations are new graph-based rules aimed at identifying risks such as data exposure, access privilege escalation, unprotected data, and compliance vulnerabilities.
> 
> 
> 
> You can now select any node or entity supported in the Graph Explorer to build queries for test evaluation and view the relevant findings. Importantly, for this type of test evaluation, you don’t need to rely on SPM findings or go through the hassle of creating frameworks and projects. Simply create the test directly using the Graph Explorer nodes and get the relevant results quickly and easily.

#### Step 1 - SPM findings

The Compliance module relies on insights derived from the Security Posture Management (SPM) findings. To use this module effectively, it’s essential to have existing SPM data, as it identifies and addresses violations of established security rules and policies that may lead to data vulnerabilities or non-compliance.

By integrating SPM findings, the Compliance module lets you proactively manage and resolve security issues, ensuring your organization not only meets regulatory requirements but also strengthens its overall security posture.

> [!NOTE]
> **Note**
> 
> For custom frameworks, including SPM findings is optional.

[Learn more](/v1/docs/using-security-posture-management).

#### Step 2 - Choose the framework

You have the flexibility to either create your own framework (custom framework) or use the predefined ones. If you opt for the custom framework, you must develop your own tests, controls, and frameworks for compliance assessment. With the predefined framework, creating tests, controls, and frameworks is optional—you can start a project using the available out-of-the-box tests and controls.

> [!NOTE]
> **Note**
> 
> Steps 3 to 9 are mandatory if you choose to create your custom framework. If you are using a predefined framework, skip directly to step 10.

![Framework_-_Toxic_combinations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-104c009e-0acd-5eb0-a7b1-1da1aeecf7a2.png)

#### Step 3 - Create a framework

The next step is to create your framework. Frameworks serve as the top-level grouping for the controls you are implementing, categorizing them based on relevant regulations, standards, or best practices.

Examples of frameworks include regulations like **GDPR**, standards like **ISO 31000**, or best practices such as the **CDMC**. The primary goal of a framework is to achieve compliance and mitigate risk.

For instance, the **CDMC** framework from the **EDM Council** outlines 14 key controls to help organizations effectively migrate, manage, and protect data in cloud or hybrid cloud ecosystems. Implementing these controls helps reduce risks associated with data handling.

By establishing a robust framework, you can ensure that your organization is well-equipped to meet compliance requirements and manage associated risks effectively.

[Learn more](/v1/docs/creating-a-new-framework).

#### Step 4 - Create a category

After defining the custom framework, the next is to add a custom category tailored to your organization’s needs. A category is a collection of sub-categories that contain controls used to verify policies and remediations to ensure compliance across various data systems.Note: You can also add a predefined category in the custom framework.

**Example**

As an example, **Data Cataloging and Classification** can be a category within the **CDMC framework**.

[Learn more](/v1/docs/managing-categories).

#### Step 5 - Create a sub-category

Create a sub-category within your compliance framework. A sub-category is a collection of controls designed to verify policies and implement remediations, ensuring compliance across various data systems.

> [!NOTE]
> **Note**
> 
> You can also add a predefined sub-category in the custom framework.

By organizing controls into sub-categories, you can enhance the specificity and effectiveness of your compliance efforts, making it easier to manage and assess the relevant requirements.

**Example**

Under the category **Data Cataloging and Classification** within the CDMC framework, the sub-category is **Data Classification** which focuses on the processes and controls used to classify data based on sensitivity and compliance requirements.

[Learn more](/v1/docs/managing-sub-categories).

#### Step 6 - Create a control

After creating the sub-category, the next step is to define your controls. A control articulates specific intentions and expectations derived from regulations, standards, or best practices.

> [!NOTE]
> **Note**
> 
> You can also use predefined controls in the custom framework.

![Controls_-_After_toxic_combinations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fb848c4c-8a04-9aad-e36e-6c167a13a670.png)

Each control specifies requirements that must be met to ensure compliance. For example, controls may include statements like **Document Purpose** or **Data lineage is documented for all processing activities involving sensitive data**. Additionally, controls may outline specific requirements such as the **encryption of sensitive data**.

[Learn more](/v1/docs/controls-overview).

#### Step 7 - Create a test

After successfully creating a control, you need to create your own tests. These tests act as detailed plans that outline the steps necessary to ensure compliance with the requirements specified in your controls.

> [!NOTE]
> **Note**
> 
> You can also use predefined tests in the custom frameworks.

![Rule_center_dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cc6b8954-02d2-5432-7ef2-820a9e7b59d6.png)

Each test defines the specific actions needed to meet the intentions and expectations outlined in the controls. You have two options for creating your tests:

- Automated tests: These are executed based on expressions against the Unified Data Graph (UDG).

> [!NOTE]
> **Note**
> 
> You can select any node in the Graph Explorer (an entity in the Compliance module) to create and evaluate tests, providing deeper insights into your data landscape.
- Manual/Attestation tests: These require individuals to provide answers and can evaluate one or more attributes of an object.

By developing these tests, you can effectively assess compliance within your custom framework and ensure that all requirements are met.

**Example**

**Test: Access control compliance test**

Verify that all users have unique usernames, strong passwords, and appropriate role-based access, while ensuring regular audits and monitoring of access logs for compliance with the Access Control Policy.

[Learn more](/v1/docs/creating-a-test).

#### Step 8 - Link test with control

Once you have created your tests and controls, the next step is to link or group the related tests under the appropriate control. This ensures that each control is supported by the necessary assessments to verify compliance.

**Example**

As a generic example, if your control states, “A documented business continuity and disaster recovery plan is in place, tested, and approved on an annual basis,” you would link all tests related to verifying the business continuity plan. This might include tests that assess the documentation process, testing frequency, and approval status.

#### Step 9 - Link the sub-category with the control

After you have created your sub-category, the next crucial step is to link it to the relevant control. This connection enhances the structure and clarity of your compliance framework. It ensures that each control is supported by the specific sub-categories designed to fulfill its requirements.

#### Step 10 - Create a project

Now that you have established your framework and defined the necessary tests, controls, categories, and sub-categories, it is time to create a project.

A project serves as the practical application of your initiatives, helping you implement the directives necessary to achieve your compliance goals. You have the option to create a manual project or use one of the OOB projects, which automatically generates compliance assessments upon connecting your IaaS account. Creating a project is essential for implementing initiatives that achieve compliance goals through frameworks.

![Projects_-_Toxic_Combinations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-985b7a21-f305-ebbf-2c90-0e33e6b05fc2.png)

[Learn more](/v1/docs/project-overview).

#### Step 11 - Test runs to evaluate the control

In this step, tests are conducted to evaluate the effectiveness of your controls. There are two primary methods for running these evaluations:

| **Automated evaluation** This approach involves creating various expressions that are executed against the Unified Data Graph (UDG). Each expression serves as a criterion to determine whether a data asset aligns with a specified control or meets certain compliance requirements. Automated evaluations enable efficient and consistent testing, ensuring that controls are assessed accurately against defined standards. | ![Automated_testing.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e9eeda4f-7c5c-7f0f-9aaf-7a858020140b.png) |
| --- | --- |
| **Attestation or manual evaluation** Attestation involves manual assessments where you provide answers to evaluate one or more attributes of an object. This method requires examining specific parts of the system or process to determine compliance with the control’s rules. Manual assessments may be necessary when control requirements cannot be easily automated or when more nuanced evaluations are required. | ![attestation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a3bcc18c-01bb-d00d-8923-350928d51cbd.png) |

[Learn more](/v1/docs/evaluating-tests-in-a-project).

#### Step 12 - View the risk score

After running the tests, you can view their risk scores. The risk score provides a comprehensive measure of your organization's risk by quantifying the severity and volume of findings. It serves as a key indicator of the organization’s overall risk posture, highlighting potential areas of concern and identifying toxic combinations of elements that could increase risk. The score calculation incorporates both the number and the weighted severity of findings, producing a value scaled between 0 and 100.

If the score is higher than the trend, it signals that data risk is increasing, indicating worsening vulnerabilities that require immediate attention.If the score is lower than the trend, it demonstrates that data risk is decreasing, reflecting improvements in the organization’s risk posture.

This makes the risk score a dynamic and actionable tool, providing a clear view of the organization’s current and evolving risk environment.

#### Step 13 - View the findings

The test findings dashboard lets you view the findings against the tests and address the violations of the established rules, potentially leading to data vulnerabilities or non-compliance. You can explore, identify, and resolve compliance challenges and roadblocks. The dashboard comprises graphs and widgets offering real-time compliance status across various international frameworks.

[Learn more](/v1/docs/test-findings).

![Test_Findings_-_Risk_Score.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7f66f496-f71b-8b26-baf3-3e3ef289b4a7.png)
