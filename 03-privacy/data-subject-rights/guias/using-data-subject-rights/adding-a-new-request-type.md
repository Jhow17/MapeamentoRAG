---
title: "Adding a new request type in a regulation"
slug: "adding-a-new-request-type"
updated: 2026-01-14T09:39:49Z
published: 2026-01-14T09:39:49Z
canonical: "helpcenter.securiti.ai/adding-a-new-request-type"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Adding a new request type in a regulation

You can add custom requests if out-of-box requests don’t meet your organization’s needs.

To add a new regulation:

1. From the Regulations Support dashboard, at the end of the row, click **More Actions**(3 dots) **> Add Request Type**.

![Table displaying various regulations, including China PIPL and their deadlines.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-08 at 12.29.29 PM.png)
2. On Add Request Type popup, fill the following information:

| Request Type Value | Choose the request type from the menu. These values are populated from the [Request Types](/v1/docs/configuring-dsr-request-types) dashboard. |
| --- | --- |
| Request Type Label | Specify a label for the request type. |
| Deadline | Enter the request’s response deadline in days. The maximum value is 1000 days. |
| Extension Period | Enter the extension period in days. The value must be between 1 and 365 days. |
3. Once done, click **Add**

After adding, the Associated DSR Forms dialog appears. It lists all DSR forms affected by the regulation changes. You must review each listed form, make the required changes, and then republish it.

> [!NOTE]
> Note
> 
> The newly added request type is marked as User Defined, and the regulation’s Source changes to Customized.

### Edit or delete a request type

You can also edit or delete a request type from a regulation.

1. On the Regulations Support dashboard, expand the regulation to view its request types.
2. At the end of request type row, click **More Actions** (3 dots) > **Edit Request Type** or **Delete Request Type**.

![Overview of data subject rights regulations with highlighted access request type.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-08 at 2.56.39 PM.png)
3. Make the changes or confirm deletion.

After saving, the Associated DSR Forms dialog appears. Review and republish the listed forms.

- If both the regulation and request type are **Standard**, editing marks both as **Customized**.
- If both are **User Defined**, their sources remain unchanged.
- When a request type is deleted, the regulation’s Source changes to **Customized**.

### Reverting a customized request type to default

You can revert a customized request type to its standard configuration using the Revert to Default option.

To revert a request type to default:

1. On the Regulations Support dashboard, expand the regulation to view its request types.
2. Locate the request type where the Source is marked as Customized.
3. At the end of the request type row, click **More Actions** (3 dots) > **Revert to Default**.

![Overview of data subject rights regulations with highlighted access request type.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-08 at 3.03.21 PM(1).png)
4. In the confirmation dialog, click **Yes, Revert** to restore the request type to its default configuration.

After reverting, the Associated DSR Forms dialog appears. It lists all DSR forms affected by the regulation changes. You must review each listed form, make the required changes, and then republish it.

> [!NOTE]
> Note
> 
> The Revert to Default option is available only for request types with the Customized source. It is not available for User Defined or Standard request types. Reverting a request type to default changes only the request type’s source back to standard. The regulation remains customized.
> 
> If the regulation itself is reverted to default, both the regulation and all associated request types are set to standard.
