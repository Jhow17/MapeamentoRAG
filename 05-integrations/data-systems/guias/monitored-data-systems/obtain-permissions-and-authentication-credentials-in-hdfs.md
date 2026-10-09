---
title: "Obtain permissions and authentication credentials in HDFS"
slug: "obtain-permissions-and-authentication-credentials-in-hdfs"
updated: 2026-07-08T08:02:11Z
published: 2026-07-08T08:02:11Z
canonical: "helpcenter.securiti.ai/obtain-permissions-and-authentication-credentials-in-hdfs"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain permissions and authentication credentials in HDFS

Hadoop Distributed File System uses the following Authentication methods. The Table below shows the authentication credentials required for each Authentication method.

| Authentication method | Authentication Credentials |
| --- | --- |
| No Authentication | - User (If you are not using Keyring) - WebHDFS API Port |
| Password (Kerberos) | - Kerberos Host - Kerberos Port - Kerberos Realm - Kerberos Principal for Namenode (If you are not using Keyring) - (Optional) Kerberos Principal for User (If you are not using Keyring) - Kerberos User Password (If you are not using Keyring) - Data transfer protection |
| Keytab (Kerberos) | - Kerberos Host - Kerberos Port - Kerberos Realm - Kerberos Principal for Namenode (If you are not using Keyring) - (Optional) Kerberos Principal for User (If you are not using Keyring) - Data transfer protection (If you are not using Keyring) - Kerberos Keytab (If you are not using Keyring) |

> [!NOTE]
> **Note**
> 
> We assume you have an HDFS Instance running or have access to its admin to obtain the necessary permissions for connector activation. Also, to use the Kerberos method, we assume you have Kerberos running separately before connector activation.

The procedure below explains steps to acquire Authentication credential for all Authentication methods.

1. Acquire the following values needed for all types of Authentication.
  - **Host**: Obtain the domain or IP address of the HDFS NameNode from your system administrator or by accessing the HDFS Configuration files (*core-site.xml* and *hdfs-site.xml*). For example; *namenode.example.com*
  - **Port**: Identify the port on which the HDFS NameNode is listening. This is typically configured in *hdfs-site.xml*. Common default port is *8020*.
  - **Path**: Determine the HDFS path you need to scan. Ensure the path includes any necessary namespaces. For example; */data/user-files*.
2. **For no Authentication**: In environments where HDFS does not require Authentication, you can directly access the system by gathering the above mentioned parameters and the user value.
  - **User**: Use the HDFS username that will be used for accessing the filesystem. In a No Authentication setup, this might be any username configured for accessing HDFS. For example; *hdfs*
3. For **Keytab** or **Password** based Authentication using Kerberos, record the following values.
  - **Kerberos Host**: Record the domain or IP address of the Kerberos Key Distribution Center (KDC) or the Kerberos service. You can record this value from the Kerberos config file. See an example below for host.

For example; *kerberos.example.com*
  - **Kerberos Port**: This is the network port on which the Kerberos service (usually the KDC) listens for Authentication requests. You can record this value from the Kerberos config file. The default port for Kerberos is typically 88, but this can vary based on Configuration.
  - **Kerberos Realm**: Identify the Kerberos realm associated with your organization. You can record this value from the Kerberos config file under the "[realms]" section. See an example below for realm name.

For example; *EXAMPLE.COM*
  - **Kerberos Principal for Namenode:** Identify the Service Principal Name (SPN) for the Namenode. You can record this value from the HDFS Configuration file such as *core-site.xml*. See an example below for SPN.

For example; *hdfs/namenode.example.com@EXAMPLE.COM* where *EXAMPLE.COM* is the realm name.
  - (Optional) **Kerberos Configuration File**: The Kerberos Configuration file (krb5.conf) is used to define the realms, domain mappings, and server details required for secure Authentication via Kerberos in the HDFS Connector Activation process in Securiti.

> [!NOTE]
> **Important**
> 
> You must have a Pod version 1.121.0 or higher to use the Kerberos Configuration file.
4. **For Password based Authentication (Kerberos with password)**: For environments using Kerberos Authentication with a password, acquire the following parameters in addition to the ones specified in step 3 above.
  - **Kerberos Principal for User**: Identify the Kerberos principal for the user. For example; *john/namenode.example.com@EXAMPLE.COM* where *john* is the username and *EXAMPLE.COM* is the realm name.
  - **Kerberos User Password**: Use the password associated with the Kerberos principal. The password for the Kerberos principal is usually set when the principal is created. If you are the administrator, you can set or reset the password using the Kerberos admin tools.
5. **For Keytab Authentication (Kerberos with Keytab)**: When using Kerberos with Keytab files, the Credentials are stored in a keytab file, which provides an automated login without requiring a password. Acquire the keytab file in addition to the parameters specified in step 3 above.
  - **Keytab File**: Upload the keytab file generated or provided by your Kerberos administrator. The keytab file uses **.keytab** file extension.
6. For **Keytab** or **Password** based Authentication using Kerberos, specify the **Data Transfer Protection** value. Select one of the following SASL protection values from the menu.
  - Authentication
  - Integrity
  - Privacy
7. (Optional) For **Keytab** or **Password** based Authentication using Kerberos, you can upload a Kerberos Config File (krb5.conf). It is usually available on path `/etc/krb5.conf` on Kerberos Server machine. When provided, you no longer need to record the following parameters.
  - Kerberos Host
  - Kerberos Port
  - Kerberos Realm
8. Proceed to [Connecting HDFS (Self-hosted) with Securiti](/latest/docs/connecting-hdfs-self-hosted-with-securiti).
