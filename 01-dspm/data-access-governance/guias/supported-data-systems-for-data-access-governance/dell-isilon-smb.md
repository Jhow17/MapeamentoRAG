---
title: "SMB - Dell Isilon"
slug: "dell-isilon-smb"
updated: 2026-08-31T06:06:12Z
published: 2026-08-31T06:06:12Z
canonical: "helpcenter.securiti.ai/dell-isilon-smb"
stale: true
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# SMB - Dell Isilon

This section describes the Data Access Governance features supported for SMB Shares hosted on Dell Isilon SMB storage and outlines the steps to configure these capabilities.

### Supported Data Access Governance Feature Sets

The following features are supported for Dell Isilon SMB:

#### Access Intelligence

- Privilege Analysis - Privilege Analysis is supported for Self-Hosted SMB Connectors.

- File level Permissions granularity

- Activity Analysis - Not Supported

##### Access Control

- Not supported

##### Cross Border Transfer Policies

- Not supported

> [!NOTE]
> Note
> 
> If Data Access Governance features for Dell Isilon SMB are not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

## Example Supported Use Cases

The supported example use cases include:

Access Intelligence

- Identify and report on which Isilon users have access to specific Files and what their permissions are on those Files.
- Identify and report on which Isilon users have access to Files containing sensitive data elements.
- Identify and report users assigned to a specific User Group that have access to Files.
- Identify users with direct access and group-based access to Shares.
- Map local user accounts on Isilon back to Active Directory identities ingested through AD sync.

## Configuring Dell Isilon SMB Data Access Governance

To see the Dell Isilon SMB access intelligence data (Privilege Analysis), there are some prerequisite steps.

**Configuring** **Access Intelligence (****Privilege Analysis)**

#### Prerequisites

Ensure the following requirements are met before configuring the Isilon SMB connector.

  

### SMB Share Availability

Ensure that SMB shares are already created on the Dell Isilon SMB cluster and are accessible from the Securiti pod.

### Active Directory Integration

If you are using an Active Directory user account for authentication, ensure that:

- The Isilon cluster is joined to the Active Directory Domain.
- The user used for the connector has access to the SMB share.

1. ### Permissions

The user account you use for activating the SMB connector must have the following permissions:

| Permission Level | Permission |
| --- | --- |
| Share | Read |

> [!NOTE]
> Note
> 
> The SMB share must explicitly grant access to the Active Directory user (or a group that the user belongs to). If the user does not have access to the share, the collector will not be able to retrieve file metadata or permissions.

> [!NOTE]
> Note
> 
> The following ports are required :
> 
> - **443 (HTTPS)** – Required for PowerScale REST API (PAPI) communication (user/group metadata).
> - **445 (SMB)** – Required for SMB file system access and permission evaluation

#### Setting up API permissions and roles

Privilege Analysis for Dell Isilon SMB requires the user account configured in the IAM Metadata Source to have access to the **PowerScale Platform API (PAPI)**. Specifically, the user account provided in the Access Scan related configuration must have read access to the following Isilon Platform API endpoints.

| API Endpoint | Purpose |
| --- | --- |
| /platform/1/cluster/config | Fetches cluster configuration to determine the API version |
| /platform/{version}/auth/users | Fetches local SMB users |
| /platform/{version}/auth/groups?zone=System | Fetches local SMB groups |
| /platform/{version}/auth/groups/{group_name}/members?zone=System | Fetches members for a specific local SMB group |

This access is used by Securiti to retrieve identity metadata such as users, groups, and Active Directory domain information from the Isilon cluster. Access to the APIs translates to the following privileges in the Isilon cluster:

- ISI_PRIV_AUTH
- ISI_PRIV_AUTH_USERS
- ISI_PRIV_AUTH_GROUPS
- ISI_PRIV_LOGIN_PAPI

You can grant this access using one of the following options.

#### Option 1: Grant user access to the PAPI API through SystemAdmin role

Assign the user whose credentials will be provided in the Access Scan related configuration to the built-in **SystemAdmin** role. This role provides access to the PAPI, in addition to other privileges. This is a quick way to provide necessary privileges.

Note that the role provides broad access to privileges on your Isilon system, therefore please evaluate whether this is appropriate under your company's best practices before choosing this approach.

Run the following command on the Isilon CLI:

```plaintext
isi auth roles modify SystemAdmin --add-user "<domain>\\<username>"
```

Example:

```plaintext
isi auth roles modify SystemAdmin --add-user "example.company.com\\jane.doe"
```

#### **Option 2: Create a dedicated API role (Recommended)**

