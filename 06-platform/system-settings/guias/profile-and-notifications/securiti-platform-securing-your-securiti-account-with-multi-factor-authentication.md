---
title: "Securing your Securiti account with multi-factor authentication"
slug: "securiti-platform-securing-your-securiti-account-with-multi-factor-authentication"
updated: 2026-09-21T16:06:37Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/securiti-platform-securing-your-securiti-account-with-multi-factor-authentication"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Securing your Securiti account with multi-factor authentication

Multi-factor authentication (MFA) adds a second check to your Securiti login. When MFA is active on your account, you enter your password and then a six-digit verification code.

Each method that can produce a verification code is called a factor. Your account can have one factor or both factors enabled at the same time, which are mentioned in [Available Factors](/latest/docs/securiti-platform-securing-your-securiti-account-with-multi-factor-authentication#available-factors2) section. This article describes the available factors, how you enable and remove them, how your organization can require a specific factor, and the solution when you lose access to a factor.

## Available factors

Use the following table to understand each available factor in Securiti:

| **Factor** | **Description** |
| --- | --- |
| Email | Securiti sends a code to the email address on your account. |
| Authenticator app | An Authenticator app on your device generates the code, for example Google Authenticator. |

The sole first factor you enable becomes your primary factor and Securiti selects your primary factor by default for login. If you have both factors and you remove one factor, the factor that remains becomes your primary factor. With both factors enabled, Securiti selects Authenticator app factor as your primary factor.

> [!NOTE]
> **Note**
> 
> When you enable your first factor, Securiti ends your other active sessions. You must log in again on your other devices.

Your available factors depend on whether your organization requires MFA, and which factor it requires. Use the following table to understand the details of each state.

| **Organization’s setting** | **Required action** |
| --- | --- |
| Does not require MFA | You choose whether to use MFA or not. You can enable either one factor or both factors, or turn off MFA. |
| Enforces MFA | Once your organization enforces MFA, it automatically activates email factor for all users that do not have any MFA factor enabled. At your login screen, Securiti asks you for MFA code sent to you email. You cannot turn this factor off. However, you can turn off email factor only when you enable Authenticator app factor for your account. |
| Enforces MFA with Authenticator app | Once your organization enforces Authenticator app MFA, it automatically activates and requires you to configure at login screen. Once you configure it, you can login to your Securiti account. You cannot turn this factor off. On successful Authenticator app factor setup, Securiti removes your existing email factor and blocks you from activating email factor. |
| Enforcing MFA for privileged users only | This happens when your administrator limits enforcement of any MFA factor to privileged users only. This only pushes the privileged users in your Securiti tenant to use the MFA. This enforces the MFA with the following rules: - For privileged users, Securiti applies “Enforces MFA with Authenticator app” explained above. - For non-privileged users, Securiti applies “Enforces MFA” explained above. |

> [!NOTE]
> **Note**
> 
> If you log in through Single Sign-On, your identity provider handles authentication and Securiti does not prompt you for a verification code.

### Accessing MFA page

To access the Multi-factor authentication page in Securiti, proceed with the following steps.

1. In Securiti, near the bottom of the left navigation bar, click your avatar and choose **Manage Account**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TKZBKAAM.png)
2. In your **Manage Account** page, click the **Multi-factor Authentication** tab.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6K194KBE.png)

This tab lets you configure the factor for your account, or displays the available factors if already existing in your account.

## Configuring MFA for your account

You can configure MFA for your account with any of the following options:

- Email factor
- Authenticator app factor
- Email and authenticator app both

Proceed with the following given procedure to configure your MFA.

### Configuring email factor

To configure email factor, proceed with the following steps:

1. On the **Multi-factor authentication** tab, click **Set up MFA**.
2. From **Set up Multi-Factor Authentication** popup, select **Email** option. After selecting, click **Continue**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-P6MG80OY.png)

Securiti sends a six digit MFA code to your account email.
3. On the **Let’s set up your Email** popup, enter the six digit code Securiti sent to your account email.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-P9N7RI1Y.png)

Securiti enables the Email factor in your account.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1A4PFM62.png)

> [!NOTE]
> **Note**
> 
> If your organization enforces the Authenticator app factor for your account, the control for enabling email is disabled. Hover over it to see the reason.

