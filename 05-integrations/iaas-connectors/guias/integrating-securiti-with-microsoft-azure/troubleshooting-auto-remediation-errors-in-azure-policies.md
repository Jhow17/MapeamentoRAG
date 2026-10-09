---
title: "Troubleshooting Auto-Remediation Errors in Azure Policies"
slug: "troubleshooting-auto-remediation-errors-in-azure-policies"
updated: 2026-01-05T08:22:52Z
published: 2026-01-05T08:22:52Z
canonical: "helpcenter.securiti.ai/troubleshooting-auto-remediation-errors-in-azure-policies"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting Auto-Remediation Errors in Azure Policies

Securiti provides auto-remediation capabilities for Azure posture policy rules, similar to those available for other cloud platforms. If you encounter internal errors during auto-remediation, follow these steps to resolve them and enable seamless execution:

### Step 1: Locate Your App Registration

1. In the Azure portal, navigate to **App Registrations**.
2. Click **All Applications** to view the list of registered apps.
3. Locate the app registration created during the setup of your connector. Search by the date of setup if needed.
4. Copy the **Display Name** of the app for later use.

![Troubleshoot-azure-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc59ca22-7a41-40aa-267a-b11b396824da.png)

### Step 2: Create a Custom Role

1. Navigate to the **Subscriptions** tab in your Active Directory.
2. From the left-hand panel, select **Access Control (IAM)**.
3. Click on the **Role Assignments** tab.

![Troubleshoot-azure-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08fa828b-6fad-04dc-498a-135a21152ed0.png)
4. Under **Create a Custom Role**, click **Add**.

![Troublesoot-azure-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ca66dd11-747c-78f2-d9ac-17308a228602.png)
5. On the **Create a Custom Role** page:
  1. Provide a name for the custom role (e.g., "Auto-Remediation Role").
  2. Go to the **Permissions** tab and search for the specific permission required by the remediation policy. For example, for Azure Storage, search for

```plaintext
Microsoft.Storage/storageAccounts/write
```

![Troubleshoot-azure-4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9439f184-0cfe-6b1e-dd9e-f05b5bb17448.png)
  3. Add the required permission and save the custom role.

### Step 3: Assign the Custom Role to Your App Registration

1. Return to the **Access Control (IAM)** tab.
2. Click **Add Role Assignment** under the **Add** tab.

![Troubleshoot-azure-5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-72f928f3-3f4a-ffe8-5eca-d17d4b82897e.png)
3. Search for the custom role you created in Step 2.

![Troubleshoot-azure-6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad199e28-6921-b8f7-0281-66f369ec4675.png)
4. Click **Next** to move to the **Members** tab.
5. In the **Assign Access** To menu, select **User**, **Group**, or **Service Principal**.

![Troubleshoot-azure-7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a063ef8e-b9af-431b-163e-8df914228615.png)
6. Click **+ Select Members** and paste the **Display Name** of your app registration copied earlier.
7. Select the app from the menu and click **Close**.
8. On the **Add Role Assignment** page, click **Next**.

![Troubleshoot-azure-8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2209bf7b-674b-75ca-232b-6eabec4376e9.png)
9. Review your selections and click **Review + Assign** to complete the process.

After completing the steps above, you can create Azure Storage policies with auto-remediation enabled. The assigned permissions ensure that remediation tasks execute without errors.