You can create a custom role that provides **read-only API** access required for Privilege Analysis. This role is then assigned to the user, whose credentials will be provided in the Access Scan related configuration. This is the recommended approach, as it adheres to the Principle of Least Privilege.

Note that the example below uses **AuthQueryRole** as the role name. You may pick a name that suits your company's established naming practices.

1. **Create a new role ('AuthQueryRole') for API access:**

```plaintext
isi auth roles create AuthQueryRole --description "Allows read access to auth users/groups via PAPI"
```

1. **Grant the required privileges:**

Assign the parent privilege:

```plaintext
isi auth roles modify AuthQueryRole --add-priv-read=ISI_PRIV_AUTH
```

Assign child privileges:

```plaintext
isi auth roles modify AuthQueryRole --add-priv-read=ISI_PRIV_AUTH_GROUPS

isi auth roles modify AuthQueryRole --add-priv-read=ISI_PRIV_AUTH_USERS
```

Allow API Login:

```plaintext
isi auth roles modify AuthQueryRole --add-priv-read=ISI_PRIV_LOGIN_PAPI
```

1. **Assign your AD user to this new role**

```plaintext
isi auth roles modify AuthQueryRole --add-user "<domain>\\<username>"
```

Example:

```plaintext
isi auth roles modify AuthQueryRole --add-user "example.company.com\\jane.doe"
```

For more information, see [Dell Isilon documentation](https://infohub.delltechnologies.com/en-us/l/dell-powerscale-administrative-security-with-multi-party-authorization/overview-7816/)

1. ### **Pod Configuration and Deployment**

You must configure and deploy a Securiti pod in your environment to connect your Isilon server with a Self-Hosted SMB Connector.

Make sure the pod deployment has appropriate reachability through firewalls and network routing to reach:

- The Isilon SMB endpoint (port 445)
- The Isilon management/PAPI endpoint (port 443)

For more information, see [Pod Installation](/v1/docs/pod-installation-cluster-version-v128).

1. ### Configure Private Cloud Storage (Optional)

Securiti lets you store Identity and Access Management (IAM) metadata of your data systems, extracted using Access Scan Definitions (ASDs), in your Private Cloud Storage.

If you have not configured Private Cloud Storage for your tenant, the IAM metadata is stored in Securiti’s cloud storage. For more information, see [Configuring Private Cloud Storage](/latest/docs/system-settings-configuring-private-cloud-storage).

1. ### Configure and activate the Isilon Self-Hosted SMB Connector

Securiti uses the SMB Share information specified during connector configuration to determine the scope of Access Scans:

When configuring the connector, ensure that:
  - If you configure the connector without specifying any Share names, Securiti scans all shares hosted on the Isilon server.
  - If you specify one or more shares, Securiti scans only those shares.
  - The Securiti pod has network reachability to the Isilon SMB endpoint.
  - The credentials used have read-level access to the Shares and NTFS permissions being scanned. For more detailed setup steps and configuration parameters, refer to the [SMB Connector](/v1/docs/smb-connectors) documentation.
2. ### Perform Inventory Sync and Discovery Scan

For your Dell Isilon SMB instance, perform:

- **Data Inventory Sync** Data Inventory Sync reads file metadata and makes files available in the Data Command Graph.

OR

- Discovery Scan Discovery Scan detects sensitive/personal data stored within SMB Shares.

> [!NOTE]
> Note
> 
> **Data Inventory Sync:** Reads metadata from Files and unstructured data resources and makes them available in the graph. In conjunction with an access-scan on the data-system(s), it can show access permissions that principals have on those Files and data resources.
> 
> **Discovery Scan:** Detects sensitive or personal data associated with data resources. In conjunction with an access scan on the data-system(s), it shows which users can access specific sensitive data elements.

1. ### Configure an Active Directory Server (Optional)

[Configure an Active Directory (AD) Server](/latest/docs/identity-providers-idp-providers-for-identity-sync) to synchronize users and groups into the Data Command Graph. Ensure that the AD configured in Securiti is the same AD server used by the Dell Isilon SMB environment.

When you run a Dell Isilon SMB Access Scan, Securiti discovers users and groups referenced in access control entries:

- If AD is not configured or synced, users and groups are ingested as shell principals and group membership edges are not created.
- If AD is configured and synced, Securiti links principals to corresponding AD identities by matching SIDs and creates direct user-to-group membership relationships.
- If an Access Scan is run before an AD Sync, access mappings may not reflect the current state if users or groups were added, deleted, or modified in Active Directory during that time.
- Any subsequent **AD Sync or Dell Isilon SMB Access Scan triggers re-analysis** to keep the Data Command Graph up to date. Changes to data or access permissions are reflected only after the relevant scan or sync is executed.

> [!NOTE]
> Note
> 
> - Nested group memberships are currently not supported. Only direct user-to-group memberships from Active Directory are ingested and represented in the **Data Command Graph**.
> - To accurately analyze group-based access paths, sync Active Directory and then re-run the Access Scan.

1. ### Configure IAM Metadata Source

To configure an IAM Metadata Source:

- In Securiti, open Data Access Governance, from the left menu bar, click Settings.
- Click IAM Metadata Sources. This opens the IAM Metadata Sources page.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1783391201867.png) Near the upper right corner of the page, click +New IAM Metadata Source.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1783391201870.png)

