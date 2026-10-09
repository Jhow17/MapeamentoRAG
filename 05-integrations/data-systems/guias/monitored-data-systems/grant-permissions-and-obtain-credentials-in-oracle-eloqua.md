---
title: "Prerequisites for Oracle Eloqua (Self-hosted)"
slug: "grant-permissions-and-obtain-credentials-in-oracle-eloqua"
updated: 2026-04-06T21:00:01Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-oracle-eloqua"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Oracle Eloqua (Self-hosted)

## Using the admin account access

To create a security group with required permissions and assign users, you must have admin privileges in the Oracle Eloqua.

## 1. Assigning required permissions to a security group

1. Create a security group in your Oracle Eloqua application. For more information, see Oracle Eloqua’s documentation on [Creating a security group](https://docs.oracle.com/en/cloud/saas/marketing/eloqua-user/Help/SecurityGroups/Tasks/CreatingSecurityGroups.htm).
2. On the **Security Group Overview** page, click **Action Permissions**, as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-01 at 10.03.45.png)

On the action permissions page, under the **Forms** section, select `View Form Submission Data`, as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-01 at 10.12.28.png)

On the action permissions page, under the **Management** section, select the following permission, as shown below:

To learn more about assigning action permission, see Oracle Eloqua’s [Setting action permissions](https://docs.oracle.com/en/cloud/saas/marketing/eloqua-user/Help/SecurityGroups/ActionPermissions.htm).
  - `Access to App Cloud Developer`
  - `Manage Users (General)`

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-01 at 10.22.13.png)
3. On the **Security Group Overview** page, under **Settings**, grant **Interface Access** to `AppCloud Developer`, as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-01 at 11.34.18.png)

To learn more about granting interface access, see Oracle Eloqua’s [Interface access](https://docs.oracle.com/en/cloud/saas/marketing/eloqua-user/Help/SecurityGroups/InterfaceAccess.htm).
4. On the **Security Group Overview** page, click **Licensing**, as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4XTP1D3U.png)

In the **Licensing** section, mark `Eloqua Marketing Platform`, as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-01 at 11.43.28.png)

To learn more about licensing, see Oracle Eloqua’s [Changing license availability for a security group](https://docs.oracle.com/en/cloud/saas/marketing/eloqua-user/Help/SecurityGroups/Tasks/ChangingLicenseAvailability.htm).

## 2. Creating and assigning users to the security group

You must create a user and assign that user to the security group you created above. For more information on user creation, see Oracle Eloqua’s [Creating individual users](https://docs.oracle.com/en/cloud/saas/marketing/eloqua-user/Help/UserManagement/Tasks/CreatingIndividualUsers.htm).

On the **New** **User** screen, grant **Privileged** **Access** of `Asset Manager` to the user.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-01 at 11.46.19.png)

> [!NOTE]
> Tip
> 
> Any permissions or licenses granted to the security group is inherited to the users added in it.

## 3. Registering an application and recording credentials

The Oracle Eloqua Data system requires Client ID, Secret, and URL to establish a successful connection with Securiti.

1. Log in to your Oracle Eloqua portal as per your Oracle Eloqua’s POD or Data Center location, as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Oracle Eloqua.png)
2. After logging in to your Oracle Eloqua portal, record the **Base URL** to use later, as shown below

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-01 at 11.55.44.png)

The **Base URL** must be in the following format:

`https://secure.p0x.eloqua.com`
3. Register an application. For more information on Oracle Eloqua’s app registration, see [Register an application](https://docs.oracle.com/en/cloud/saas/marketing/eloqua-develop/Developers/AppCloud/Register/register-app-and-services.htm).
4. After registering an app, under **AppCloud Developer** > **Authentication to Eloqua**, copy the **Client ID** and **Client** **Secret**, as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-18 at 9.14.10 AM.png)
5. Proceed to [(New UI) Connecting the Oracle Eloqua (Self Hosted) with Securiti](/latest/docs/new-ui-connecting-the-oracle-eloqua-self-hosted-with-securiti).
