---
title: "Create and configure a Firebird server"
slug: "create-and-configure-a-firebird-server"
updated: 2026-07-20T11:43:42Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/create-and-configure-a-firebird-server"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create and configure a Firebird server

> [!NOTE]
> **Note**
> 
> This procedure requires different commands depending on the operating system you have. Refer to the [Firebird documentation](https://firebirdsql.org/file/documentation/html/en/firebirddocs/qsg5/firebird-5-quickstartguide.html) for variation in the following operating systems:
> 
> - Windows
> - Linux
> - Mac OS

Configure your Firebird server to integrate with Securiti by following the procedure below.

1. Go to the Firebird website's [Downloads](https://www.firebirdsql.org/en/server-packages/) page to download the installation kit according to your processor and operating system type.

| Operating system | Installation kit |
| --- | --- |
| Linux | Use the terminal command to download the installation kit file. The link in the command varies according to the processor size. See the [Firebird documentation](https://firebirdsql.org/file/documentation/html/en/firebirddocs/qsg5/firebird-5-quickstartguide.html#qsg5-installing-kits) for the installation kit. |
| Windows | Download the installation kit file by clicking on the relevant link on the [downloads](https://www.firebirdsql.org/en/server-packages/) page. See the example for the 64-bit Windows system. `Firebird-5.0.1.1469-0-windows-x64.exe` |
| Mac | Download the installation kit file by clicking on the relevant link on the [downloads](https://www.firebirdsql.org/en/server-packages/) page. See the example for 64-bit Mac OS. `Firebird-5.0.1.1469-0-macos-x64.pkg` |
2. (Optional) Update the Firebird Database and install licenses.

Refer to [Firebird documentation](https://firebirdsql.org/file/documentation/html/en/firebirddocs/qsg5/firebird-5-quickstartguide.html) for upgrading the Database and installing licenses. You can skip this step if you do not want to perform this additional step.
3. **Extract and install the Firebird file.**
  - Refer to matching procedure for Windows and Mac operating systems:
    1. Access the downloaded file in the relevant drive.
    2. Start the installation. Setup screen appears as shown below.
    3. Under the **Run Firebird server as** section, select the **Run as a Service** radio button.
    4. Click **Next**.

![InstallScreen-5_0.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e99d5bb4-eeb8-d4cc-86ca-a54276d96b90.png)
    5. Finish the installation process by clicking **Next** on each screen.
  - Refer to the matching procedure for the Linux operating system:

This procedure contains examples for 64-bit operating systems, you can use [Firebird documentation](https://firebirdsql.org/file/documentation/html/en/firebirddocs/qsg5/firebird-5-quickstartguide.html) to get commands for your operating system
    1. Access the *.tar.gz* file. See the example of a command for the 64-bit operating system.

```plaintext
ubuntu#  tar -xvzf Firebird-5.0.1.1469-0-linux-x64.tar.gzubuntu# sudo systemctl start firebird
```
    2. Access the Firebird file directory. See the example of a command for the 64-bit operating system.

```plaintext
ubuntu#  cd Firebird-5.0.1.1469-0-linux-x64
```
    3. Use the following command to install the Firebird file. See the example of a command for the 64-bit operating system.

```plaintext
ubuntu# sudo ./install.sh
```

On successful installation, following screen appears in the terminal.

![Install-linux.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-71435fa7-8b01-ebd9-63f2-5df1c4867b8b.png)
4. Start and Enable Firebird Service.

Refer to [Firebird documentation](https://firebirdsql.org/file/documentation/html/en/firebirddocs/qsg5/firebird-5-quickstartguide.html) to get more information on starting and enabling Firebird service.
  - For Windows and Mac, it is enabled at the time of installation in the Step 3.
  - Refer to the matching procedure to start and enable Firebird service for the Linux operating system.
    1. Use the following command to start the Firebird.

```plaintext
ubuntu# sudo systemctl start firebird
```
    2. Use the following command to enable the Firebird service.

```plaintext
ubuntu# sudo systemctl enable firebird
```
5. Verify the installation.

Refer to [Firebird documentation](https://firebirdsql.org/file/documentation/html/en/firebirddocs/qsg5/firebird-5-quickstartguide.html) to get more information on verifying the installation in various operating systems.
  - For Windows and Mac operating systems, go to services and make sure the Firebird runs as a service.
  - For Linux operating system, use the following command to verify the Firebird installation.

```plaintext
ubuntu# sudo systemctl status firebird
```
6. Access the isql tool.

For the Linux, Windows, and Mac operating systems, refer to section "Default disk locations" in [Firebird documentation](https://firebirdsql.org/file/documentation/html/en/firebirddocs/qsg5/firebird-5-quickstartguide.html) to access the isql tool.
7. Create the Firebird Database.

For the Linux, Windows, and Mac operating systems, refer to section Creating a Database using isql in [Firebird documentation](https://firebirdsql.org/file/documentation/html/en/firebirddocs/qsg5/firebird-5-quickstartguide.html) to create a Firebird Database. See the example command for creating a Database.

```plaintext
CREATE DATABASE 'localhost:/opt/firebird/data/mydatabase.fdb' 
USER 'SYSDBA' PASSWORD 'yourpassword';
```

It creates a successful Firebird server Connection in your operating system.
8. Record the Credentials for Connector Activation.

On the Firebird server **Connection settings** dialogue box, record the following parameters for Connector Activation:
  - Host
  - Port
  - Path
  - Username
  - Password

![activation-parameters-hide.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dac13166-f089-3647-6c43-1d3e022d52e0.png)
9. Proceed to [Connect Firebird connector with Securiti](/latest/docs/connect-firebird-connector-with-securiti).