### Configuring Authenticator app factor

You must install any Authenticator app in your mobile phone, for example Google Authenticator. To configure Authentication app factor, proceed with the following steps:

1. On the **Multi-factor Authentication** tab, click Set up MFA.
2. From **Set up Multi-Factor Authentication** popup, select **Authenticator App** option. After selecting, click **Continue**.

It displays **Setup Authenticator App** popup, with a QR code to scan and secret keys.
3. On the **Setup Authenticator App** popup, perform one of the following actions:
  1. Use the QR code to configure MFA with following steps:
    1. Open your Authenticator app and add a new MFA in it.
    2. From the available options in Authenticator app, select **Scan a QR code** or a similar option.

It opens the camera of your mobile phone within the Authenticator app.
    3. Using that camera inside your Authenticator app, scan the QR code displaying in the **Setup Authenticator App** popup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-70BTUHKN.png)

After scanning, your Authenticator app automatically stores your Securiti accounts and starts displaying MFA code.
    4. Below the QR code, enter the six digit MFA code from your Authenticator app.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JY0PDOBC.png)
    5. After adding, click **Verify Code**.

If the entered code is correct, it verifies it and saves the Authenticator app as a factor.
  2. Use the secret key to configure MFA with following steps:
    1. After seeing the **Setup Authenticator App** popup where you can see QR code and secret keys both, copy the secret keys.
    2. On your Authenticator app, add a new MFA and select Enter a setup key.
    3. On your Authenticator app, enter the secret keys displaying in your Setup Authenticator App popup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KLO2PR04.png)

After scanning, your Authenticator app automatically stores your Securiti accounts and starts displaying MFA code.
    4. Below the QR code, enter the six digit MFA code from your Authenticator app.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JY0PDOBC.png)
    5. After adding, click **Verify Code**.

If the entered code is correct, it verifies it and saves the Authenticator app as a factor.

Securiti enables the Authenticator app factor. Codes change every few seconds, so if a code is not accepted, enter the next one the app shows. The QR code and setup key stay valid while you retry.

> [!NOTE]
> **Note**
> 
> If your organization requires the Authenticator app factor for your account, Securiti removes your email factor once you complete this setup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PZYKLXMR.png)

## Enforcing MFA for users

If you are an administrator, you can enforce MFA for the users in your organization and choose which factor they use.

Use the following table to understand the details of the settings.

| **Setting** | **Description** |
| --- | --- |
| Factor | Securiti lets you enforce the following factors: - Email - Authenticator app |
| Enforce MFA | You can either enforce users to use Authenticator app as an factor, or any of the supporting factors. |
| Scoped users | For email factor, it applies to all the users. For Authenticator App factor, it supports the following types of users in scope of enforcing MFA: - All the users in the tenant - Privileged users are those users who have access to every single resource, that is a `Super Admin`. |

To enforce the MFA to the users, proceed with the following steps:

1. In Securiti, at the top left of your screen, click the **Jewel** icon. From the Platform Services section, select **Settings**.
2. From the left menu bar under **System Settings**, select **Security > Login Settings**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-C2IS2UWL.png)
3. Near the upper right corner of the **Login Settings** area, click **Edit** (**pencil icon**).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-P4GO9U6L.png)
4. In the settings, mark **Force Enable MFA**. This enforces all users to use MFA in their accounts. By default, by marking this checkbox, it applies the email factor to the users.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-O85NZUNE.png)
5. Below the **Force Enable MFA**, mark **Enforce Authenticator App**. This enforces Authenticator App factor instead of email to the users.

When you select it, it displays a new **Apply to** dropdown menu.
  1. From the **Apply to** dropdown menu, select any of the following:

| Parameter | Description |
| --- | --- |
| Privileged users only | Privileged users are those users who have access to every single resource, that is a Super Admin. |
| All users | It applies this factor to all the users in the tenant. |
6. From the **Require an authenticator app popup**, click **Yes, continue**.

This applies the MFA to users in your tenant.

## Logging in with multi-factor authentication

Once you setup your MFA for your account, proceed with the following steps:

