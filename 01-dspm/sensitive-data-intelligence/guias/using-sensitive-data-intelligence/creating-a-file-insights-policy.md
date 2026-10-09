---
title: "Creating a File Insights policy"
slug: "creating-a-file-insights-policy"
updated: 2026-07-22T11:47:52Z
published: 2026-07-22T11:47:52Z
canonical: "helpcenter.securiti.ai/creating-a-file-insights-policy"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Creating a File Insights policy

> [!WARNING]
> Important
> 
> Before configuring a policy, run the required scans to gather metadata for identifying files that match your policy conditions. These may include Data Inventory Syncs, Discovery Scans, and Access Intelligence Scans.

To create a File Insights policy:

1. From the main menu, choose **Policies**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-URFR8B76.png)
2. On the **Policies** page, choose **File Insights**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6TKYJQZE.png)
3. Near the upper right corner of the page, click **+ Create**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-93UG0QZ5.png)
4. Enter a **Name** and **Description** for the policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-A9AQ98U4.png)
5. Set the **Severity** level to calculate the overall data risk score for the policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IS32ESJ1.png)
6. Set the policy **owner**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6X1F9KAE.png)
7. (Optional) Set the policy **co-owners**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1SO6OJRT.png)
8. To activate the File Insights policy, turn on the **Activate Policy** toggle, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DK7KDDIP.png)
9. In the **Scope** section, click **Edit Query** to add files to your scope, as shown below. This opens the **Graph Explorer**, where you can select the file scope and relevant data elements (such as first name, last name, SSN, and so on). Review the query results carefully to ensure the scoped files match your expectations. Then click **Use Query** to apply the selection. The scope is now defined, and you are returned to the File Insights policy configuration page.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LZPT2SI4.png)

To learn more about **Graph Explorer**, see the [Graph Explorer](/latest/docs/using-data-command-graph) documentation. Securiti can automatically carry over queries created in Graph Explorer to the policy creation page. For more information, see [Create policies using Graph Explorer](/latest/docs/create-policies-using-graph).
10. To view the number of files included in the scope, click **Show Impact** in the **Scope** section, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-27Y2ZVCY.png)
11. Click **Create Policy.** Once created, the policy appears on the File Insights **Policies** page, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6J9AY1PV.png)
