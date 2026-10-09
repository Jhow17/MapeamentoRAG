---
title: "Creating a test"
slug: "creating-a-test"
updated: 2025-12-01T08:01:47Z
published: 2025-12-01T08:01:47Z
canonical: "helpcenter.securiti.ai/creating-a-test"
area: dspm
modulo: compliance
tipo: guia
data_captura: 2026-10-06
---

# Creating a test

> [!NOTE]
> Note
> 
> Only users with [read permissions](/v1/docs/compliance-rbac-permissions-and-roles) for tests can be associated with those tests

To create a specifically tailored test for automated evaluation of controls, you must have metadata information stored in UDG.

To create a test:

1. In Securiti, open **Compliance**, and at the upper right corner of the Compliance dashboard, click **Tests**.
2. On the **Tests** list, in the upper right corner, click **Create**.
3. In the **General Information** section, enter:
  - Test name
  - Test description
  - Tags
  - Risk factor

You have to set a risk factor for the test to define the Impact of the Risk associated with the tests. The available risk types are as follows:
    - Insecure application
    - Disaster recovery
    - Vulnerability
    - Unprotected data
    - Insure AI model
    - External exposure
    - Lineage
    - Privilege escalation
  - Owner
4. Under the **Evaluation Logic** section, choose the test evaluation method.

In the case of automated evaluation, choose **Graph Expression** and click **Add Query** to create a query expression to evaluate the test.

> [!NOTE]
> **Important**
> 
> Before creating a graph expression for automated evaluation of the test, make sure the Graph Explorer is enabled on your tenant. Otherwise, reach out to [support@securiti.ai](mailto:support@securiti.ai).

For manual evaluation, choose **Attestation** and choose **Frequency** from the menu.

> [!NOTE]
> **Note**
> 
> Frequency signifies the test's expiration timeframe, either in terms of months, quarters, or annual, indicating when the test will no longer be valid.
  - Click **+** to select a node. You can also use the search bar to search for the node to add to the expression.

![Query_building_in_tests.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5b41a0c0-938d-e5fe-b2f0-fd9958cbee85.png)

> [!NOTE]
> **Note**
> 
> You can select any node supported in the Graph Explorer (referred to as an entity in the Compliance module), to create and evaluate a test.
> 
> This capability enables you to derive greater value and deeper out-of-the-box (OOTB) insights into your data landscape. It supports building and managing a robust system of graph-based rules to identify, report, manage, and lifecycle risky insights effectively. The OOTB library of graph-based rules highlights sensitive or risky combinations of assets, configurations, associated data, and access patterns.
> 
> Additionally, you can create compliance tests on raw data within files, broadening the range of supported data types for deeper and more comprehensive analyses. However, this functionality is currently limited to file extensions. Other extensions, such as column extensions and workflow extensions, are not supported at this time.
> 
> With the introduction of file extension support, you can now:
> 
> - Analyze compliance risks directly within raw file data, providing a more holistic view of your data landscape.
> - Create, manage, and monitor queries seamlessly in Graph Explorer for both structured and unstructured data, ensuring consistent and robust risk mitigation.

> [!NOTE]
> **Important**
> 
> Compliance nodes cannot be selected for creating tests.
  - Further, click **Options** (three dots) on the right side of the node you want to add properties for and click **Add Property**.

![test_graph_explorer_-_add_property.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b5bef402-2103-c871-643c-ea98ca92b53a.png)
  - Select the property of the node that you want to add and further choose the operator to select what criteria to match from the menu.
  - You can also add relationships to expand the expression and view all entities or nodes having direct relationships with your node. Click **Options** (three dots) on the right side of the node or node's property and click **Add Relationship**.

![create_test_graph_explorer_-_add_relationship.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c6c32e32-b7aa-d8fe-84aa-792a50289765.png)
  - You can select multiple nodes using the same procedure. Once done, click **Apply.**

For more information on graph expression, see [Filtering entities and their attributes](/v1/docs/using-graph-explorer)
5. Set the **Severity** of the test on a scale ranging from Very Low to Very High. Each test's severity reflects the level of risk it assesses.
6. Further, you can select **Controls** associated with the test for evaluation purposes.
7. Click **Create Test**.

### View test details

1. On the **Tests** list, locate the card for the test you want to view details of.
2. At the right end of the card, choose **Options** (three dots) **> Graph View of Test**.
  - The first section offers a graphical representation of how the test integrates with numerous controls, sub-categories, categories, frameworks, projects, and data systems.

![graph_view_expanded.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2fb155f5-bd46-63a7-6751-19f6cd9c3d8d.png)
  - Click on any component in the graph to see further information about it. For instance, clicking on Category takes you to the list of categories along with the count to which the test belongs.

![graph_view_detail.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-26892890-2eac-ddf8-4e08-1cb2bd991018.png)
