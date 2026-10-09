---
title: "Creating an OCI Instance"
slug: "creating-an-oci-instance"
updated: 2026-07-16T07:09:12Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/creating-an-oci-instance"
stale: true
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Creating an OCI Instance

Creating an OCI instance is essential for automated asset discovery; including shadow assets and protection of your data across your cloud environment. By setting up and activating the instance, you ensure that Securiti has the necessary permissions to monitor, and manage the security posture, and apply privacy controls to the data within your OCI infrastructure.

### Prerequisites

- **OCI Prerequisites**

> [!NOTE]
> **Note**
> 
> OCI activation is supported via the one-click activation approach and currently not supported via downloadable terraform templates.
  - To activate an OCI instance, you must have the OCI Tenancy Administrator role permissions. Once permissions are confirmed, Securiti offers a one-click activation that connects to all compartments within your OCI tenancy.
- **Securiti Prerequisites**

| Purpose | Module(s) Required |
| --- | --- |
| Sensitive Data Scan | [Sensitive Data Intelligence](/v1/docs/using-sensitive-data-intelligence) |
| Posture Scan & Auto-remediation | [Security Posture Management](/v1/docs/using-security-posture-management) |
  - In Securiti, you must have the subscription to the following modules to integrate Securiti with OCI:

### One-click Activation

1. In Securiti, select the jewel icon and choose **Integrations** from the left navigation bar.
2. On the **Integrations** page, navigate to **IaaS Connectors**.
3. To create a new instance, click **Add IaaS Connectors** in the top-right corner of the page, and then select **Oracle Cloud Infrastructure**.
4. On the **Add Oracle Cloud Account** configurations page provide the following information:

![Form to add an Oracle Cloud account with various discovery options listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-22 at 12.42.21 PM.png)

| Parameter | Description |
| --- | --- |
| Connector Name | Provide a unique name for the connector. |
| Initiate asset discovery (default) | Find, identify, and catalog all assets such as virtual machines and databases. This option is pre-selected. |
| Initiate security posture scan | Mark this checkbox to let Securiti scan your OCI account for security vulnerabilities and identify misconfigurations (access controls, network settings, encryption protocols) in cloud infrastructure or resources. |
| Auto-remediate security posture violations | Mark this checkbox to let Securiti automatically remediate applicable OCI security vulnerabilities it finds. |
5. Click **Generate API Token**.
6. On the **Create Oracle Cloud Connector** pop-up, click **Continue**.

> [!NOTE]
> Note
> 
> The **Create Oracle Cloud Connector** pop-up informs you that a new connector will be created and after its creation you will be provided with the steps to authenticate it with your Oracle Cloud account.
7. You can copy the **Securiti API token**, **Connector ID**, and **OCI API Public Key** to use these values later while creating the stack.

> [!NOTE]
> Note
> 
> **OCI API Public Key** helps validate key integrity and reduces the risk of accepting unverified keys, thereby, strengthening the security of OCI connector authentication.
8. Click **Deploy to Oracle cloud**.
9. When prompted, log in to the OCI console using your tenancy administrator credentials.
10. After you log in, Oracle redirects you to the **Create Stack** page.
11. On the **Stack Information** tab, accept the Oracle terms of use, optionally name the stack, and choose the compartment to execute in. Then click **Next**.

![stack-info-tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d22f67c-bff4-0109-87bb-298ccab2ddff.png)

> [!NOTE]
> Note
> 
> - OCI asset discovery includes the root compartment along with child compartments, providing coverage of the full OCI environment. The root compartment appears in the list of discovered compartments and follows the same discovery schedule as other compartments.
> - Ensure that the package URL is accessible from the machine on which the OCI connector is being configured.
12. On the **Configure Variables** tab, paste the connector Id in the connector_id box and integration token in the **securiti_token** box, and public key in the **oci_api_public_key** that you copied earlier. Also, add an email in the **user_email** box. Oracle will set this email as the primary email for the OCI Identity User and use it to send account-related notifications.

Then click **Next** to start the stack deployment.

![Configuration settings for creating a stack in cloud infrastructure management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (4).png)

After the stack deploys, Securiti automatically starts asset discovery and populates the **Data Systems Overview** dashboard with them.

## Related

- [Performing Actions Post OCI Instance Creation](/performing-actions-post-oci-instance-creation.md)
- [Visualizing Results of Asset Discovery](/visualizing-results-of-oci-asset-discovery.md)
- [Roles & Permissions Required for OCI Integration](/roles-permissions-required-for-oci-integration.md)
