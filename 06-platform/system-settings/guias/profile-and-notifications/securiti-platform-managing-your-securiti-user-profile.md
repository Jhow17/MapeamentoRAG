---
title: "Managing your Securiti user profile"
slug: "securiti-platform-managing-your-securiti-user-profile"
status: "update"
updated: 2026-09-25T06:41:25Z
published: 2026-09-25T06:41:39Z
canonical: "helpcenter.securiti.ai/securiti-platform-managing-your-securiti-user-profile"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Managing your Securiti user profile

Your user profile lets you configure and update information about your account. You can use your profile page to:

- Configure basic profile information, including things like your name, email address, and the language for Securiti pages and dashboards
- Add an avatar photo or image
- Change organizations (If enabled for your Securiti tenant)
- Manage your trusted devices
- View and manage your user sessions

If you are a system user or administrator (as opposed to a guest user), you can also:

- Change your Securiti password
- Configure MFA as described in [Securing your Securiti account with multi-factor authentication](/v1/docs/securiti-platform-securing-your-securiti-account-with-multi-factor-authentication)

### Opening your user account management page

- In Securiti, near the bottom of the left navigation bar, click your avatar and choose **Manage Account**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XQGCGXST.png)

It opens the **Manage Account** page.

### Uploading an avatar icon or photo

1. In the profile picture area of your user profile page, click **Upload**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZSMKJVVW.png)
2. Either drag an image file into the drag & drop box, or click Select a file to upload and navigate to and select the file.
3. On the drag & drop box, click **Upload**.
4. Near the right edge of the page, click **Save**.

### Configuring basic pro file information

1. In the Basic Information area of your user profile page, click **Edit Profile**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JZLBJ7GV.png)
2. Configure the following settings to suit:

| First Name | Configure to suit. |
| --- | --- |
| Last Name |
| Phone number |
| Email | Shows your primary email address. You cannot edit the Primary Email. |
| Language | Choose the language in which you want Securiti to display its user interface. This setting applies only to you, not to other Securiti users. |
| Message Digest (System users only) | Use the menu to choose the frequency with which Securiti emails you a message digest of all Securiti chat messages addressed to you or sent by you. |
| Session timeout | Set the amount of time your login session is idle before Securiti automatically logs you out. |
| Primary Organization | If you have enabled the organization-level access feature, and belong to more than one organization, choose the organization you log in to by default. You can also change the organization when you log in, as described in **Changing your organization** below. |
3. Near the upper right corner of the Basic Information area, click **Save**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BA02OZTM.png)

### Changing your Securiti password

To secure your account, Securiti enforces the following password rules:

- You must change your password at least every 3 months.
- Securiti automatically logs you out if your session is inactive for more than 15 minutes.
- Securiti stores all passwords as salted, one-way hashes.

To change your Securiti password:

1. On your User Profile page, click the **Change Password** tab.
2. Enter your current and new password in the boxes.

Your password must contain:

Your password must not contain:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PLNSH90E.png)
  - At least 10 characters
  - At least one special character
  - At least one numeric character
  - At least one upper-case character
  - Any repetitions of three or more characters or numbers, for example “aaa” or “111”
  - Any sequences of three or more consecutive characters or numbers, for example “abc” or “123”
3. Click **Update Password**.

> [!NOTE]
> **Note**
> 
> Securiti checks against a database of known compromised credentials to prevent the use of weak or previously exposed passwords. If a match is found, an error message prompts you to choose a different password, as shown below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(226).png)

### Changing your organization

If the Manage Org Units premium feature is enabled for your Securiti tenant, and you belong to more than one organization, you can change between the different organizations you belong to. Doing so lets you view, edit, and create elements and resources such as assessments, workflows, DSRs, etc., belonging to that organization.

If the Multiple Org Unit Selection feature is also enabled, you can choose multiple organizations at a time, and so create aggregated views across those organizations on the same dashboards. When doing so, you can view elements and resources that belong to any of the selected organizations. You can also create, edit, or delete elements according to the privileges in your user profile. However, any element you create automatically belongs only to the primary organization configured in your user profile.

> [!NOTE]
> **Note**
> 
> Selecting multiple organizations to view their elements is not yet fully supported on all Securiti modules.

1. In Securiti, near the bottom of the left navigation bar, click your avatar and choose **Organizations**.
2. From the list of organizations, mark the checkbox for an organization from the menu as shown below.

If the Multiple Org Unit Selection feature is enabled for your tenant, you can mark checkboxes for multiple organizations, or mark the **Select All** checkbox to select all organizations.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-WWV4EJBN.png)
3. When you are done, click **Save and Refresh** to put your selection(s) into effect.

> [!NOTE]
> **Note**
> 
> You can also change your default organization as described in **Configuring basic profile information** section.

### Managing accessibility settings

Securiti allows you to enable the enhanced accessibility settings that ensure that the platform is usable by people of all abilities. It includes making the content perceivable and more operable. The key feature is enabling the color contrast settings that can be enabled using the Securiti platform.

1. Open the **Accessibility** tab under the user profile section.
2. Under the **Color Contrast** Settings, turn on the toggle to enable high contrast settings for enhanced visibility.
3. Click on **Apply Changes** to confirm and apply the settings across the platform.

![system-accessibility-settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-95f58008-509c-f1f6-97e7-d79767114fb7(5).png)
4. Click on the **Reset** button next to the Apply Changes button to reset the settings for this page.

### Accessibility settings via login page

You can also enable these settings on the **Login page** using the floating icon on the bottom right of the page.

![login-accessibility-settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f7bda2fb-530a-35b7-c238-0401202f2d6d(5).png)

### Managing your trusted devices

You use the Trusted Devices page to view and manage the devices you have marked as trusted. You mark such devices by marking the "Remember this device for 30 days" checkbox when you log in with an MFA or Authenticator code as shown below. For these devices, Securiti does not prompt you for an MFA or Authenticator code for 30 days. For more information about MFA, see [Securing your Securiti account with multi-factor authentication](/v1/docs/securiti-platform-securing-your-securiti-account-with-multi-factor-authentication).

![marking_trusted_device_login.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6a75b09d-6b91-1a8e-75fc-e22d0c73fffc(5).png)

To open the Trusted Devices page, near the lower left corner of your user profile page, in the Trusted Devices area, click **View all Devices**. The Trusted Devices page shows you a list of the trusted devices as shown below.

![trusted_devices_table.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7595c356-c2ef-655c-de29-0dfdedfd579a(5).png)

To remove a trusted device, at its right end choose **Options** (three dots) **> Remove**.

### Viewing and managing your user sessions

1. Near the lower left corner of your user profile page, in the Active Sessions area, click **View all Sessions**.
2. Use the tools on the User Sessions page to view and manage your sessions.
