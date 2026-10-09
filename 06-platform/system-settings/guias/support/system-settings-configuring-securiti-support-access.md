---
title: "Configuring Securiti support access"
slug: "system-settings-configuring-securiti-support-access"
updated: 2026-07-16T12:25:57Z
published: 2026-07-16T12:25:57Z
canonical: "helpcenter.securiti.ai/system-settings-configuring-securiti-support-access"
stale: true
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Configuring Securiti support access

Securiti administrators can enable and manage support agent access to your Securiti account. You use this feature to let Securiti tech support agents temporarily access your account for troubleshooting purposes. For security, Securiti maintains an audit log of all actions taken through the support account.

To check the support access audit log of activities taken through the support account:

1. On the **Support Access** page, click the **Audit Trail** tab.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/support-user-audit_trail(1).png)

## Supported permissions

Securiti distinguishes between regular users and support users to ensure proper access control. Therefore, the support user is limited to a few actions; however, the support user can still perform actions depending on the provided role during user creation.

A support user can not perform the following actions.

- Download evidence files
- View evidence files
- Form owner
- Assessment messaging
- Incident owner
- Change to guest user
- User deactivation
- Password reset
- Forgot password

## Create a support user

To manage the support access, you must create a support user and assign the roles. The assigned role lets the support user access the customer's infrastructure and perform actions accordingly.

To enable support access:

1. In Securiti click **Settings** and choose **Support > Support Access**.
2. Click **Enable Support Access**.
3. Apply the following settings, then click **Save**:

| Setting | Description |
| --- | --- |
| Select Role | Select the role to assign to the support agent. > [!NOTE] > Note > > If you assign **Super Admin** role to the support users, they can see both active and inactive organizations within your tenant. |
| Select Expiry Date | Select the date on which support access expires. The default is the following day. |
| Select Expiry Time | Select the time at which support access expires. |
| Exclusive Access | (Optional) Restrict access to specific support agents by entering each agent's **securiti.ai** email address and pressing Enter. Securiti displays the list of allowed agents below the field. If you leave this field empty, any Securiti support agent can access your account. |
| Select Organizations | Select the organizations the support user can access. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Privaci_support_access.png)

## Related

- [Managing Securiti users](/configuring-access-management-managing-securiti-users.md)
- [Using Roles in Securiti](/roles-in-securiti.md)
