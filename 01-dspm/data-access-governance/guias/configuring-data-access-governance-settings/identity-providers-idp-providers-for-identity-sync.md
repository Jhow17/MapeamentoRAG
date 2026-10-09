---
title: "Identity Providers"
slug: "identity-providers-idp-providers-for-identity-sync"
updated: 2026-09-02T12:31:17Z
published: 2026-09-02T12:31:17Z
canonical: "helpcenter.securiti.ai/identity-providers-idp-providers-for-identity-sync"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Identity Providers

This topic lists the supported identity providers for synchronizing identities in the Data Access Governance module and describes the configuration process for each provider. Synchronization lets you view the Principals (users, user groups, etc.) who have been provisioned access through identity providers. You can also visualize the relationship between local data system users and those granted access via identity providers such as Active Directory. This helps you understand how access is provisioned across multiple identity sources in your data environment.

The following are the supported identity providers:

- Active Directory

### Configuring Active Directory Server

Active Directory Synchronization, either on-demand or periodic, fetches users and groups from the configured AD server and makes them available in the Securiti Data Command Graph.

To configure an Active Directory Server:

1. In Securiti, at the top left corner, click the **Jewel** icon, then choose **Settings> Data Access Governance> Identity Providers**.
2. On the **Identity Providers** page, click **+Add New Server**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 4(9).png)
3. On the **Add New Server** page, configure the following settings:

