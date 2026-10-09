---
title: "Creating a Structured Data Insights policy"
slug: "creating-a-structured-data-insights-policy"
updated: 2026-08-18T16:12:49Z
published: 2026-08-18T16:12:49Z
canonical: "helpcenter.securiti.ai/creating-a-structured-data-insights-policy"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Creating a Structured Data Insights policy

To create a Structured Data Insights policy:

1. From the upper-left corner, click the **Jewel** icon to open the main menu, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NN5VEAP0.png)
2. From the main menu, choose **Policies**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8225DL81.png)
3. On the **Policies** page, choose **Structured Data Insights**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-I4SCUZSP.png)
4. Near the upper-right corner, click **+ Create**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-W4FQY2WK.png)
5. Enter a **Name** and **Description** for the policy, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DJU9W98N.png)
6. Select the policy **owner**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-G7YUI9P9.png)
7. (Optional) Select one or more policy **co-owners**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-M6C8HPQZ.png)
8. Enable **Activate Policy** toggle to run the policy immediately after it is created, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ANYC6P39.png)
9. In the **Scope** section, click **Edit Query** to define the policy scope. This opens Graph Explorer, where you can build a query to select the columns you want the policy to evaluate. After creating the query, review the query results to confirm that the selected columns match your requirements, then click **Use Query** to apply the query. For more information, see the [Graph Explorer](/latest/docs/using-graph-explorer) and [Create policies using Graph Explorer](/latest/docs/create-policies-using-graph).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-I6OWVSOP.png)
  - In this example, 132 columns match the defined query criteria, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-UHQQ2N6S.png)
10. Click **+ Add Actions** to configure one or more actions for the policy, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6W6NDQ8K.png)

## Generating findings

The **Generate Findings** action lets you create findings for data that matches the configured policy scope. You can assign a severity level to help prioritize and manage the generated findings.

The **Generate Findings** action is selected by default. To configure the **Generate Findings** action:

## Sending email notifications

The **Send Email Notifications** action lets you notify the policy owner and other users when the policy identifies new findings.

To configure the **Send Email Notifications** action:

## Triggering workflow

The **Trigger Workflow** action lets you automatically start a workflow when the policy identifies data that matches the configured policy scope.

To configure the **Trigger Workflow** action:
  1. In the **Actions** section, next to **Generate Findings** action, click **Edit**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XSBXWK5R.png)
  2. Select one of the following severity levels, as shown below.
    - Informational
    - Low
    - Medium
    - High
    - Critical

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2R8USNM9.png)
  3. Click **Save Action**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SR64G1ZN.png)
  1. Click + **Add Actions** and choose the **Send Email Notifications** action, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RPO8XG0M.png)
  2. (Optional) In the **Send Email Notifications** popup, mark the **Notify Store Owner** checkbox to send an email notification to the policy owner, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JO9YWX8F.png)
  3. (Optional) To notify additional users, enter their username or email address in the search field and select them from the list. Each added user appears as a tag below the field, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Q3GKV8MN.png)
  4. Click **Save Action**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DMLHVIFP.png)

> [!NOTE]
> Note
> 
> - Email notifications are sent only for active policies and to the configured recipients.
> - Email notifications are sent once each day at 12:00 AM UTC, regardless of the recipient's time zone.
> - Email notifications are sent only when the policy identifies new findings during the previous 24 hours.
> - If the same recipient is configured for multiple policies within the same policy category, Securiti sends a single email that includes the aggregated number of new findings. Recipients may receive separate emails for policies that belong to different categories.
> - Each email notification includes the total number of new findings and a **View Findings** link that opens the **Findings** page in Securiti.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1785913659089.png)
  1. Click **+ Add Actions**, and choose **Trigger Workflow** action, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0Z0M8QOC.png)
  2. Select the workflow that you want the policy to trigger, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4U27PUQM.png)
  3. Click **Save Action**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0EOCDDE3.png)
11. Click **Create Policy**. Once created, the policy appears on the Structured Data Insights **Policies** page, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EIXUC72X.png)
