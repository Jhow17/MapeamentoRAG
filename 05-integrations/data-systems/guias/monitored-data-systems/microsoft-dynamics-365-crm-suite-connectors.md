---
title: "Microsoft Dynamics 365 CRM (Suite)"
slug: "microsoft-dynamics-365-crm-suite-connectors"
status: "new"
updated: 2026-07-30T06:44:41Z
published: 2026-07-30T06:44:53Z
canonical: "helpcenter.securiti.ai/microsoft-dynamics-365-crm-suite-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft Dynamics 365 CRM (Suite)

The Microsoft Dynamics CRM platform is part of the Microsoft Dynamics 365 suite. It provides sales, marketing and service management support for enterprises. It enables organizations to manage customer interactions, automate sales pipelines, run targeted marketing campaigns, and deliver consistent service experiences. All this is achieved from a unified platform that integrates seamlessly with Microsoft 365, Azure, and Power Platform.

The Microsoft Dynamics CRM connector lets you integrate with Securiti to discover and govern structured customer and engagement data stored across your sales, marketing, and service modules.

Microsoft Dynamics 365 CRM (Suite), both Self-hosted and Securiti Cloud connectors, fall under the category of monitored, structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Microsoft Dynamics 365 CRM Suite (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence (Discovery scan) - DSR Automation using SQL queries - Breach Analysis - Workflow |
| Microsoft Dynamics 365 CRM Suite (Securiti Cloud) | Securiti Cloud connector supports: - DSR Automation using SQL queries - Breach Analysis - Workflow |

### Supported pod types for self-hosted connector

- Standard Securiti Pods.

### Supported authentication methods

- For Self-hosted connector:
  - Microsoft Dynamics 365 CRM Suite application-based authentication
    - OAuth-based authentication for APIs.
- For Securiti Cloud connector:
  - Microsoft Dynamics 365 CRM Suite application-based authentication
    - OAuth-based authentication for APIs.

### Supported keyring for Microsoft Dynamics 365 CRM Suite (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**. For more information, see [Configuring HashiCorp vault instance in Securiti](/latest/docs/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti).

### Supported items for classification scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Groups
- Users
- Folders
- Files

### Prerequisites for configuring Microsoft Dynamics 365 CRM Suite connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Microsoft Dynamics 365 CRM Suite with a Self-hosted connector. For more information on configuring pods, see [Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must have admin access to Microsoft Dynamics CRM, Power Platform, and Microsoft Entra ID for configuring security roles, users, and generating API permissions.

For more information, see [Acquire authentication credentials in Microsoft Dynamics 365 CRM Suite (Self-hosted)](/latest/docs/acquire-authentication-credentials-in-microsoft-dynamics-365-crm-self-hosted) and [Acquire authentication credentials in Microsoft Dynamics 365 CRM Suite (Securiti Cloud)](/latest/docs/acquire-authentication-credentials-in-microsoft-dynamics-365-crm-securiti-cloud).

> [!WARNING]
> **Important**
> 
> You must have the Basic User role in the Microsoft Dynamics 365 CRM Suite account and an Application Administrator role in Azure before proceeding with the Connector Activation.

#### 3. Allowlisting URLs for discovery scan with Microsoft Dynamics 365 CRM Suite (Self-hosted)

> [!NOTE]
> **Note**
> 
> You must allowlist the following URLs on your firewall for Microsoft Dynamics 365 CRM (Suite) to ensure proper functionality of Sensitive data Intelligence (SDI) and Data Subject Rights (DSR) to work as expected:
> 
> - [https://graph.microsoft.com](https://graph.microsoft.com)
> - [https://login.microsoftonline.com](https://login.microsoftonline.com)
> 
> You need to allowlist the following URLs depending on the selection of your region in the Cloud menu on the Connector Activation screen.
> 
> | Cloud | URL |
> | --- | --- |
> | North America | https://{{account}}.crm.dynamics.com/ |
> | South America (LATAM/SAM) | https://{{account}}.crm2.dynamics.com/ |
> | Canada (CAN) | https://{{account}}.crm3.dynamics.com/ |
> | Europe, Middle East, Africa (EMEA) | https://{{account}}.crm4.dynamics.com/ |
> | Asia Pacific (APAC) | https://{{account}}.crm5.dynamics.com/ |
> | Oceania (OCE) | https://{{account}}.crm6.dynamics.com/ |
> | Japan (JPN) | https://{{account}}.crm7.dynamics.com/ |
> | India (IND) | https://{{account}}.crm8.dynamics.com/ |
> | United States of America Government | https://{{account}}.crm9.dynamics.com/ |
> | United Kingdom (UK) | https://{{account}}.crm11.dynamics.com/ |
> | France (FRA) | https://{{account}}.crm12.dynamics.com/ |

#### 4. Use cases and permissions for Microsoft Dynamics 365 CRM Suite

This table covers use cases and permissions required for Microsoft Dynamics 365 CRM Suite Self-hosted and Securiti Cloud connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Sensitive Data Intelligence (SDI) | SDI Discovery Scans is only available on the self-hosted connector. | - **Microsoft Dynamics CRM Admin Access:** - Account Domain - **Microsoft Graph API Application Permissions:** - For self-hosted connector: [User.Read](https://learn.microsoft.com/en-us/graph/permissions-reference#userread) - For cloud connector: [User.Read](https://learn.microsoft.com/en-us/graph/permissions-reference#userread) - **Self-hosted connector only. Power Platform admin center access to:** - Create basic user - Custom security role - Assign permissions to Read | These permissions let Securiti read the users and their metadata for classification purposes and to build the Personal Data Index for DSR Automation. |
| Data Subject Request (DSR) | N/A | These permissions lets Securiti read all of the data within your Microsoft Dynamics 365 CRM Suite instance for DSR searches. |

### Connect Microsoft Dynamics 365 CRM Suite connectors with Securiti

#### Steps to connect Microsoft Dynamics 365 CRM Suite (Self-hosted) connector with Securiti

To configure the Microsoft Dynamics 365 CRM Suite (Self-hosted) connector, perform the procedures in the following topics:

1. [Obtain the account domain for your Microsoft Dynamics 365 CRM Suite (Self-hosted) account](/latest/docs/obtain-the-account-domain-for-your-microsoft-dynamics-365-crm-suite-self-hosted).
2. [Assigning security roles in Microsoft Dynamics 365 CRM Suite (Self-hosted)](/latest/docs/assigning-security-roles-in-microsoft-dynamics-365-crm-suite-self-hosted).
3. [Acquire authentication credentials in Microsoft Dynamics 365 CRM Suite (Self-hosted)](/latest/docs/acquire-authentication-credentials-in-microsoft-dynamics-365-crm-self-hosted).
4. [Configure the user in the Power Platform app for Self-hosted connector](/latest/docs/configure-the-user-in-the-power-platform-app).
5. [Connect Microsoft Dynamics 365 CRM Suite (Self-hosted) connector with Securiti](/latest/docs/connect-microsoft-dynamics-365-crm-suite-self-hosted-with-securiti).
6. [Configure discovery scans in Microsoft Dynamics 365 CRM Suite (Self-hosted)](/latest/docs/configure-discovery-scans-in-microsoft-dynamics-365-crm-suite-self-hosted).

#### Additional resources

- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
- [Fulfilling DSR requests for Microsoft Dynamics 365 CRM Suite (Self-hosted)](/latest/docs/fulfilling-dsr-requests-for-microsoft-dynamics-365-crm-suite-self-hosted).

#### Steps to connect Microsoft Dynamics 365 CRM Suite (Securiti Cloud) connector with Securiti

To configure the Microsoft Dynamics 365 CRM Suite (Securiti Cloud) connector, perform the procedures in the following topics:

1. [Obtain the account domain for your Microsoft Dynamics 365 CRM Suite (Securiti Cloud)](/latest/docs/obtain-account-domain-microsoft-dynamics-365-crm-suite-securiti-cloud).
2. [Assigning security roles in Microsoft Dynamics 365 CRM Suite (Securiti Cloud)](/latest/docs/assigning-security-roles-in-microsoft-dynamics-365-crm-suite-securiti-cloud).
3. [Acquire authentication credentials in Microsoft Dynamics 365 CRM Suite (Securiti Cloud)](/latest/docs/acquire-authentication-credentials-in-microsoft-dynamics-365-crm-securiti-cloud).
4. [Connect Microsoft Dynamics 365 CRM Suite (Securiti Cloud) connector with Securiti](/latest/docs/connect-microsoft-dynamics-365-crm-suite-securiti-cloud-connector-with-securiti).
5. [Initiate Microsoft Dynamics 365 CRM Suite (Securiti Cloud) data scanning](/latest/docs/initiate-microsoft-dynamics-365-crm-suite-securiti-cloud-data-scanning).

#### Additional resources

- [Fulfilling DSR requests for Microsoft Dynamics 365 CRM Suite (Securiti Cloud)](/latest/docs/fulfilling-dsr-requests-for-microsoft-dynamics-365-crm-suite-securiti-cloud).

Self-hosted systems refer to computer systems or software applications that are hosted and operated by organizations or individuals who use them, rather than being hosted and operated by service providers or third parties. It becomes the responsibility of the organization to host, maintain, and manage the system or software.

Securiti’s sensitive data scanning feature which lets you target specific locations by looking for specific data elements, on specific schedules and by specific owners. These settings are configured when creating a discovery scan for a data system. Discovery scan is used when a data system containing sensitive information is shared by multiple teams. Each user can create a scan job for the portion of the data system they manage. See Understanding discovery scans for more information.