On the New IAM Metadata Source popup:

1. Enter the Connection Name. Example: Isilon Metadata Source
2. Select Isilon in Source Type. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(20).png)
3. Select the Pod Name from the dropdown menu.
4. Enter the Host (Isilon management IP/FQDN).
5. Select Basic in Authentication Type.
6. Enter Username and Password. If using an Active Directory user, include the AD domain. Example: Administrator@svmad.local
7. (Optional) Enable **Disable TLS Verification** only if required for non-trusted certificates. Click **Create New IAM Metadata Source**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(5).png)
8. ### Configure an Access Scan Definition

To configure an Access Scan Definition:

1. In Securiti, open Data Access Governance, then choose Settings > Access Scan Definitions.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(13).png)
2. Near the upper right corner, click + New Access Scan Definition. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(11).png)

On the New Access Scan Definition popup:

1. Enter the Name. Example: SMB-Isilon
2. Select Isilon in Data System.
3. Enter the Host (IP/FQDN of your Isilon SMB endpoint).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(22).png)
4. In Source of Credentials and Connectivity for Access Intelligence Scans, select IAM Metadata Source.
5. In Metadata Sources, select the configured metadata source. Example: Isilon-MDS
6. In Associated Connectors, select the SMB connector instance.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled%202(10).png)
7. (Optional) In Identity Providers, select the Active Directory Server Instance if you want identity mapping.
8. (Optional) In **Scan Configuration**, enable automatic access scans and configure exclusion windows. Click **Add Definition** to create the Access Scan Definition.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(6).png)
9. ### Perform an Access Scan

On the Access Scan Definition page:

- Activate the Access Scan Definition that you created by enabling the toggle.
- Click the three dots option, and select Scan Now.

## Using Access Intelligence with Dell Isilon SMB

Below are example use cases to familiarize you with how to leverage the Data Command Graph to identify access and risk in your Dell Isilon SMB environment using Securiti’s Privilege Analysis feature.

When you filter in the Data Command Graph, all of the associated tables update with your filtered results.

Identifying Users assigned to a specific User Group that have access to Files using the Access Graph Explorer

This use case requires Active Directory integration.

1. Open Access Graph Explorer.
2. Click + to open the filter menu and select the User Group Principal entity.
3. Click the three dots next to User Group Principal, select Add Relationship → User Principal.
4. Click the three dots next to User Principal, select + Add Property → Provider Type = SMBIsilon.
5. Click the three dots next to User Principal, select Add Relationship → Resource Access.
6. Click the three dots next to Resource Access, select Add Relationship → Files.
7. Click the three dots next to Files, select + Add Property → Data System Type = SMB.
8. Click Run Query.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(9).png)

Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [Reporting Dashboard Documentation](/latest/docs/getting-started-with-graph-reporting-dashboards).

Access Intelligence is the insight into the users’ access to applications and data. This includes permissions and activity perfromed on data sources.

Privilege Analysis is a feature set of DAG Access Intelligence which ingests the Identity and Access Management (IAM) and Role Based Access Control (RBAC) metadata within your data systems and presents the data through a normalized knowledge graph allowing you to quickly identify who can access sensitive data, how that access is created, and who can administer that access within a data system.

Permissions refer to the minimum set of access details required to connect a data system with Securiti and allow scanning of data. Permissions could be of an administrative role where the user has all privileges to scan, share and access data, or it can be READ/WRITE only. Without the required permissions, data cannot be discovered or scanned for sensitive information.

Domain is a logical or thematic grouping of related data assets. Domains are used to categorize and organize data assets based on their subject matter or the business context they belong to. For example, you might have a Finance domain that includes data related to financial transactions, reports, and analysis, or a Human Resources domain that encompasses data related to employee information, payroll, and HR processes.
