---
title: "Acquire authentication credentials in SMB"
slug: "acquire-authentication-credentials-in-smb"
updated: 2026-08-31T21:00:01Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-smb"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in SMB

1. Log in to the server running SMB.

> [!NOTE]
> **Note**
> 
> - Securiti assumes Samba is installed before you activate the connector.
> - Ensure you are running TCP port 445 to enable mounting for the SMB connector.
> - For existing SMBv1 connector activations, enable `8dot3` to retrieve the file creation date. This doesn't apply to new activations, which no longer support SMBv1.
  - **User** Credentials are your Windows user and password.
  - Your **host** is the server IP/address.
  - The **domain** is an optional parameter. It applies to the following scenarios:
    - (Mandatory) For SMB shares hosted on a Windows system with Active Directory Integration, it is required to provide the network domain. Failure to do so may result in a Discovery scan error if it is configured to fetch the file owner.

Use the command below to acquire domain name for your current Active Directory (AD) user.

```plaintext
echo %USERDOMAIN%
```
    - (Optional) SMB shares hosted on a Windows system without Active Directory Integration are not required to provide the network domain.
    - (Optional) The domain is not required for SMB shares hosted on MAC/Linux systems.
2. Obtain the path as follows:
  1. Open **Windows PowerShell**.
  2. Issue the **<*Get-SmbShare*>** command as shown below.

![SMB-share-path.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be088a12-4f92-f0eb-e878-3149ac968dcd.png)
3. Record the path info to use later.
4. Obtain the SMB Protocol **version** as follows:

> [!NOTE]
> **Note**
> 
> Use this to confirm the version of an existing SMB server. If you're activating a new SMB connector, skip the SMBv1 check below. Securiti no longer supports SMBv1 for new activations as of release 1.150.
  1. For SMB1 on Windows Machines:
    1. **<*Get-WindowsFeature FS-SMB1*>**
    2. **<*Get-SmbServerConfiguration | select EnableSMB1Protocol*>**

![SMB-version-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-82fcba9a-24cb-6ebc-f56c-be088c9bcc09.png)

If ‘Install State’ in the output of "command 1" says 'installed’ and the output of "command 2" says true, that means "protocol 1" is enabled, and the version is 1.0.
  2. For SMB2 on Windows Machines:

**<*Get-SmbServerConfiguration | select EnableSMB2Protocol*>**

![SMB-version-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae5c131d-686f-2048-072d-86f08adaf3a4.png)

If the above command returns true, that means SMB2 is enabled, and the version is 2.0.
  3. For Linux-based systems, run the **<*sudo smbstatus*>** command on the server, as shown below.

![SMB_Linux_command.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea6fda1-8622-7e53-9d73-0fc117874fc5.png)

> [!NOTE]
> **Note**
> 
> In the above example, SMB3_02 under Protocol Version represents SMB version 3. Similarly, SMB2_02 and SMB1_02 represent SMB versions 2 and 1, respectively.
> 
> For MACOS, the default version is 3.0
5. Record the correct version number to use later.
6. Following Permissions are required for SMB Data system instances. The below procedures cover the steps to assign Permissions in Windows and Mac servers.

| Permission | Use case |
| --- | --- |
| List shares | The permission is required to discover network shares. It is necessary in case you are activating the Connector with “/” as a shared path. |
| Read | The permission is required to scan an SMB share. |
| Read and Write | The read and write Permissions are required on both the source share and the quarantine share if quarantine policy is being used. |

To assign Permissions on **Windows SMB server**:

To assign Permissions on **Mac SMB Server**:

To assign Permissions required for **Ubuntu SMB Server**:

> [!NOTE]
> **Note**
> 
> Permissions for a Ubuntu SMB server are derived from the smb Configuration file, located at /etc/samba/smb.conf.

See the Table below for Permissions and their use cases for Ubuntu SMB Server.

| Permission settings in Ubuntu server | Use Case |
| --- | --- |
| To mark a share for discovery or listing, set **browseable = yes** for the specific share. > [!NOTE] > **Note** > > If **browsable=no**, the share cannot be discovered with the user Credentials, even if the user has access to it. | Listing shares |
| The relevant user must be added to **valid users** list. | Reading shares (Downloading/Scanning) |
| Either **read only = no OR writable = yes** must be set on both source and destination shares | Modifying files (Quarantine) |
  1. Right click on the share and select **Properties**.

![smb_windows1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a6f5a9ab-6109-b525-c514-44812df62e9e.png)
  2. Select **Sharing** tab and click **Share**.

![smb_windows2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16006ea8-fbe8-8385-1391-6eaacfdcf159.png)
  3. Select the user and permission level. Following Permissions are required as least privileges.

![smb_windows3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f0d3af84-1755-6b27-db81-40b76e2d6a6e.png)

> [!NOTE]
> **Note**
> 
> No permission is required for listing of shares as anyone with access to the smb server, can list the shares.
    - **Read**: Read access is required for scanning (listing or downloading) for a share.
    - **Read/Write**: Required for both source and quarantine shares.
  1. Go to **Settings > General > Sharing**
  2. In the **Content & Media** section, enable **File Sharing** if not done already.

![smb_mac1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-158c8928-43ae-0df9-cade-00dae323177f.png)
  3. On the right side of the File Sharing option, select the Info sign.
  4. Select the share for which you want to assign Permissions and assign the Permissions to the necessary user.

![smb_mac2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4f8865d5-dff2-9d34-1384-e098ad67529e.png)
    - **Read Only**: Required for listing and scanning shares.
    - **Read & Write**: Required for quarantine purposes for source and quarantine shares.
7. Proceed to [Connecting SMB with Securiti](/latest/docs/connecting-smb-with-securiti).

To include the `created_date` in your files, see the [Troubleshooting for SMB connector](/latest/docs/troubleshooting-for-smb-connector).
