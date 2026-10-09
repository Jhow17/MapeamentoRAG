---
title: "Getting started with System Settings"
slug: "getting-started-with-system-settings-1"
updated: 2026-07-01T09:31:57Z
published: 2026-07-01T09:31:57Z
canonical: "helpcenter.securiti.ai/getting-started-with-system-settings-1"
area: geral
modulo: getting-started
tipo: guia
data_captura: 2026-10-08
---

# Getting started with System Settings

System Settings is a centralized component within the platform that allows administrators to configure and manage the security, access, and integration settings for the organization's use of the Securiti platform. It provides tools to ensure proper configuration of user roles, credentials, security measures, and access control.

As an administrator, you can set up critical infrastructure integrations, manage user authentication, and control access across multiple platforms. You can also configure private cloud storage, set IP restrictions, and manage sensitive credentials through a secure vault.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/System%20Settings-Design%202.drawio(1).svg)

### Step 1: Log in to the Securiti Platform

#### Method 1

Log into your Securiti platform using your username and password, simply enter your registered email address and password on the Securiti login page. If you forget your password, use the “Forgot Password” option to reset it and regain access to your account.

#### Method 2

For SSO access, select your organization’s SSO provider from options like Azure, Okta, ADFS, or OneLogin. You’ll be redirected to your organization's authentication page. Enter your credentials there, and once verified, you’ll be logged into the Securiti platform.

[Learn more](/latest/docs/system-settings-configuring-single-sign-on)

### Manage your Securiti profile settings

| In the User Profile Settings, you can personalize your account by uploading a profile picture. You can also configure or update your user password for enhanced security. Additionally, manage your trusted devices by reviewing and authorizing the devices that can access your account, ensuring greater control over account security and access. [Learn more](/latest/docs/securiti-platform-managing-your-securiti-user-profile) | ![Securiti-profile-settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f036d5af-4a16-882b-fe96-6b84c7550aa6(1).png) |
| --- | --- |

### Manage General Settings in Securiti Platform

| ![Securiti-general-settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7c206d74-acb0-bf1f-d7d8-9143f262488e(1).png) | In the General Settings, you can add secondary domains to extend your organization's reach. You can also specify admin and security contact emails and phone numbers to ensure proper notifications for critical issues. Additionally, configure concurrent login session limits to control the number of active sessions per user, enhancing security and managing access efficiently. [Learn more](/latest/docs/system-settings-configuring-securiti-general-settings) |
| --- | --- |

### Manage Accessibility Settings in Securiti Platform

| **User management actions** You can then create and edit user accounts as needed. Import multiple users at once via CSV for faster setup. Manage account statuses by activating or deactivating, or deleting users. Additionally, you can set up passwords for users and configure partner access, allowing external collaborators to access the platform securely. [Learn more](/latest/docs/configuring-access-management-managing-securiti-users) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-G23LXFJV.png) |
| --- | --- |
| **Managing and create roles** You can then efficiently create and manage user roles. You can view all available user roles and create fine-grained roles and permissions using Role-Based Access Control (RBAC). This helps ensure that each user has the correct permissions and access levels based on their role, letting you maintain a secure and organized access structure across the platform. [Learn more](/latest/docs/roles-in-securiti) | ![roles-settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1983b21-4cf1-0b73-fcf2-9ec99a850951(1).png) |
| **Configure single sign-on** To configure Single Sign-On (SSO), Securiti supports various providers, including Azure, Okta, ADFS, OneLogin, RedHat, and Generic SAML. Select your preferred SSO provider and allow users to log in seamlessly using their existing credentials, enhancing both convenience and security by centralizing access management. [Learn more](/latest/docs/system-settings-configuring-single-sign-on) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NKV3NFCD.png) |

### Manage Integration Settings in Securiti Platform

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7R3ZLXNL.png) | **Configure Private cloud storage** Securiti supports private cloud storage configurations for: - Azure - Min.io - AWS - GCP This allows you to securely manage your data within your chosen cloud environment. By integrating your private cloud storage, you can streamline data management while maintaining full control over your infrastructure. [Learn more](/latest/docs/system-settings-configuring-private-cloud-storage) |
| --- | --- |
| ![manage-credentials-vault.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc716393-7917-23f1-7665-3782119d635b(1).png) | **Manage Credentials** Securiti allows you to manage your credentials securely using various methods to ensure secure control of all access credentials. You can generate and manage API keys and SSH keys for secure access. Additionally, use the Keyring feature to store sensitive credentials and the Credentials Vault to safeguard and manage your organization’s authentication details. [Learn more](/latest/docs/managing-credentials-configuring-credential-vaults) |

### Manage Security Settings in Securiti Platform

| **Manage IP Restrictions** Enhance security by managing IP restrictions. You can specify trusted IP ranges or addresses, ensuring that only users accessing from approved networks can log into the platform. This helps prevent unauthorized access from unknown or untrusted locations. [Learn more](/latest/docs/configure-securiti-settings-configuring-ip-address-restrictions-and-masking) | ![ip-masking-settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a6e36675-ae0e-01ec-3026-f9dc3b697fa1(1).png) |
| --- | --- |
| **Audit Logging** Audit logging allows you to track changes, monitor user activity, and maintain transparency for compliance purposes.. Audit logs are crucial for both security management and regulatory compliance. [Learn more](/latest/docs/securiti-platform-viewing-the-securiti-audit-log) | ![audit-logging.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bb459334-ea7f-f12e-7ca4-4faddee9097f(1).png) |
| **Support Access for troubleshooting** Securiti allows administrators to grant temporary support access to Securiti's support team for troubleshooting purposes. You can specify the access level and duration, ensuring that support is provided efficiently while safeguarding your organization’s sensitive data and operations. [Learn more](/latest/docs/system-settings-configuring-securiti-support-access) | ![support-access-settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-46d76601-5bbc-6f26-58c6-7036596eaec5(1).png) |

### System Settings API documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The system settings API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| [Embedded content](https://player.vimeo.com/video/1012313059) | **Run APIs directly from the docs** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without setting up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/system-settings/apidocs/index.html) |
| --- | --- |
| ![postman-get-session-api-call.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4c4b43b4-4812-17a2-4e5c-3df13ca75bcc(1).png) | **Download the postman collection** We also provide postman collection for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that let you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/system-settings/apidocs/index.html) |

## Related

- [Configuring single sign-on](/system-settings-configuring-single-sign-on.md)
- [Configuring private cloud storage](/system-settings-configuring-private-cloud-storage.md)
- [Configuring the Securiti self-service portal](/configuring-the-securiti-self-service-portal.md)
