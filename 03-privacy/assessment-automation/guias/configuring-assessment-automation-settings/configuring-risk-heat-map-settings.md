---
title: "Configuring risk heat map settings"
slug: "configuring-risk-heat-map-settings"
updated: 2025-12-08T12:43:00Z
published: 2025-12-08T12:43:00Z
canonical: "helpcenter.securiti.ai/configuring-risk-heat-map-settings"
deprecated: true
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Configuring risk heat map settings

> **Deprecated.** This article is deprecated. See [risk settings in V2](https://helpcenter.securiti.ai/docs/configuring-settings-in-risk-v2).

### Prerequisites

You must have one or more of the following roles and have access to the assessment organization to configure risk heat map settings.

- DPO
- Operator
- Super admin
- Module owner
- Assessment owner or question owner

See the user roles and permissions [topic](/v1/docs/understanding-user-roles-and-permissions-before-conducting-assessments) for more information.

To configure the labels for the Likelihood and Severity axes of the risk heat map and the risk levels plotted on them:

1. In Securiti Dashboard View, select **Assessment Automation > Settings > Risk Settings**.
2. Click **Edit** (pencil icon) to rename the axis and level labels, as shown below.

![risk-heat-map-settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c666652f-d508-e22e-be95-6ae8dc4802b5.png)
3. Near the upper right corner of the page, click **Save**.

Furthermore, you can configure the Risk heat map's size and severity by choosing different matrices and adding categories.

To set the Heat Map matrix:

1. In Securiti Dashboard View, select **Assessment Automation > Settings > Risk Settings**.
2. On the Risk Matrix, choose either a *3x3*, *4x4* , or *5x5* matrix from the Heat Map menu to suit, as shown below.

![Risk_Matrices.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-400601ff-42a5-62a7-212e-8210d474045c.png)

Click **Save**

To add (or delete) categories to the Severity Category:

1. In Securiti Dashboard View, select **Assessment Automation > Settings > Risk Settings**.
2. Near the bottom of the page, in the Severity Category field, enter the category name, for example, "Human damage", "Business continuity", "Product Market Action", etc., and press the enter (Return) key.

When you want to remove a category, click the **x** icon next to the category.

![screenshot-qa_securiti_xyz-2023_08_23-11_19_38.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a9a43dbe-e3ac-8eca-3cb8-86d26d9419a7.png)
3. Click **Save** in the top right.

To configure the template for the risk assessment, select User Defined from the Set Risk menu. You define the risk after publishing the assessment based on your response.

See [Creating assessment questions with conditional logic](/v1/docs/creating-assessment-questions-with-conditional-logic) for more information.
