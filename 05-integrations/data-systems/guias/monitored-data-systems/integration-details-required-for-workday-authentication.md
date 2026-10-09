---
title: "Integration details required for Workday authentication"
slug: "integration-details-required-for-workday-authentication"
status: "new"
updated: 2025-11-03T06:15:02Z
published: 2025-11-03T06:15:02Z
canonical: "helpcenter.securiti.ai/integration-details-required-for-workday-authentication"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Integration details required for Workday authentication

1. Log in to your Workday instance.
2. Workday requires the following integration setup details:
  - [Create Integration System User](/v1/docs/integration-details-required-for-workday-authentication).
  - [Create Integration Security Group](/v1/docs/integration-details-required-for-workday-authentication).
  - [Security Configurations - Configuring domain security permissions](/v1/docs/integration-details-required-for-workday-authentication).
  - [Activate security policy changes](/v1/docs/integration-details-required-for-workday-authentication).
3. To create Integration System User:
  1. In Workday, search and select **Create Integration System User** Task.
  2. Enter a User Name and Password on the Create Integration System User page, and leave the Session Timeout Minutes value to '0', as shown below.

> [!NOTE]
> **Important**
> 
> Record the username and password to use later.

![Create_Integration_System_User.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-56721aaa-bf95-3f16-a7bd-fa8869b898f6.png)

Click **OK**
  3. Now search and select **Maintain Password Rules** Task.

![Search_Maintain_Password_Rules.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-76844335-9828-b677-9f33-1ec5ea4e8fe1.png)
  4. Search and add the Integration System User you created above to the System Users exempt from the password expiration box.

![Session_Timeout.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-418cd435-918d-3811-c5bb-0e3550030760.png)
4. Create a Integration System Security Group:

You can create a Security Group from the two types of Integration System Security Groups available:
  - (Option 1)**Integration System Security Group (Constrained):** It limits data access to designated organizations.

To create a Integration System Security Group (Constrained), see the steps below:
    1. In the Workday top search bar, search and select **Create Security Group** Task.

It opens a Create Security Group popup.
    2. On the **Create Security Group** popup, do the following settings.
      1. Select the **Integration System Security Group (Constrained)** from the **Type of Tenanted Security Group** menu.
      2. Enter a convenient name for the security group.
      3. Click **Ok**.

![Create-Constrained.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ed65bdee-babc-f64c-acdb-645ac7e10aec.png)

It opens a newpage to edit further setting for **Integration System Security Group (Constrained)**
      4. On the **Edit Integration System Security Group (Constrained)** page, apply the following settings:
        1. Select the users from the **Integration System Users** menu which you created earlier.
        2. Select the organization from the **Organizations** menu.
        3. Mark the radio button for **Access Rights to Organizations** that suits you the best.
        4. Click **Ok** to create Integration System Security Group (Constrained).

![edit-constrained.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-676aa970-defc-9e02-11f2-69a86d03408a.png)
  - (Option 2) **Integration System Security Group (Unconstrained):** It grants unrestricted access to data within the entire account.

To create a Integration System Security Group (Unconstrained), see the steps below:
    1. In the Workday top search bar, search and select **Create Security Group** Task.

It opens a Create Security Group popup.
    2. On the **Create Security Group** popup, do the following settings.
      1. Select the **Integration System Security Group (Unconstrained)** from the **Type of Tenanted Security Group** menu.
      2. Enter a convenient name for the security group.
      3. Click **Ok**.

![create-unconstrained.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-67760771-27ab-7fe4-72b6-e3d95f59fc5a.png)

It opens a newpage to edit further setting for **Integration System Security Group (Unconstrained)**
      4. On the **Edit Integration System Security Group (Unconstrained)** page, apply the following settings:
        1. Select the users from the **Integration System Users** menu which you created earlier.
        2. Click **Ok**. to create Integration System Security Group (Unconstrained).

![edit-uncontrained.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ee7f6389-3cf8-459d-9d56-4d9a7908e979.png)
5. To configure domain security policy permissions:
  1. In Workday, search and select the **View Security for Securable Item** task.
  2. On the popup for View Security for Securable Item, enter a name for the Securable Item by selecting from [these](/v1/docs/access-required-for-workday-modules) web services (domains) according to the modules you want to use, for example **Get Change Government IDs**.

![Securable_item.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9d564fd8-711c-6d83-caac-ff9940102178.png)

Click **OK**
  3. To run posture scans, add the user group to the list of **Permitted Security Groups** for the Web Service Task **Get Integration System Users**.

![workday_getintegration_sysusers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc0092f7-5222-bf04-e4cf-0bb3174a30d9.png)
  4. Workday displays the Tasks page with your entered web service name, as shown below.

![workday_getintegration_viewsecurity.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0c9dea45-7ddc-ce99-6db0-c93dfe787352.png)
  5. Click **View Security** for the task, as shown below.
  6. Configure the user security group if isn't already mentioned in the Permitted Security Groups:
    1. Click **Actions** (three horizontal dots), next to the policy name under Security Policy column.

![workday_editpermissions_securitygroup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-01f98cb8-4879-841c-8112-2b0a97d2a023.png)

Select **Domain Security Policy > Edit Permissions**.
    2. Click **+** (plus sign) on the Integration Permissions table to add the security group you want to assign access to, as shown below.

![Click plus sign.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-470785a7-baf2-f0fe-c170-c572614f83dc.png)
    3. Search for the security group (example: QA), and assign **Get** operations access by marking the checkbox in the Get column to its right, as shown below.

![Get_operation_-_QA.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0112ce0e-2c65-0d2f-e303-965fbd17da12.png)

Click **OK**
  7. For all the web services you want to assign access to, repeat steps 5b to 5f.
6. **Once you've assigned user security groups to all the web services, you must activate those changes.**

**To activate security policy changes:**
  1. In Workday, search **Activate Pending Security Policy Changes**.

![Activate_Pending_Security_Policy_Changes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c256e1c-b707-ac16-b46a-ac19b8d92d15.png)
  2. Add a comment and click **OK**.
  3. Mark the **Confirm** checkbox and click **OK**.
7. Proceed to [Acquire authentication credentials in Workday](/v1/docs/acquire-authentication-credentials-in-workday).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
