---
title: "Viewing DSR form details"
slug: "viewing-dsr-form-details"
updated: 2025-10-30T19:09:19Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/viewing-dsr-form-details"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Viewing DSR form details

You can view DSR form details in the metadata card. The card shows the form's key details such as the owner, regulation, personal identifiers, and associated data systems.

1. From the DSR Form Dashboard, choose the form row. At the right side of the row click **View Metadata**.

![Accessing metdata card from forms dashboard.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-20 at 1.22.15 PM.png)

From the metadata card, you can view the list of data system instances associated with the DSR form by clicking the linked number.

![Dashboard displaying DSR forms, their statuses, and associated regulations for management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-20 at 1.25.25 PM.png)

The count varies depending on how the form is configured:
  - If the form has a rule configured and a task template associated, the count reflects the data system instances connected to that task template.
  - If data system instances are configured directly in the DSR form under the automation settings, the count reflects those directly added instances.
  - If no automation rule or task template is configured, the count includes all data system instances where the **Include this instance in the DSR workflow** checkbox is enabled.

This opens a list of connected systems and shows their automation status, helping you track connection readiness. You can also click a link against each instance to access instance configurations.

![Dashboard displaying associated data systems with connection statuses and form details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-10-20 at 1.27.04 PM.png)