1. Open the Securiti platform in your browser.
2. On the login screen, enter your email and password for your account.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0FC85H8H.png)
3. Enter the MFA verification code. For your Authenticator app, copy the code from the app and paste it here. For the Email factor, Securiti sends the MFA code to your email.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-M2K0BAXK.png)
4. To skip the code on later logins from the same device, mark **Remember this device for 30 days**.

The page lists only the factors enabled on your account, and selects your primary factor by default:

- If both factors are enabled, you can switch to the other factor.
- If only the email factor is enabled, Securiti sends the code automatically to your email.
- If only the Authenticator app factor is enabled, the page does not offer an email code.

## Removing your factor

You can remove a factor when another factor is enabled and verified on your account. Securiti asks for your password and for a valid code from the factor you are removing, which confirms that you still have access to it.

1. On the **Multi-Factor Authentication** tab, next to the factor you want to remove, click three dots (**Options**) and click **Remove**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-3BI5WMFU.png)
2. On the popup, enter your Securiti password.
3. Enter a code for the factor you are removing:
  - To remove the email factor, click the option to send a code, then open the email from Securiti and enter the code.
  - To remove the Authenticator app factor, enter the current code from your Authenticator app.
4. Confirm the removal.

Securiti removes the factor and makes the remaining factor your primary factor.

> [!NOTE]
> **Note**
> 
> The **Remove** option is disabled for your last remaining factor, whether or not your organization requires MFA. This keeps at least one factor on your account. To remove all factors at once, see [Turning off multi-factor authentication](/latest/docs/temp-new-mfa-page#turning-off-multifactor-authentication).

## Turning off your MFA

This action removes all factors from your account. It is available only when your organization does not enforce the MFA. When your organization requires MFA, you can change which factors you use, but you must keep at least one factor in your account.

1. On the **Multi-Factor Authentication** tab, click **Turn off MFA**.
2. It shows you a popup with a warning. It means that if you disable the MFA from your account, if you have any existing trusting devices in your profile settings, disabling it automatically removes them from your account. To continue, click **Continue with MFA Disable**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FJR5ZIGZ.png)
3. It displays a **Disable MFA** popup asking you to enter your account password. On this popup, enter your account password.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Y6CWS5C5.png)
4. Then, on the **Confirmation required to turn off MFA** popup, enter your six digit verification code either sent to your email or Authenticator app.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-B33GHALH.png)

After verifying the code, it removes the MFA from your account.

## Disabling or reset MFA of a user

Being administrator, you can remove the MFA of a certain user in your tenant. This assists if the user has lost access to the MFA. You must meet the following conditions in order to remove the MFA from a user:

- Tenant does not enforce the MFA.
- You must have the `Super Admin` role.

To remove the MFA from an account, proceed with the following steps:

1. In Securiti, at the top left of the screen, click **Jewel** icon.
2. From the Platform Services section, select **Settings**.
3. From the System Settings left menu bar, select **Organizational > Access Management > Users**. It opens the Users page.
4. Select a user you wish to remove the MFA. On the right side of that row, click three dots (**Options**).
5. From the menu, click **Disable MFA**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OZ6KX7AB.png)
6. On the **User Settings** popup, click **Disable MFA**. It gives you a warning, click the **Disable MFA** again.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-H5K1496R.png)

It removes MFA from the user.
7. (Optional) For resetting the Authenticator app factor, right below the **Disable MFA**, click **Reset Authenticator MFA**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0WAD4E55.png)
8. On the **User Settings** popup, click **Reset Authenticator MFA**. It gives you a warning, click **Reset Authenticator MFA** again.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7G9ZTI65.png)

It resets the Authenticator factor from your account.

## Recovering MFA

If you lose access to your MFA in any case, see the following table to understand the details of each situation.

| **Condition** | **Solution** |
| --- | --- |
| You cannot reach the device with your Authenticator app, and the email factor is also enabled | Switch to the email factor on the login page and enter the code sent to your email address. |
| You lose the device with your Authenticator app, and it is your only factor | Contact your tenant administrator or [support@securiti.ai](mailto:support@securiti.ai) to request an Authenticator app reset. |
| You cannot receive email at the address on your account | Use your Authenticator app if it is enabled. Otherwise, contact your tenant administrator or [support@securiti.ai](mailto:support@securiti.ai). |