| Settings | Name | Description |
| --- | --- | --- |
| Basic Settings | Appliance Type | Specify if the Active Directory operates from a Cloud environment or an On-Premises setup. If it is On-Premises, you will have to select the specific Pod in the **Appliance** menu where the connector will be executed. |
| Name | Enter a unique name for the AD Server. For example *ad-securiti-prod* |
| AD User | Email address for the AD User account. This is the user account that you use to log in to Windows AD Server. For example *Administrator@securiti.local*. *@securiti.local* is the domain name. > [!NOTE] > Note > > The AD User account must have read access to Users, Groups, and their attributes. It is recommended to use a dedicated service account rather than a Domain Admin account. A service account with read-only permissions is sufficient for synchronisation and follows the principle of least privilege. |
| Password | Enter the password for AD User account. |
| Confirm Password | Enter the password again to confirm your password. |
| Server:Port | Server and port address. If SSL is not enabled, enter the IP of the Server:389 (11.111.111.11:389). If SSL is enabled, enter the IP of the Server:636 (11.111.111.11:636) > [!NOTE] > **Note** > > For new Active Directory servers deployed post-2025, SSL/TLS is mandatory. These servers require LDAPS (port : 636) and will not allow unsecured LDAP connections. |
| SSL enable | Mark the **SSL enable** to secure communication between applications across a network. To export an existing LDAP SSL certificate: - On your Windows AD machine, press **Windows Key + R** to open the Run dialog. - Type **mmc** and press **Enter**. This opens Microsoft Management Console (MMC). - Click **File > Add/Remove Snap-in...**. - From the list of snap-ins, select **Certificates**, then click **Add>.**. - Choose **Computer account**, click **Next**, select **Local computer**, and then click **Finish**. - Click **OK** to return to the main MMC window. **Locating the Certificate:** - In the left pane, expand **Certificates (Local Computer)**. - Navigate to **Personal > Certificates**. - Locate the certificate that was issued to your server for LDAPS. - It should have the server’s **fully qualified domain name (FQDN)** as the Subject. - Ensure that **Server Authentication** is listed under its intended purposes. **Exporting the Certificate:** - Right-click on the certificate, select All **Tasks>Export...**. - The **Certificate Export Wizard** will open. - Click **Next** on the welcome screen. **Choose Export Format:** - On the **Export File Format** page, select **Base-64 encoded X.509 (.CER)**. - Click **Next**, choose a file name and location, and click **Finish**. Click the **Upload Document** to upload the certificate from your device. Supported file formats are `.cer` and `.pem`. > [!NOTE] > Note > > If your Active Directory server is deployed on AWS and accessed using LDAPS (port 636), proper DNS resolution of the Active Directory host is required. > > In AWS environments, this is commonly achieved by configuring a **Private Hosted Zone in Amazon Route 53** that maps the AD server’s hostname to its private IP address. > > Refer to **Route 53 Setup for LDAPS (Optional – AWS Only)** below for step-by-step instructions. #### Route 53 Setup for LDAPS (AWS Only) > [!NOTE] > This section applies **only** when Active Directory is hosted on AWS and LDAPS (SSL/TLS on port 636) is enabled. **Purpose** This setup ensures that the Active Directory server’s hostname can be resolved privately within the VPC, which is required for secure LDAP (LDAPS) connections. --- #### Step 1: Navigate to Route 53 1. Log in to the AWS Console: [https://console.aws.amazon.com](https://console.aws.amazon.com) 2. In the top search bar, type **Route 53** 3. Click **Route 53** --- #### Step 2: Create a Private Hosted Zone 1. In the left sidebar, click **Hosted zones** 2. Click **Create hosted zone** 3. Enter the following: - **Domain name:** `IAMAD.LOCAL` - **Description:** Active Directory DNS for LDAPS (optional) - **Type:** Private hosted zone - **VPC Association:** - Region: Select your region (e.g., `us-east-1`) - VPC ID: Select the VPC where your appliance or Kubernetes cluster is deployed 4. Click **Create hosted zone** --- #### Step 3: Create an A Record 1. Click the hosted zone **IAMAD.LOCAL** 2. Click **Create record** 3. Configure: - **Record name:** `EC2AMAZ-J0MRT24` (auto-appends `.IAMAD.LOCAL`) - **Record type:** A – IPv4 address - **Value:** `172.31.24.69` (AD server private IP) - **TTL:** 300 - **Routing policy:** Simple 4. Click **Create records** --- #### Step 4: Verify VPC DNS Settings 1. Go to **VPC** service 2. Select **Your VPCs** 3. Click the VPC used above 4. Ensure: - DNS resolution: **Enabled** - DNS hostnames: **Enabled** 5. If disabled, go to **Actions → Edit VPC settings**, enable both, and save. --- #### Step 5: Verify Hosted Zone Records You should see: - NS record (auto-created) - SOA record (auto-created) - A record mapping the AD hostname to the private IP --- #### Step 6: Test DNS Resolution From an EC2 instance in the same VPC: ```plaintext nslookup EC2AMAZ-J0MRT24.IAMAD.LOCAL ``` ` `Successful resolution confirms DNS is correctly configured. --- #### Step 7: Trigger Active Directory Sync Once DNS resolution is verified, return to the Securiti platform and run **Verify Connection** or initiate **Sync** for the Active Directory server. |
| Base Distinguished Name | Base distinguished name for example: `dc=securiti,dc=local`. |
| Verify Connection | Click the **Verify Connection** button to check the status of integration. Note that **Verify Connection** option is not currently supported for On-Premise AD Servers. |
| Configure User Ingestion | All Enabled Users | Ingest all enabled users from the Active Directory server. |
| Users from Groups | Ingest only users that belong to specific AD groups. You can specify this by using a filter of Group Name. |
| Users with Attributes | Ingest users that match specific attribute-based criteria defined in Active Directory. Use the field below to define the Active Directory filter. **Example:** (& (objectClass=user)(department=Finance)). Select this option when you want to ingest only those users who match specific **Active Directory attributes** stored in your Active Directory. This is helpful when you **do not want** to **ingest all users** or **entire groups** but i**nstead want to target users** who **share common characteristics**, such as department, location, title, object class, or any other attribute available in your AD schema. In this example stated above, department is an attribute for users and Finance is the value stored in that attribute out of many others. This lets you get all users who are present in the Finance department. |
| Configure Security Group Ingestion | All Security Groups | Ingest all security groups from the Active Directory server. |
| Groups with Attributes | Ingest only groups and users that meet defined attribute-based criteria. Enter Active Directory filter criteria to match specific AD groups. **Example:** (&(objectClass=group)(title=Finance)) |
| Additional Settings | Enable Auto Sync | Enable the toggle to automatically synchronize users and groups based on a set interval. Choose the desired **sync frequency** (e.g., Hourly, Daily, Weekly). |

You can now expand the **Metadata Explorer panel (⛶)** to a larger view for easier reading and navigation of metadata details.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 5(6).png)
