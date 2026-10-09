---
title: "Upgrading version for SMB connector"
slug: "migrating-from-smbv1-to-smbv2-3"
updated: 2026-08-31T09:23:34Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/migrating-from-smbv1-to-smbv2-3"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Upgrading version for SMB connector

This guide explains how to verify that your file server supports SMBv2 or SMBv3, migrate your existing connector to a supported SMB version, validate the connection after migration, and troubleshoot common migration issues.

> [!NOTE]
> Note
> 
> SMBv1 is a legacy protocol with known security limitations. To improve security and performance, Securiti is transitioning SMB connections from SMBv1 to the supported SMBv2 and SMBv3 protocols. Securiti recommends you to use SMBv3 when your file server supports it.

## Prerequisites

Before you reconfigure the connector:

- Confirm that your file server supports SMBv2 or SMBv3.
- Make sure that no scans are in progress for the connector. You cannot reconfigure a connector while a scan is running.
- Confirm that you have the required permissions to update the connector configuration.

Use one of the following options to confirm which SMB versions your file server supports.

#### Option 1: Use nmap (Recommended)

1. If you have nmap installed on a system that can connect to the file server, open a terminal or command prompt on that system and run:

`nmap --script smb-protocols &lt;server-ip&gt;`
2. Replace `&lt;server-ip&gt;` with the IP address of your file server.
3. Review the supported SMB dialects returned by the command. If the results include **2.0.2, 2.1, 3.0, 3.0.2, or 3.1.1**, your file server supports SMBv2 or SMBv3 and is ready for migration.

#### Option 2: Use Windows PowerShell

1. If your file server is running Windows, open Windows PowerShell with administrator privileges on the file server and run:

`Get-SmbServerConfiguration | Select EnableSMB1Protocol, EnableSMB2Protocol`
2. Ensure that `EnableSMB2Protocol` is set to `True`.

If SMBv2 is disabled, you can enable it by running the following command:

`Set-SmbServerConfiguration -EnableSMB2Protocol $true`

> [!NOTE]
> Note
> 
> Review your organization's security and change-management requirements before modifying the SMB configuration on your file server.

#### Option 3: Verify Samba configuration on Linux

1. If your file server is running Samba on Linux, open a terminal on the file server and review the Samba configuration:

`/etc/samba/smb.conf`

You can also run the following command in the terminal to check the installed Samba version:

`smbd --version`
2. Confirm that the Samba version and configuration support SMBv2 or SMBv3 before proceeding with the migration.

## Reconfigure the connector

After confirming that your file server supports SMBv2 or SMBv3:

1. Make sure that no scans are currently in progress for the connector.
2. In the **Integrations > Monitored Data Systems**, open your relevant connector's **Authentication** page.
3. On the **Authentication** page, under **SMB Version**, enter `3.x` if your file server supports SMBv3. If SMBv3 is not supported, enter `2.x`, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-10 at 9.23.42 AM.png)
4. After entering the relevant SMB Version, click **Save Configuration and Continue**.

Securiti activates the connector using the selected SMB version.

## Verify the migration

After you save the updated configuration, Securiti validates the connection.

The connector diagnostic utility checks the updated configuration and can identify issues such as:

- Connectivity errors.
- Missing or insufficient permissions.
- Authentication errors.
- Configuration issues.

Review the diagnostic results and resolve any reported issues. For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

#### Additional resources

- [SMB FAQs](/latest/docs/smb-faqs)
